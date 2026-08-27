# Trust Protocol

## Overview

Trust Protocol is a fully separate, standalone Hono service that provides identity clearance, policy clearance, and trust resolution for any platform that integrates via API key. SIMARA is the primary caller, but the service is platform-agnostic.

**It never holds user PII, VCs, or a sanctions list.** It verifies identity claims that wallets present to it, evaluates policy rules, computes trust scores from signals, and queries external sanctions databases independently.

## Architecture

```text
Platform (SIMARA) ──POST /v1/evaluate──► Trust Protocol
                                                │
                           ┌────────────────────┼────────────────────┐
                           ▼                    ▼                    ▼
                    IC (Identity        PC (Policy          TR (Trust
                    Clearance)          Clearance)          Resolution)
                    - DID resolution    - Rule engine        - D1 signals
                    - W3C VP verify     - D1 cache (60s)     - Score formula
                    - Sanctions check   - Phase 2: SLOAD     - Phase 2: RPC
                           │                    │                    │
                           └────────────────────┴────────────────────┘
                                                │
                                         composer.ts
                                         (Decision 1 logic)
                                                │
                                         TrustProtocolResult
                                         { verdict, ic, pc, tr, vpHash, ... }
```

## Trust Score Thresholds

| Action | Minimum Score |
|---|---:|
| swap / staking / lp_provision | 800 |
| marketplace_listing | 900 |
| institutional_lp / cex_bridge / settlement / treasury_transfer / agent_operation | 1000 |

Review band: threshold − 50. Score in band + soft flags → REVIEW instead of BLOCK.

## Verdict Composition

```text
if (!ic.passed || !pc.passed) → BLOCK
if (tr.trustScore === null)    → BLOCK (no history)
if (!tr.meetsThreshold)        → BLOCK
if (score in reviewBand && softFlags.length > 0) → REVIEW
else → CLEAR
```

## API

- `GET /v1/health` — public service health and feature map.
- `POST /v1/evaluate` — API-key protected evaluation endpoint.
- `GET /v1/score/:did` — API-key protected trust score lookup.
- `POST /v1/signals` — API-key protected trust-signal write.
- `GET /v1/audit/:evalId` — API-key protected audit lookup.
- `POST /admin/keys` — admin-token protected API-key issuance.
- `DELETE /admin/keys/:keyId` — admin-token protected key revocation.

## Local Development

```bash
npm install --legacy-peer-deps
npm run db:migrate:local
npm run db:seed
npm run build
pm2 start ecosystem.config.cjs
```

**Test API key (local only):** `test-simara-api-key-dev-only`

## Deployment

- Platform: Cloudflare Pages
- Database: Cloudflare D1 (`trust-protocol-production`)
- Production deployment: pending
- Secrets: `OFAC_API_KEY`, `CHAINALYSIS_API_KEY`, `ELLIPTIC_API_KEY`, `ELLIPTIC_API_SECRET`, `TP_ADMIN_SECRET`

## Phase 2 Upgrade Paths

- Ed25519 VP/VC signature verification and DID resolution in `src/ic/identity-clearance.ts`
- StatusList2021 revocation checks in `src/ic/identity-clearance.ts`
- Live Chainalysis and Elliptic checks in `src/sanctions/sanctions-verifier.ts`
- On-chain policy reads in `src/pc/policy-cache.ts`
- On-chain trust-score RPC in `src/tr/trust-score-oracle.ts`

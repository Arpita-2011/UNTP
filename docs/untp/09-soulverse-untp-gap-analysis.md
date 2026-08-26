# Soulverse × UNTP — Gap Analysis

> **Purpose:** Identify the gaps between Soulverse's currently verified/reported infrastructure and what would be required to become a credible UNTP implementation partner.
>
> **Basis:** GitHub `08-soulverse-existing-infrastructure-and-untp-proposal.md`, the Soulverse × UNTP positioning brief dated 26 August 2026, and the current public UNTP documentation. Items that are not confirmed by engineering are deliberately marked **Unverified** rather than treated as existing capability.

## 1. Executive Summary

The assessment does **not** show that Soulverse is currently UNTP-compliant. It shows a potentially credible starting point and a set of gaps that must be closed before external claims are made.

The most important finding is:

> **The existence of working Verifiable Credential issuance and verification is the first blocking technical question.**

The current Soulverse assessment verifies `did:soul` and a working `did:soul` resolver, but the resolver uses a different specification from the UNTP Identity Resolver. The positioning brief also marks SoulWallet, Trust Registry, Trust Protocol, and VC issuance/verification as unverified. fileciteturn11file0

UNTP currently requires software implementers to conform to its credential specifications and registration/conformance process. The current registration guide says a software vendor should publish a vendor DID, include an `issuingSoftware` block in credentials, issue a registration VC, and expose stable URLs; ongoing observations then check signatures, schemas, vocabulary and issuer authority. citeturn0search2turn0search6

Therefore, the proposed strategy is:

```text
Existing Soulverse infrastructure
          ↓
Technical gap assessment
          ↓
UNTP compatibility/conformance layer
          ↓
UNTP test services
          ↓
Software Implementer registration
          ↓
Pilot implementation
          ↓
Enterprise / government adoption
```

---

## 2. Current Soulverse Baseline

### Verified / demonstrated

| Capability | Current assessment | UNTP relevance |
|---|---|---|
| `did:soul` | **Verified** | High |
| `did:soul` resolver | **Verified** | High, but not a direct UNTP match |
| SoulScan | **Existing** | Low for core UNTP; potentially complementary for person-level authentication |
| Soulogram | **Existing** | Low for core UNTP |

### Unverified and requiring engineering confirmation

| Capability | Current assessment | Why it matters |
|---|---|---|
| VC issuance | **Unverified** | Core to issuing UNTP DPP/DCC/DFR/DTE/DIA credentials |
| VC verification | **Unverified** | Core to receiving/verifying UNTP credentials |
| SoulWallet credential support | **Unverified** | Need to establish whether it can hold/issue/use required credential formats |
| Trust Registry | **Unverified** | Potential differentiator, but cannot currently be claimed as production capability |
| Trust Protocol | **Unverified** | Potential trust/discovery layer, but architecture must be confirmed |
| Credential status/revocation | **Unverified** | Needed for robust credential lifecycle handling |
| UNTP Identity Resolver compatibility | **Not established** | Existing resolver uses a different specification |
| UNTP-specific credential types | **Not established** | Requires schema/context/type implementation |
| UNTP implementation registration | **Not started** | Required for the proposed software-implementer path |

The source positioning brief explicitly says that Soulverse currently has no UNTP registration or working-group relationship, making this a pre-outreach assessment rather than an existing partnership. fileciteturn11file0

---

## 3. Gap Matrix

| # | Area | Current Soulverse state | UNTP expectation / target | Gap | Priority |
|---|---|---|---|---|---|
| G1 | DID | `did:soul` exists | Supported DID method usable by UNTP flows | Compatibility must be validated | **P0** |
| G2 | DID resolver | Working `did:soul` resolver | UNTP Identity Resolver / linkset model | Existing resolver is not a plug-in match | **P0** |
| G3 | VC issuance | Unverified | Issue UNTP-compatible W3C VCs | Need to prove existing capability or build it | **P0** |
| G4 | VC verification | Unverified | Verify incoming UNTP VCs | Need to prove existing capability or build it | **P0** |
| G5 | UNTP credential model | Not established | Implement relevant UNTP credential types/schemas | Mapping and implementation gap | **P0** |
| G6 | VC technical profiles | Not established | Support UNTP-recommended technical options | Need profile-level compatibility testing | **P0** |
| G7 | Credential status | Unverified | Support applicable lifecycle/status mechanisms | Engineering validation required | **P1** |
| G8 | Trust Registry | Unverified | Trusted issuer/implementation discovery and trust information | Architecture-to-UNTP mapping required | **P0** |
| G9 | Trust Protocol | Unverified | Trust/discovery/verification flows compatible with UNTP | Architecture and API mapping required | **P0** |
| G10 | Digital Identity Anchor | Not established | Understand/consume or potentially support DIA flows | Need implementation assessment | **P1** |
| G11 | Identifier resolution | Not established | Identity resolver/linkset patterns | Need implementation or adapter | **P1** |
| G12 | Key management | Not established for UNTP | Secure keys, rotation and verification | Need engineering evidence | **P1** |
| G13 | `issuingSoftware` | Not established | Include software/vendor/version metadata in issued credentials | New implementation requirement | **P0** |
| G14 | Vendor DID | Not established for SWI registration | Publish vendor DID at controlled domain | Registration gap | **P0** |
| G15 | Registration VC | Not established | Issue SoftwareVendorEntry registration VC | Registration gap | **P0** |
| G16 | Stable credential URLs | Not established | Expose stable URLs for registration/credentials | Infrastructure requirement | **P1** |
| G17 | Conformance testing | Not started | Pass UNTP test services | New validation work | **P0** |
| G18 | Continuous observation | Not started | Remain conformant under rolling observations | Operational requirement | **P1** |
| G19 | UNTP scope | Not selected | Declare supported credential types/software scope | Product decision required | **P0** |
| G20 | UNTP implementation register | Not registered | Registered/discoverable implementation | Process gap | **P0** |
| G21 | Government/enterprise integration | Directionally relevant | Production integration with supply-chain systems | Use-case-specific development | **P1** |
| G22 | Person-level identity | SoulScan exists | Not a core UNTP requirement | Potential complementary capability only | **P2** |
| G23 | Governance participation | No current participation | Optional ecosystem contribution | Partnership/ecosystem gap | **P2** |

---

## 4. G1 — DID Compatibility

### What we have

Soulverse has a working `did:soul` identifier system. This is a genuine foundation because UNTP uses DIDs for issuer identification.

### Gap

Having a DID method does **not** automatically mean it is compatible with every UNTP workflow.

The following must be tested:
- DID document structure
- verification methods
- authentication methods
- service endpoints
- key rotation
- resolution response
- interoperability with UNTP-required DID discovery patterns
- domain/authority relationships where required

### Acceptance criteria

A Soulverse DID can be used as an issuer/controller identity in a UNTP test scenario and can be resolved and verified by an independent implementation.

---

## 5. G2 — Resolver Gap

UNTP's current Identity Resolver specification defines structured linkset responses and is aligned with the GS1 resolver linkset schema/RFC 9264. It distinguishes identifiers that are discoverable, resolvable and verifiable. citeturn0search1

The Soulverse assessment says the current `did:soul` resolver is working but follows a different resolver specification. fileciteturn11file0

### Gap

```text
Soulverse resolver
       ≠
UNTP Identity Resolver
```

### Proposed solution

Do **not** discard the existing resolver immediately.

Evaluate an adapter or a UNTP-compatible resolver service that maps Soulverse identity data to the UNTP linkset/API model.

### Acceptance criteria

An independent UNTP verifier can:
1. resolve the relevant identifier;
2. receive the expected structured response;
3. discover relevant credential/service links; and
4. continue the verification flow without a Soulverse-specific integration.

---

## 6. G3/G4 — Verifiable Credential Gap

This is the highest-risk unknown.

UNTP recommends W3C Verifiable Credentials for its major credential types, including Product Passports, Conformity Credentials, Traceability Events, Facility Records and Identity Anchors. citeturn0search7

The Soulverse positioning assessment explicitly marks VC issuance and verification as **Unverified**. fileciteturn11file0

### Questions engineering must answer first

1. Can Soulverse issue W3C VCs today?
2. Can Soulverse verify external W3C VCs today?
3. Which VC data model/version is supported?
4. Which proof formats are supported?
5. Can credentials be represented using JSON-LD where required?
6. Are JWT/JOSE or SD-JWT profiles supported where required?
7. Can credentials be revoked/status-checked?
8. Can credentials be hosted at stable URLs?
9. Can an issuer's DID be independently resolved?
10. Can the existing wallet consume these credentials?

### Decision gate

```text
VC capability confirmed
       │
       ├── YES → map to UNTP VC profiles
       │
       └── NO  → estimate VC infrastructure build
```

No external claim about UNTP readiness should be made before this gate is answered.

---

## 7. G5 — UNTP Credential Types

UNTP is not simply "VC compatible." It defines interoperable credential types and discovery mechanisms for supply-chain transparency. citeturn0search13

Relevant types include:
- Digital Product Passport (DPP)
- Digital Conformity Credential (DCC)
- Digital Traceability Event (DTE)
- Digital Facility Record (DFR)
- Digital Identity Anchor (DIA)

### Gap

Even if Soulverse supports generic VCs, that does not prove support for UNTP credential schemas, vocabulary and business rules.

### Required work

Create a credential-by-credential compatibility matrix:

| Credential | Issue | Verify | Schema | Vocabulary | Discovery | Priority |
|---|---|---|---|---|---|---|
| DPP | TBD | TBD | TBD | TBD | TBD | High |
| DCC | TBD | TBD | TBD | TBD | TBD | High |
| DTE | TBD | TBD | TBD | TBD | TBD | Medium |
| DFR | TBD | TBD | TBD | TBD | TBD | Medium |
| DIA | TBD | TBD | TBD | TBD | TBD | High |

Do not attempt all credential types initially. Select the smallest commercially meaningful scope for a pilot.

---

## 8. G8/G9 — Trust Registry & Trust Protocol

These are potentially Soulverse's strongest differentiators, but they are currently unverified in the source assessment. fileciteturn11file0

### Gap

We need to establish whether the existing products are:
- implemented;
- production-ready;
- documented;
- API-accessible;
- capable of representing trusted issuers/entities;
- capable of resolving trust information;
- capable of policy-based verification;
- capable of handling authority/delegation relationships;
- interoperable with UNTP's registers and resolver model.

### Important distinction

UNTP's Software Implementer Register is itself an ecosystem governance mechanism. The register answers which software issued a credential and whether that software is conformant. The current UNTP design uses continuous observations rather than treating registration as a one-time certification. citeturn0search6turn0search8

Therefore, a Soulverse Trust Registry should **complement** UNTP governance rather than attempt to replace the UNECE-maintained implementation register.

### Proposed role

```text
UNTP registers / governance
          ↓
Soulverse Trust Infrastructure
          ↓
Enterprise / government trust decisions
```

This is a proposal to validate, not a current compliance claim.

---

## 9. G10 — Digital Identity Anchor

UNTP's Digital Identity Anchor is a W3C VC issued by an authoritative register and binds a DID to an already-recognised registered identity such as a business, facility or trademark. The authoritative register—not the entity being anchored—is the issuer. citeturn0search0

### Gap

Soulverse's current identity model is not enough by itself to become a DIA issuer.

A DIA requires an authoritative identity authority and appropriate trust relationships.

### Potential Soulverse role

Soulverse could potentially:
- consume and verify DIAs;
- support DIA discovery;
- provide infrastructure to authoritative registrars if a deployment requires it;
- integrate DIA verification into enterprise/government workflows.

It should **not** claim that Soulverse itself is an authoritative registrar unless a specific government or authority relationship exists.

---

## 10. G13–G20 — Software Implementer Registration

This is a concrete operational gap.

The current UNTP registration guide identifies a practical registration sequence:

1. Publish a vendor DID at a controlled domain.
2. Include an `issuingSoftware` block in every credential issued by the software.
3. Use a stable `softwareVersionId` per build.
4. Issue a registration VC describing the vendor, products, versions and declared UNTP scope.
5. Host the registration VC at a stable URL and notify UNECE.
6. Optionally implement a binding-credential service for a stronger conformance signal.
7. Pass ongoing observation checks. citeturn0search2

### Soulverse gaps

| Requirement | Status |
|---|---|
| Vendor DID | Not established |
| Controlled domain | To confirm |
| `issuingSoftware` | Not established |
| Stable software version IDs | Not established |
| Registration VC | Not established |
| Stable registration URL | Not established |
| Declared UNTP scope | Not decided |
| Binding credential service | Optional / not assessed |
| Conformance test | Not started |
| Register entry | Not registered |

### Why this matters

UNTP's register is designed to provide discoverability and an ongoing signal of implementation conformance, not simply a marketing badge. citeturn0search6

---

## 11. G17 — Conformance Testing

Conformance testing is a formal requirement for implementation registration. UNTP provides test services and a test playground for implementers to test credentials against UNTP standards. citeturn0search3

### Gap

Soulverse currently has no established UNTP conformance test result.

### Required work

- Obtain the relevant UNTP test cases.
- Implement a minimal UNTP credential flow.
- Test schemas.
- Test vocabulary resolution.
- Test signatures.
- Test issuer DID reachability.
- Test discovery/resolution.
- Test credential lifecycle where applicable.
- Document failures and remediation.

The registration system also performs ongoing observations, including signature, schema, vocabulary and issuer-authority checks. citeturn0search2

---

## 12. G21 — Enterprise & Government Integration

This is not a single UNTP protocol gap. It is a **productisation gap**.

UNTP is designed so independent actors can participate without a central data store. citeturn0search12

Soulverse therefore needs to demonstrate that the infrastructure can be integrated into:
- existing enterprise systems;
- government registers;
- certification systems;
- supply-chain applications;
- ERP/PLM/traceability platforms;
- existing identity infrastructure.

### Proposed product

A reusable **Soulverse UNTP Integration Layer** could expose:

```text
Enterprise / Government System
             ↓
       Soulverse APIs
             ↓
      UNTP Adapter Layer
             ↓
 DID / VC / Trust / Resolver
             ↓
       UNTP ecosystem
```

---

## 13. G22 — Person-Level Identity

SoulScan is relevant to authenticating individuals, but this is not a core UNTP requirement.

The source assessment identifies a possible complementary model:

```text
UNTP
  → establishes trust in the organisation

Soulverse
  → potentially establishes trust in the person acting for that organisation
```

For example, a future workflow could link an authenticated employee/operator to an organisation's UNTP identity.

However:

> **This is a proposed extension/opportunity, not an existing UNTP requirement.**

It should not be part of the initial UNTP implementation scope.

---

## 14. G23 — Ecosystem / Partnership Gap

Soulverse currently has no UNTP registration, working-group relationship or UNTP-facing implementation material according to the positioning assessment. fileciteturn11file0

The immediate ecosystem gap is therefore not "become a partner" in the abstract. It is to establish technical credibility first.

Recommended order:

```text
Technical validation
       ↓
UNTP pilot
       ↓
Conformance evidence
       ↓
Software Implementer registration
       ↓
Technical ecosystem participation
       ↓
Government / enterprise partnerships
```

---

## 15. Priority Classification

### P0 — Blocking

These determine whether Soulverse can realistically become a UNTP implementation partner:

1. VC issuance
2. VC verification
3. UNTP credential model support
4. DID compatibility
5. Resolver compatibility
6. `issuingSoftware` implementation
7. Vendor DID and registration VC
8. UNTP scope selection
9. Conformance testing
10. Software Implementer registration
11. Trust Registry/Trust Protocol architecture validation

### P1 — Required for production readiness

- Credential status/revocation
- Key management
- Stable URLs/hosting
- DIA consumption/discovery
- Enterprise/government integrations
- Operational monitoring
- Continuous conformance management

### P2 — Strategic extensions

- Person-level authentication through SoulScan
- Additional ecosystem governance participation
- Industry-specific extensions
- Broader government trust infrastructure

---

## 16. Recommended MVP

Do **not** attempt to make the entire Soulverse stack UNTP-compatible initially.

Build one narrow end-to-end flow:

```text
Organisation
    ↓
Soulverse DID
    ↓
UNTP-compatible credential
    ↓
Soulverse Trust / Registry layer
    ↓
UNTP-compatible discovery/resolution
    ↓
Independent verifier
    ↓
Verified result
```

### MVP success criteria

- Credential can be issued.
- Credential validates against the selected UNTP schema.
- Issuer DID resolves independently.
- Relevant trust information is discoverable.
- Credential can be independently verified.
- `issuingSoftware` identifies the Soulverse implementation/version.
- Credential passes the relevant UNTP test service.
- Architecture does not require the verifier to use Soulverse-specific software.

---

## 17. Engineering Questions — First Meeting

Before writing implementation tickets, engineering should answer these questions:

### VC
1. Do we currently issue W3C VCs?
2. Do we currently verify external VCs?
3. Which VC versions/proof formats are supported?
4. Where is the implementation in the repository?

### DID
5. How does `did:soul` resolve?
6. What resolver specification does it implement?
7. Can we expose an RFC 9264/UNTP-style linkset resolver?

### Trust Registry
8. Does the Trust Registry exist as implemented code?
9. What entities/relationships does it model?
10. What APIs are available?

### Trust Protocol
11. Does the Trust Protocol exist as implemented code?
12. What problem does it solve?
13. What are its APIs and data models?

### Wallet
14. Can SoulWallet issue, receive, store and present the credential types required for the chosen UNTP pilot?

### Operations
15. Can we host stable credential URLs?
16. Can we support credential status/revocation?
17. How are keys generated, stored, rotated and recovered?
18. Can we add `issuingSoftware` and stable software-version identifiers?

### UNTP
19. Which UNTP credential type should be our first implementation?
20. What is the smallest conformance scope we can register?

---

## 18. Business Decision Gate

After the technical assessment, use this decision tree:

```text
                  VC capability?
                     /     \
                   NO       YES
                   /          \
          Estimate build      ↓
             effort       Resolver gap?
                             /     \
                           HIGH     LOW
                            ↓         ↓
                      Adapter /    Continue
                      redesign
                            \         /
                             ↓       ↓
                       UNTP POC
                           ↓
                     Conformance
                           ↓
                  Implementation Register
                           ↓
                    Commercial pilot
```

The business case should only be approved after the POC demonstrates that the gaps can be closed without disproportionate architectural change.

---

## 19. Final Assessment

### Current position

**Potentially compatible foundation, but not yet a UNTP implementation.**

### Strongest verified asset

`did:soul` + working resolver.

### Strongest potential differentiator

Trust Registry + Trust Protocol — **subject to engineering confirmation**.

### Biggest technical uncertainty

Verifiable Credential issuance and verification.

### Biggest interoperability gap

The existing Soulverse resolver is not currently the same resolver specification used by UNTP.

### Biggest ecosystem gap

No current UNTP registration or demonstrated conformance.

### Recommended strategy

> **Validate the existing Soulverse trust stack first, build a narrow UNTP compatibility layer, pass conformance testing, register as a Software Implementer, and then use that technical credibility to pursue government and enterprise implementation opportunities.**

This keeps UNTP as the open standard and keeps Soulverse's proprietary infrastructure differentiated around implementation, trust services, integration and product delivery.

---

## Sources

- UNTP Architecture: https://untp.unece.org/docs/specification/Architecture/
- UNTP Technical Specifications: https://untp.unece.org/docs/specification/
- UNTP Verifiable Credentials: https://untp.unece.org/docs/specification/VerifiableCredentials/
- UNTP Identity Resolver: https://untp.unece.org/docs/specification/IdentityResolver/
- UNTP Digital Identity Anchor: https://untp.unece.org/docs/specification/DigitalIdentityAnchor/
- UNTP Requirements: https://untp.unece.org/docs/about/Requirements/
- UNTP Registers: https://untp.unece.org/docs/implementations/
- Software Implementers Register: https://untp.unece.org/docs/implementations/swi/
- Software Registration Guide: https://untp.unece.org/docs/implementations/swi/registration-guide/
- UNTP Test Services: https://untp.unece.org/docs/tools-and-support/TestService/
- Soulverse baseline: `08-soulverse-existing-infrastructure-and-untp-proposal.md`
- Soulverse × UNTP positioning brief: 26 August 2026

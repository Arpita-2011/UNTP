# BD Guide — Soulverse Approach to UNTP

> **Audience:** Business Development, Partnerships, Marketing and leadership
>
> **Purpose:** Provide a simple, consistent way to understand UNTP, explain why Soulverse is interested, position Soulverse correctly, and conduct initial conversations with UNECE, governments, enterprises and ecosystem partners.
>
> **Status:** Strategic positioning document. Technical compatibility and some Soulverse capabilities remain subject to engineering validation.

---

## 1. Executive Summary

### What is UNTP?

**UNTP (United Nations Transparency Protocol)** is an open interoperability protocol being developed under the UN/CEFACT ecosystem to help organisations exchange trustworthy supply-chain information across different systems.

In simple terms:

> **UNTP is trying to create a common language for trusted supply-chain information so that organisations do not have to use the same software or build their own trust model from scratch.**

UNTP is explicitly a **protocol, not a platform**. It does not require the entire supply chain to move onto one database or one commercial system. Each participant can keep using its own systems while exchanging information using common standards. citeturn0search1turn0search6

UNTP uses technologies such as Verifiable Credentials, DIDs, identifiers, trust anchors and discovery mechanisms to make supply-chain information verifiable and interoperable.

The current public documentation says public review has closed and UNTP 1.0 is expected on **1 September 2026**; the current specification is suitable for pre-production pilots. citeturn0search1

---

## 2. The Problem UNTP Is Solving

A simple example:

A manufacturer tells a buyer:

> "This product was manufactured using certified sustainable materials."

The buyer needs to know:

- Who made the claim?
- Is the organisation legitimate?
- Who certified the claim?
- Which standard or scheme was used?
- Is the credential genuine?
- Has the information been changed?
- Is the credential still valid?
- Can the product/facility identifier be independently resolved?
- Can the evidence be connected to other supply-chain evidence?

Today, this can involve different databases, certificates, platforms and manual verification processes.

UNTP's approach is to create a common interoperability layer so that these claims can be digitally issued, discovered and independently verified across systems.

The UNTP trust model is designed so a verifier can follow the chain from a credential to the issuing software, conformity scheme and identifiers involved. citeturn0search10

---

## 3. Why This Is Relevant to Soulverse

Soulverse is already working in the broader digital trust space around:

- Decentralised Identity
- Verifiable Credentials
- Identity verification
- Trust infrastructure
- Trust Registry / Trust Protocol concepts
- Government and enterprise identity use cases

This creates a potential alignment with UNTP.

However, the correct statement is **not**:

> "Soulverse already supports UNTP."

The correct statement is:

> **"Soulverse has an existing digital-trust foundation that we believe can be adapted to support UNTP. We are currently validating the technical gaps and exploring how we can contribute as an implementation partner."**

That distinction is important for BD conversations.

---

## 4. Our Strategic View

We should treat UNTP as an **ecosystem opportunity, not a competitor**.

### UNTP's role

UNTP provides:

- Common standards
- Interoperability rules
- Credential/data models
- Trust and identity patterns
- Discovery mechanisms
- Conformance mechanisms
- Open governance
- Implementation registers

### Soulverse's potential role

Soulverse can potentially provide:

- Identity infrastructure
- Credential infrastructure
- Trust infrastructure
- Trust Registry / discovery capabilities
- Verification infrastructure
- Enterprise/government integrations
- UNTP implementation services
- Products built on top of UNTP

The simple relationship is:

```text
UNTP
  ↓
Defines the common language and rules
  ↓
Soulverse
  ↓
Provides implementation infrastructure + products + integration
  ↓
Government / Enterprise / Supply-chain participants
```

UNTP itself describes its model as a protocol over platforms: organisations can continue using their preferred software as long as implementations conform to the protocol. citeturn0search1turn0search3

---

## 5. How We Should Present Soulverse

### Primary positioning

> **Soulverse is a digital-trust infrastructure and implementation partner. We help governments and enterprises build interoperable identity, credential and trust systems using open standards such as UNTP.**

### UNTP-specific positioning

> **We are exploring UNTP as an interoperability standard for trusted supply-chain information. Our goal is to make Soulverse infrastructure UNTP-compatible and help organisations adopt UNTP without replacing their existing systems.**

### Short version for a meeting

> **"UNTP defines the common trust and interoperability standard; Soulverse can provide the infrastructure and implementation layer that makes it usable in real-world government and enterprise systems."**

### One-sentence version

> **"Soulverse can help organisations implement UNTP by providing identity, credentials, trust, verification and integration infrastructure."**

---

## 6. What We Are Actually Proposing

We should present the opportunity as four complementary tracks.

### Track 1 — UNTP Software Implementation

Implement the relevant UNTP specifications in Soulverse and pursue registration in the UNTP Software Implementers Register.

UNTP explicitly identifies software vendors that issue or verify UNTP credentials as candidates for the Software Implementers Register. The register is intended to make conformant software discoverable to users and customers. citeturn0search0turn0search2

**BD message:**

> "We want to make our infrastructure UNTP-compatible and become a recognised implementation in the UNTP ecosystem."

This is our clearest near-term technical/ecosystem objective.

---

### Track 2 — Trust Infrastructure

Investigate whether Soulverse's Trust Registry and Trust Protocol can support UNTP-related trust and discovery requirements.

**Important:** These capabilities are currently subject to engineering validation. Do not describe them externally as already UNTP-compliant.

Potential future proposition:

> **"Soulverse provides reusable trust infrastructure that can sit underneath UNTP-compatible enterprise and government applications."**

This is potentially our strongest differentiation, but it must be proven technically.

---

### Track 3 — UNTP Implementation Partner

Help organisations adopt UNTP.

Potential services:

- UNTP readiness assessment
- Architecture design
- Identity and credential integration
- Trust infrastructure deployment
- Existing-system integration
- Conformance testing
- Government/enterprise implementation
- Customisation and support

UNTP's implementation model explicitly recognises implementation support and professional/community assistance as part of lowering adoption risk. citeturn0search3turn0search4

**BD message:**

> "Organisations do not necessarily need to build UNTP infrastructure themselves. Soulverse can help them implement it within their existing technology environment."

---

### Track 4 — Ecosystem & Standards Participation

We can contribute to the ecosystem through:

- Technical discussions
- Public reviews
- Implementation feedback
- Conformance testing
- Open-source contributions
- Working-group participation
- Relevant extension discussions

The objective is not simply visibility. It is to gain early technical understanding, influence where appropriate, and build credibility through real implementation experience.

---

## 7. What Makes Soulverse Relevant

The strongest story is not that Soulverse has "blockchain" or "DIDs."

The stronger story is:

### 1. Digital trust infrastructure

Soulverse is building infrastructure around digital identity, credentials and trust.

### 2. Government / enterprise orientation

Our target environment includes organisations where identity, verification, compliance and trust are operational requirements.

### 3. Interoperability mindset

UNTP is based on open standards rather than requiring participants to join one proprietary platform. That aligns with an infrastructure approach rather than a closed ecosystem.

### 4. Potential trust infrastructure differentiation

If validated, the Soulverse Trust Registry and Trust Protocol could become an important part of our differentiation from generic VC/SSI providers.

### 5. Productisation

We can potentially turn standards into usable government and enterprise products rather than stopping at protocol implementation.

---

## 8. What We Already Have vs What Still Needs Validation

BD must use this distinction carefully.

### Verified / established

- `did:soul` exists.
- A working `did:soul` resolver exists.
- SoulScan exists as an identity/verification capability.
- Soulverse has an existing digital-trust product direction.

### Needs engineering confirmation

- UNTP-compatible VC issuance
- UNTP-compatible VC verification
- SoulWallet support for required credential flows
- Trust Registry implementation and API capabilities
- Trust Protocol implementation and API capabilities
- Credential status/revocation
- UNTP Identity Resolver compatibility
- UNTP credential types and schemas
- Key-management requirements
- UNTP conformance

### Not currently claimed

- UNTP certification/compliance
- UNTP Software Implementer registration
- UNTP partnership with UNECE
- UNTP working-group membership
- Government project awarded through UNTP

**BD rule:** Never convert a proposed capability into a current product claim.

---

## 9. Where We Fit in the UNTP Ecosystem

UNTP has an implementation ecosystem with multiple registers and software implementations. The Software Implementers Register is specifically intended for vendors whose software issues or verifies UNTP credentials. citeturn0search2turn0search7

The ecosystem can be understood as:

```text
                    UN / UNTP
                       │
          Standards + Governance
                       │
        ┌──────────────┼──────────────┐
        │              │              │
     Software       Extensions      Trust /
   Implementers                    Identifiers
        │              │              │
        └──────────────┼──────────────┘
                       │
                 Implementations
                       │
        ┌──────────────┼──────────────┐
        │              │              │
   Government      Enterprise      Supply Chain
    systems         systems        participants
```

Soulverse should initially pursue the **Software Implementer + implementation partner** position, while investigating whether its Trust Registry/Protocol can provide a differentiated trust infrastructure layer.

---

## 10. Our Differentiation vs Other Implementation Partners

There are already SSI, VC and trust-infrastructure companies in the UNTP ecosystem.

Therefore, BD should not say:

> "We also do DIDs and VCs."

That is not sufficient differentiation.

Instead, investigate and build the proposition around:

> **Trust infrastructure + implementation + government/enterprise integration.**

Potential differentiation areas:

| Area | BD message |
|---|---|
| Trust Registry | Reusable trust/discovery infrastructure — subject to validation |
| Trust Protocol | Trust relationship/verification layer — subject to validation |
| Enterprise integration | Connect standards to existing systems |
| Government integration | Help public-sector organisations operationalise digital trust |
| Implementation | Move from standard to production system |
| Productisation | Build applications on top of open standards |
| Interoperability | Avoid forcing customers into one proprietary platform |

The actual competitive differentiation should be validated against the current UNTP implementer ecosystem before external positioning is finalised.

---

## 11. What We Should Ask UNTP / UNECE

The first conversation should be a **discovery conversation**, not a sales pitch.

### Questions about the ecosystem

1. What is the recommended path for a technology company wanting to become a UNTP Software Implementer?
2. What technical capabilities are most valuable to the UNTP ecosystem today?
3. Which implementation areas currently have the largest gaps?
4. What types of partners are UNECE/UNTP actively looking for?
5. What does successful implementation-partner participation look like?

### Questions about technology

6. Which UNTP credential types should a new software implementer prioritise?
7. What are the minimum technical requirements for the first implementation?
8. How should an existing DID/resolver infrastructure integrate with the UNTP Identity Resolver?
9. What are the recommended conformance tests for an initial implementation?
10. What is the expected roadmap toward UNTP 1.0 and subsequent versions?

### Questions about adoption

11. Which governments or industries are currently piloting UNTP?
12. Which implementation use cases are closest to production?
13. What sectors are showing the strongest demand?
14. How are implementation partners being connected to adopters?

### Questions about contribution

15. How can Soulverse participate in technical discussions?
16. Can Soulverse contribute implementation feedback or open-source components?
17. Are there specific working groups or implementation pilots where our team could contribute?

---

## 12. What We Should NOT Say

### Avoid

> "UNTP is the future global standard."

Better:

> "UNTP is an emerging UN/CEFACT interoperability standard with significant potential for global adoption."

### Avoid

> "Soulverse is UNTP compliant."

Better:

> "We are assessing and working toward UNTP compatibility/conformance."

### Avoid

> "UNECE selected Soulverse as a partner."

Unless this has actually happened.

### Avoid

> "Soulverse Trust Registry is the UNTP trust registry."

Better:

> "We are assessing whether our Trust Registry can support UNTP's trust and discovery requirements."

### Avoid

> "UNTP will replace existing supply-chain platforms."

Better:

> "UNTP is designed to allow existing systems to interoperate rather than requiring a single platform."

### Avoid

> "Blockchain is required for UNTP."

It is not. UNTP explicitly requires blockchain independence. citeturn0search3

---

## 13. BD Pitch — 60 Seconds

> **"We are exploring UNTP because it addresses a problem that is closely aligned with what Soulverse is building — how organisations can establish and exchange trustworthy digital information across systems.**
>
> **UNTP is being developed under the UN/CEFACT ecosystem as an open interoperability protocol. It is not another platform; it provides common standards so different organisations can exchange verifiable supply-chain information without moving onto the same system.**
>
> **Soulverse already works in the digital trust space with decentralised identity and verification infrastructure, and we are assessing how our trust infrastructure can become UNTP-compatible. Our goal is not to compete with UNTP, but to become an implementation and technology partner that helps governments and enterprises adopt it.**
>
> **We are currently validating the technical gaps, particularly around Verifiable Credentials, resolver compatibility and our Trust Registry/Trust Protocol. Once validated, we want to build a focused UNTP implementation, complete conformance testing and explore registration as a Software Implementer.**
>
> **Longer term, we see an opportunity to help organisations turn UNTP standards into production systems through infrastructure, integration and implementation services."**

---

## 14. BD Pitch — 20 Seconds

> **"UNTP is creating an open standard for trusted, interoperable supply-chain information. Soulverse wants to become an implementation partner — using our identity, credential and trust infrastructure to help governments and enterprises adopt UNTP without replacing their existing systems."**

---

## 15. Potential Commercial Model

The opportunity can develop in stages.

### Stage 1 — Technical implementation

UNTP-compatible Soulverse infrastructure.

### Stage 2 — Pilot

Implement with one government, enterprise or supply-chain ecosystem.

### Stage 3 — Implementation services

Offer:
- Assessment
- Architecture
- Integration
- Deployment
- Conformance
- Support

### Stage 4 — Platform / infrastructure

Offer reusable APIs and infrastructure for organisations building UNTP-compatible solutions.

### Stage 5 — Vertical products

Build specific products around:
- Digital Product Passports
- Certification
- Sustainability evidence
- Traceability
- Compliance
- Government supply-chain programmes

The commercial model should follow actual customer demand rather than assuming UNTP adoption will automatically create revenue.

---

## 16. Recommended Engagement Strategy

### Phase 1 — Learn

Engage with UNTP/UNECE to understand the roadmap, implementation ecosystem and adoption priorities.

### Phase 2 — Validate

Engineering validates Soulverse against UNTP requirements.

### Phase 3 — Build

Create a focused UNTP-compatible POC.

### Phase 4 — Prove

Run conformance tests and document the implementation.

### Phase 5 — Register

Pursue Software Implementer registration if the implementation meets requirements.

### Phase 6 — Sell

Use the implementation as credibility when approaching governments, enterprises and ecosystem partners.

```text
Learn → Validate → Build → Prove → Register → Sell
```

---

## 17. The Story We Want the Market to Remember

The simplest story is:

> **UNTP creates the open standard for trusted supply-chain information. Soulverse helps organisations implement that standard.**

Or even shorter:

> **UNTP defines the trust language. Soulverse helps organisations speak it.**

This is the core positioning to maintain across BD, marketing, partnerships and leadership conversations.

---

## 18. Internal Decision Gates

Before BD makes stronger external claims, these gates should be completed:

### Gate 1 — VC

Can Soulverse issue and verify the relevant UNTP-compatible credentials?

### Gate 2 — Resolver

Can Soulverse interoperate with the UNTP Identity Resolver model?

### Gate 3 — Trust infrastructure

Can the Trust Registry and Trust Protocol demonstrably support the intended UNTP trust/discovery flows?

### Gate 4 — Conformance

Can the implementation pass the relevant UNTP tests?

### Gate 5 — Registration

Can Soulverse become a Software Implementer in the UNTP register?

### Gate 6 — Customer

Can we demonstrate a real customer use case where UNTP interoperability creates measurable value?

Only after these gates should the positioning move from **"exploring UNTP"** to **"UNTP implementation partner."**

---

## 19. Bottom Line for BD

### We are NOT saying:

> "UNTP needs Soulverse."

### We ARE saying:

> "UNTP creates an emerging open standard for trusted supply-chain information. Soulverse has relevant digital-trust capabilities and wants to validate, implement and contribute to that standard. If the technical fit is strong, we can help organisations adopt UNTP through infrastructure, integration and implementation services."

### Our immediate ask from the ecosystem

**Understand → participate → validate → implement → register → partner.**

That is the recommended Soulverse approach to UNTP.

---

## Sources

- UNTP About: https://untp.unece.org/docs/about/
- UNTP Requirements: https://untp.unece.org/docs/about/Requirements/
- UNTP FAQ: https://untp.unece.org/docs/about/FAQ/
- UNTP Technical Specifications: https://untp.unece.org/docs/specification/
- UNTP Implementations: https://untp.unece.org/docs/implementations/
- UNTP Software Implementers: https://untp.unece.org/docs/implementations/swi/
- Software Registration Guide: https://untp.unece.org/docs/implementations/swi/registration-guide/
- Implementation Registers Architecture: https://untp.unece.org/docs/governance/implementation-governance/
- Implementation Plans: https://untp.unece.org/docs/tools-and-support/ImplementationPlans/

# Soulverse Existing Infrastructure & Proposed UNTP Position

> **Purpose:** Internal working document to map Soulverse's existing trust infrastructure to UNTP and define the proposal we could take to the UNTP/UNECE ecosystem.
>
> **Status:** Hypothesis to validate against the current Soulverse implementation and the final UNTP 1.0 specification.

## 1. Executive Summary

UNTP is an open interoperability standard for exchanging trustworthy supply-chain information across independent systems. Soulverse should not position itself as a replacement for UNTP. The proposed position is:

> **UNTP defines the common interoperability and trust language; Soulverse provides infrastructure, products and implementation services that help organisations adopt that language.**

The strategic hypothesis is that Soulverse's existing identity, credential, trust and verification capabilities can be adapted to support UNTP rather than creating a separate UNTP-specific stack.

The first technical question is therefore not "Can we build UNTP?" but:

> **How much of the Soulverse trust stack already satisfies UNTP requirements, and what interoperability/conformance layer is required?**

---

## 2. Soulverse Existing Infrastructure

The following represents the current Soulverse capabilities that are relevant to the UNTP assessment. These should be verified against the actual Soulverse repositories before being treated as final architecture claims.

### 2.1 DID / Decentralised Identity

Soulverse has an identity layer based around DIDs and its own DID method.

**Potential UNTP relevance:**
- UNTP uses DIDs for issuer identification.
- Soulverse can potentially provide DID creation, resolution and management for organisations participating in UNTP ecosystems.

**Validation required:**
- Exact DID method compatibility.
- DID document format and resolution behaviour.
- Key management and rotation.
- Interoperability with the DID methods/resolvers expected by UNTP deployments.

### 2.2 Verifiable Credentials

Soulverse has infrastructure for issuing and verifying Verifiable Credentials.

**Potential UNTP relevance:**
- UNTP's trust model relies heavily on verifiable credentials.
- Soulverse could provide credential issuance and verification infrastructure for UNTP-compatible applications.

**Validation required:**
- VC data model compatibility.
- Supported proof formats.
- JSON-LD / JOSE / SD-JWT requirements where applicable.
- Credential status and revocation.
- Required UNTP credential types and extensions.

### 2.3 Trust Registry

The Soulverse Trust Registry is potentially the strongest strategic fit.

A trust registry can provide infrastructure for recording or resolving trusted entities, issuers, governance relationships and trust information.

**Potential UNTP relevance:**
- UNTP needs mechanisms for discovering and establishing trust in participants and credentials.
- A Soulverse Trust Registry could potentially become a UNTP-compatible trust/discovery component.
- This could provide more differentiated value than simply offering generic VC issuance.

**Validation required:**
- Exact mapping between Soulverse registry data structures and UNTP implementation/register requirements.
- Governance model.
- Issuer onboarding.
- Trust-list semantics.
- Registry APIs.
- Resolution/discovery mechanisms.
- Delegation and authority relationships.

### 2.4 Trust Protocol

Soulverse's Trust Protocol can potentially act as the interoperability layer for trust relationships and verification.

**Potential UNTP relevance:**
- Resolve trusted participants.
- Discover relevant trust information.
- Support verification decisions.
- Connect applications to the Trust Registry.

**Validation required:**
- Whether the protocol's current interfaces map cleanly to UNTP resolver/discovery patterns.
- Whether adapters are sufficient or protocol changes are required.

### 2.5 Credential Verification

Soulverse already has verification capabilities that can potentially be used to verify UNTP-compatible credentials.

**Potential UNTP relevance:**
- Cryptographic verification.
- Issuer verification.
- Credential status verification.
- Trust-chain evaluation.

The important distinction is that UNTP verification is not only "is the signature valid?" It can also involve determining whether the issuer, credential type, conformity scheme, identifier and implementation are trustworthy.

### 2.6 Government / Enterprise Integration Capability

Soulverse's broader product direction includes government and enterprise identity/trust use cases.

**Potential UNTP relevance:**
- Government-issued identity credentials.
- Enterprise onboarding.
- Compliance workflows.
- Integration with existing government/enterprise systems.

This should be treated as an implementation and go-to-market capability rather than assuming every existing integration is automatically UNTP-compliant.

---

## 3. Proposed Soulverse Architecture for UNTP

The preferred approach is an **UNTP compatibility layer over the existing Soulverse trust infrastructure**.

```text
                    UN / UNECE
                        |
                 UNTP Standard
                        |
          Standards + Governance + Schemas
                        |
                        v
             Soulverse UNTP Adapter
                        |
        +---------------+---------------+
        |               |               |
        v               v               v
   Trust Registry   Trust Protocol   VC / DID Layer
        |               |               |
        +---------------+---------------+
                        |
                        v
              Soulverse Trust Platform
                        |
              +---------+---------+
              |                   |
              v                   v
        Government Apps     Enterprise Apps
              |                   |
              +---------+---------+
                        |
                        v
             Supply-chain ecosystems
```

### Principle

Do not fork Soulverse into a separate "UNTP platform."

Instead:

```text
Soulverse Core Infrastructure
          +
UNTP Compatibility / Conformance Layer
          =
UNTP-compatible Soulverse implementation
```

This keeps Soulverse's proprietary capabilities independent while allowing it to conform to an open standard.

---

## 4. What We Propose to UNTP

### Proposal A — Become a UNTP Software Implementer

Soulverse can implement the relevant UNTP specifications and register its software once it satisfies the required conformance process.

**Positioning:**

> Soulverse provides trust infrastructure for organisations implementing UNTP-compatible digital trust and supply-chain solutions.

This is the most immediate proposal because it is aligned with UNTP's existing software implementer ecosystem.

### Proposal B — Trust Registry / Trust Infrastructure Implementation

Explore whether the Soulverse Trust Registry can implement or extend the trust/discovery capabilities required by UNTP.

Potential capabilities:
- Trusted issuer discovery
- Participant discovery
- Trust relationships
- Governance metadata
- Credential issuer information
- Status information
- Resolution APIs
- Policy-based trust evaluation

This should be investigated as a potential differentiator.

### Proposal C — UNTP Adoption / Implementation Partner

Soulverse can help governments and enterprises adopt UNTP instead of requiring them to build the entire trust stack internally.

Potential services:
- Architecture assessment
- UNTP integration
- DID/VC integration
- Trust Registry deployment
- Existing-system integration
- Conformance testing
- Migration from proprietary trust models
- Government/enterprise implementation
- Ongoing support

This creates a services + infrastructure opportunity around the open standard.

### Proposal D — Technical / Ecosystem Contributor

Soulverse can participate in the UNTP ecosystem through:
- Working-group participation
- Technical discussions
- Public reviews
- Implementation feedback
- Conformance testing
- Open-source contributions
- Proposed extensions where there is a genuine industry need

The objective should be to contribute practical implementation knowledge while learning where the standard is heading.

---

## 5. What We Should NOT Propose

### Do not position Soulverse as a competing standard

UNTP is the interoperability standard. Creating a parallel proprietary supply-chain trust standard would reduce the value of participating in the ecosystem.

### Do not claim UNTP adoption is guaranteed

UNTP has strong institutional backing, but future market adoption still needs validation.

### Do not claim current Soulverse components are already UNTP compliant

Compatibility must be demonstrated through a detailed technical gap analysis and conformance testing.

### Do not rebuild the Soulverse stack solely for UNTP

Prefer adapters, mappings and standards-compliance layers wherever technically sound.

---

## 6. Soulverse vs UNTP: Role Separation

| Layer | UNTP role | Soulverse proposed role |
|---|---|---|
| Standard | Define interoperability | Implement/support |
| Governance | Define framework/process | Participate and comply |
| DID | Define interoperability expectations | Provide DID infrastructure |
| VC | Define credential patterns | Issue/verify credentials |
| Trust | Define trust model | Provide Trust Registry/Protocol |
| Discovery | Define mechanisms | Provide resolver/registry implementation where applicable |
| Conformance | Define requirements/tests | Pass tests and maintain conformance |
| Applications | Enable interoperability | Build government/enterprise products |
| Integration | Define common language | Integrate with existing systems |
| Adoption | Build ecosystem | Help customers implement |

---

## 7. Technical Gap Analysis We Need

Before committing to this strategy, create a requirement-by-requirement mapping:

| UNTP requirement | Soulverse today | Gap | Required change | Priority |
|---|---|---|---|---|
| DID | Existing DID infrastructure | Validate | TBD | High |
| VC | Existing VC infrastructure | Validate | TBD | High |
| Credential verification | Existing capability | Validate | TBD | High |
| Trust Registry | Existing Trust Registry | Validate architecture mapping | TBD | Very High |
| Trust Protocol | Existing Trust Protocol | Validate discovery/resolution mapping | TBD | Very High |
| Resolver | To validate | Unknown | TBD | High |
| Credential status | To validate | Unknown | TBD | High |
| Key management | Existing capability to validate | Unknown | TBD | High |
| UNTP credential types | To validate | Potential mapping work | TBD | High |
| UNTP extensions | To validate | Potential adapter work | TBD | Medium |
| Conformance testing | Not yet established | Gap | Integrate test suite | Critical |
| Software registration | Not yet established | Gap | Complete registration process | Critical |

This table should be updated from the actual Soulverse source repositories and the final UNTP 1.0 specification.

---

## 8. Business Proposition

The proposed business model has three layers.

### Layer 1 — Infrastructure

Soulverse provides reusable trust infrastructure:
- Trust Registry
- Trust Protocol
- DID infrastructure
- VC infrastructure
- Verification
- Discovery/resolution

### Layer 2 — Products

Build domain-specific applications for:
- Government
- Supply chains
- Certification
- Compliance
- Sustainability
- Digital product passports
- Traceability

### Layer 3 — Implementation Services

Help organisations adopt UNTP:
- Consulting
- Integration
- Deployment
- Customisation
- Conformance
- Support

The strategic advantage is that the open standard can create demand for implementation without Soulverse having to control the standard itself.

---

## 9. Key Strategic Hypothesis

> **If UNTP becomes widely adopted, organisations will need interoperable trust infrastructure and implementation expertise. Soulverse can position its Trust Registry, Trust Protocol and credential infrastructure as a reusable implementation layer for that adoption.**

This hypothesis has three assumptions that must be tested:

1. **Technical:** Soulverse can achieve UNTP conformance without excessive architectural change.
2. **Market:** Governments and enterprises will actually adopt UNTP at meaningful scale.
3. **Differentiation:** Soulverse's trust infrastructure provides meaningful value beyond the existing UNTP implementation partners.

---

## 10. Recommended Next Steps

### Phase 1 — Technical validation

- Map Soulverse architecture to UNTP 1.0.
- Validate Trust Registry alignment.
- Validate Trust Protocol alignment.
- Test DID/VC interoperability.
- Identify conformance gaps.

### Phase 2 — Competitive analysis

Compare Soulverse with existing UNTP implementation partners, particularly companies offering SSI, trust registries, identity and VC infrastructure.

### Phase 3 — Ecosystem engagement

- Participate in UNTP technical discussions.
- Review the implementation process.
- Engage with relevant working groups.
- Understand implementation registration requirements.
- Identify opportunities for technical contribution.

### Phase 4 — Proof of concept

Build a small UNTP-compatible implementation using the existing Soulverse stack.

A successful POC should demonstrate:

```text
Issuer
  -> Soulverse DID
  -> UNTP-compatible VC
  -> Soulverse Trust Registry
  -> Resolver / discovery
  -> Independent verifier
  -> Trust + credential verification
```

### Phase 5 — Commercial proposition

Use the POC to define a repeatable government/enterprise implementation package.

---

## 11. Final Positioning

The recommended external positioning is:

> **Soulverse is an implementation and trust-infrastructure partner for organisations adopting open digital trust standards such as UNTP. We provide the identity, credential, trust registry, verification and integration infrastructure needed to turn those standards into production systems.**

The objective is not to compete with UNTP. The objective is to become one of the organisations that makes UNTP usable in real-world government and enterprise environments.

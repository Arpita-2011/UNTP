# Trust, Identity, Security & Confidentiality

## Sources
- Requirements: https://untp.unece.org/docs/about/Requirements/
- Architecture: https://untp.unece.org/docs/specification/Architecture/
- Verifiable Credentials: https://untp.unece.org/docs/specification/VerifiableCredentials/
- Decentralised Access Control: https://untp.unece.org/docs/specification/DecentralisedAccessControl/
- Core Vocabulary: https://untp.unece.org/docs/specification/CoreVocabulary/

## Core model
UNTP uses verifiable, identity-linked credentials to create a distributed transparency graph.

Important credential types include:
- Digital Product Passport (DPP)
- Digital Facility Record (DFR)
- Digital Conformity Credential (DCC)
- Digital Traceability Event (DTE)
- Digital Identity Anchor (DIA)

## Identity
- UNTP uses W3C DIDs for issuer identification.
- Digital Identity Anchors link a DID to an authoritative identity such as a government business registration.
- The identity layer is intended to establish stronger confidence in who controls an issuer identifier.

## Security and confidentiality
UNTP requires mechanisms for:
- balancing transparency and confidentiality;
- layered data protection;
- selective redaction;
- credential revocation;
- long-term availability;
- cryptographic agility;
- key discovery, protection and rotation.

## Access control
The current access-control design describes multiple patterns, including public access, unguessable identifiers, encryption, shared secrets, federated authentication and decentralised authentication.

## Important architecture distinction
UNTP is not wallet-dependent. Its primary supply-chain model is resolver-based discovery: credentials are published by issuers and discovered by verifiers using identifiers and resolvers. Wallets remain optional for suitable use cases.

## Soulverse relevance
This is the area to compare directly against Soulverse's Trust Registry, Trust Protocol, DID/VC infrastructure, resolver/discovery capabilities, key management, credential status and access-control architecture.

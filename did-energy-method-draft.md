# Status
Version: draft 0.1
# Introduction
This is a draft document. The purpose of this document is to propose a [w3c did](https://w3c-ccg.github.io/did-spec/) compliant DID method tailored for energy sector related use cases. This draft outlines a DID method specifically designed to address the unique challenges and requirements of energy-related use cases, such as Decentralised Energy Resources (DER) integrations, smart grid management, electic mobility and traceability of environmental attributes. By leveraging the principles of decentralization, privacy, and interoperability, this method aims to enhance trust and efficiency within the energy ecosystem.

# did:energy Method Specification
Energy ID DID - will be an implementation of the [iden3 protocol](https://docs.iden3.io/protocol/spec/). The iden3 protocol is compatible with any Ethereum Virtual Machine (EVM) based blockchains.

## Method Specific Identifier
The Energy DID method will be identified by the `energy` scheme.


```
energy-did = "did:energy:" energy-id-specific-idstring
energy-id-specific-idstring = energy-id-blockchain ":" energy-id-identifier
energy-id-blockchain = "ewc" / "eth" / "pol"
energy-id-identifier = 42*43 BASE58
```

### Example

A valid Energy DID:

On EnergyWeb mainnet - ```did:energy:ewc:<identity-type-specific-identifier>```\
On Ethereum mainnet  - ```did:energy:eth:<identity-type-specific-identifier>```\
On Polygon mainnet   - ```did:energy:pol:<identity-type-specific-identifier>```


## DID Document
```json
{
        "@context": [
            "https://www.w3.org/ns/did/v1",
            "https://schema.iden3.io/core/jsonld/auth.jsonld"
        ],
        "id": "did:energy:<network>:<identifier>",
        "authentication": [],
        "verificationMethod":[],
        "assertionMethod":[],
        "keyAgreement":[],
        "capabilityInvocation":[],
        "capabilityDelegation":[],
        "service":[],
        "publicKey":[]

    }
```
## JSON-LD Context

The energy did method uses additional JSON-LD types.

The JSON-LD vocabulary is stored in:

```
https://schema.iden3.io/core/jsonld/auth.jsonld
```

Context contains `AuthBJJCredential`(Operational key)  and `Iden3StateInfo2023` types.

```
https://schema.iden3.io/core/jsonld/iden3proofs.jsonld
```

Context contains `Iden3SparseMerkleTreeProof` and `BJJSignature2021` proofs types used with energy id.

## Type of identities
## CRUD Operations

### Create
### Update
### Resolve 
### Revoke



## Privacy Considerations

### Safeguarding Personally Identifiable Information (PII)
To protect privacy, PII should never be exposed or referenced within did:energy DID documents. Any sensitive information must remain securely off-chain to prevent unauthorized access or disclosure.

### Disclosures
References and historical changes within DID Documents are stored on the blockchain. It is important for identity owners to recognize that on-chain data is publicly accessible unless it is hashed or encrypted, and should take appropriate precautions.

### Privacy Considerations in W3C DID Specification
The did:energy method adheres to the privacy principles outlined in the W3C DID Specification, ensuring that privacy is maintained throughout the lifecycle of the DID.
- The Privacy Considerations section of the DID Implementation Guide: [https://w3c.github.io/did-imp-guide/#privacy-considerations](https://w3c.github.io/did-imp-guide/#privacy-considerations).
- The Privacy Considerations section of the Decentralized Identifiers (DIDs) (DID-CORE) specification: [https://www.w3.org/TR/did-core/#privacy-considerations](https://www.w3.org/TR/did-core/#privacy-considerations).
- The Privacy Considerations section of the DID Implementation Guide: [https://w3c.github.io/did-imp-guide/#privacy-considerations](https://w3c.github.io/did-imp-guide/#privacy-considerations).
- The Privacy Considerations section of the Decentralized Identifiers (DIDs) (DID-CORE) specification: [https://www.w3.org/TR/did-core/#privacy-considerations](https://www.w3.org/TR/did-core/#privacy-considerations).

## Security Considerations
### Key Management and Rotation
It is crucial to keep private keys secure and protected. In the event that a private key is compromised, the did:energy method supports key rotation, allowing for the replacement of the compromised key with a new one, ensuring continued security of the DID.

### Mitigating Eavesdropping Attacks
To prevent eavesdropping attacks, it is essential to use secure communication channels, such as those secured with TLS or equivalent protocols. Since our DID method employs a message-based communication protocol that does not have native encryption, securing the transmission of sensitive information is critical to maintaining confidentiality.

### Preventing Data Forgery
The did:energy method safeguards against data forgery and falsification by implementing Digital Signatures, Merkle Tree Proofs, and Zero Knowledge Proofs (ZKPs). These cryptographic techniques ensure that only the rightful identity owner can issue and present credentials, protecting the integrity and authenticity of the data within the DID system.

## Reference Implementation
## References

[Decentralized Identifiers (DIDs)](https://www.w3.org/TR/did-core/)\
[Verifiable Credentials Data Model](https://www.w3.org/TR/vc-data-model)
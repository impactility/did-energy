# Status
Version: draft 0.1
# Introduction
This is a draft document. The purpose of this document is to propose a [w3c did](https://w3c-ccg.github.io/did-spec/) compliant DID method tailored for energy sector related use cases. This draft outlines a DID method specifically designed to address the unique challenges and requirements of energy-related use cases, such as Decentralised Energy Resources (DER) integrations, smart grid management, electic mobility and traceability of environmental attributes. By leveraging the principles of decentralization, privacy, and interoperability, this method aims to enhance trust and efficiency within the energy ecosystem.

# did:energy Method Specification
Energy ID DID - will be an implementation of the [iden3 protocol](https://docs.iden3.io/protocol/spec/). The iden3 protocol is compatible with any Ethereum Virtual Machine (EVM) based blockchains.

## Method Specific Identifier
The Energy DID method will be identified by the `energy` scheme.

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
## Type of identities
## CRUD Operations

### Create
### Update
### Resolve 
### Revoke

## Use Cases
###
Decentralised Energy Resources(DER)
###
Electic Mobility

## Security and Privacy Considerations
- The Privacy Considerations section of the DID Implementation Guide: [https://w3c.github.io/did-imp-guide/#privacy-considerations](https://w3c.github.io/did-imp-guide/#privacy-considerations).
- The Privacy Considerations section of the Decentralized Identifiers (DIDs) (DID-CORE) specification: [https://www.w3.org/TR/did-core/#privacy-considerations](https://www.w3.org/TR/did-core/#privacy-considerations).
- The Privacy Considerations section of the DID Implementation Guide: [https://w3c.github.io/did-imp-guide/#privacy-considerations](https://w3c.github.io/did-imp-guide/#privacy-considerations).
- The Privacy Considerations section of the Decentralized Identifiers (DIDs) (DID-CORE) specification: [https://www.w3.org/TR/did-core/#privacy-considerations](https://www.w3.org/TR/did-core/#privacy-considerations).


## References

[Decentralized Identifiers (DIDs)](https://www.w3.org/TR/did-core/)\
[Verifiable Credentials Data Model](https://www.w3.org/TR/vc-data-model)
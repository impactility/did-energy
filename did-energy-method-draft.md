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
## Type of identities
## CRUD Operations

### Create
### Update
### Resolve 
### Revoke

## Use Cases
### Decentralised Energy Resources(DER)
Distributed Energy Resources (DERs), such as solar panels, wind turbines, battery storage systems, microgrids, and electric vehicles should adopt `did:energy` method. `did:energy` method ensures enhanced security, privacy, and interoperability. Unlike traditional systems that rely on centralized authorities,`did:energy` DIDs offer cryptographic security, ensuring tamper-proof and decentralised, autonomous identity management. This decentralized approach empowers DER owners, protects sensitive data through privacy-preserving features, and supports seamless integration across various platforms, enabling more resilient and scalable energy systems as the grid becomes increasingly decentralized and diverse.

### Electic Mobility
The Electric Mobility sector should adopt `did:energy` based  Decentralized Identifiers (DIDs) and Verifiable Credentials (VCs) to address the challenges of identity federation and fragmentation. Traditional identity systems in this sector are often siloed, leading to fragmented identities across different charging networks, vehicle systems, and service providers. `did:energy` DIDs provide a unified, decentralized identity solution that allows electric vehicles, charging stations, and users to securely authenticate and interact across multiple platforms. Verifiable Credentials issued to `did:energy` DIDs will enable the seamless exchange of trusted information without relying on centralized authorities, fostering interoperability, enhancing privacy, and simplifying the user experience in a rapidly expanding and interconnected mobility ecosystem.

### Digital Product Passports
The energy sector faces increasing regulatory demands for transparency, sustainability, and traceability of products throughout their lifecycle. Digital Product Passports (DPPs) are becoming essential to meet these needs, providing a comprehensive record of an energy product's origin, manufacturing process, certifications, and compliance with environmental and safety standards. `did:energy` Decentralized Identifiers (DIDs) and Verifiable Credentials (VCs) can offer a robust solution for implementing DPPs by enabling secure, decentralized, and tamper-proof identification and verification of product information. DIDs provide a unique, immutable identity for each product, while VCs store verifiable data about the product’s regulatory compliance and other key attributes. This approach not only ensures that all stakeholders, from manufacturers to regulators, can access accurate and consistent information but also simplifies the process of proving compliance with complex regulatory frameworks, ultimately supporting the sector's move towards more responsible and transparent practices.

## Security and Privacy Considerations

### Key Management

- The Privacy Considerations section of the DID Implementation Guide: [https://w3c.github.io/did-imp-guide/#privacy-considerations](https://w3c.github.io/did-imp-guide/#privacy-considerations).
- The Privacy Considerations section of the Decentralized Identifiers (DIDs) (DID-CORE) specification: [https://www.w3.org/TR/did-core/#privacy-considerations](https://www.w3.org/TR/did-core/#privacy-considerations).
- The Privacy Considerations section of the DID Implementation Guide: [https://w3c.github.io/did-imp-guide/#privacy-considerations](https://w3c.github.io/did-imp-guide/#privacy-considerations).
- The Privacy Considerations section of the Decentralized Identifiers (DIDs) (DID-CORE) specification: [https://www.w3.org/TR/did-core/#privacy-considerations](https://www.w3.org/TR/did-core/#privacy-considerations).

## Reference Implementation
## References

[Decentralized Identifiers (DIDs)](https://www.w3.org/TR/did-core/)\
[Verifiable Credentials Data Model](https://www.w3.org/TR/vc-data-model)
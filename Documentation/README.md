---
version: 0.2
Last Edit: 2023-10-13
tags: WIDE, EUDIW, DID, claims
email: bb@acurraent.com
authors: benedictvscriticus
---
# WIDE Core Library
![Group 57](https://github.com/Consortium-WIDE/wide-core/assets/104435781/b842c1f0-aa37-4079-9500-425732f286d3)

**WIDE** is short for Web3 Identity for DAOs and Education. The project was incepted in response to the 2023 #OC1 by the NGI TRUSTCHAIN consortium. **WIDE** is being developed and maintained by a consortium led by acurraent UG, coordinated by Joshua Ellul, Director of the Centre for Distributed Ledger Technologies at the University of Malta, and the technical lead Matthew Scerri .

*WIDE addresses the challenges of market fragmentation and low interoperability for decentralised identity management. WIDE seeks uses decentralised ledger technology (DLT) for secure claim verification and encryption to integrate decentralised identity functionalities with decentralised autonomous organizations (DAOs), along with introducing authorization interfaces that may be more familiar to users of legacy systems. The architecture of WIDE is modular, designed to interact within distinct operational contexts: Issuers, Holders, and Verifiers. WIDE is being developed as an open-source project under the EUPL-1.2 License, emphasising our commitment to transparency and collaborative development.*

## A Decentralised Identity Bridge

WIDE operates at the intersection of edge and cloud wallets to tackle the remaining and more challenging innovations within the decentralised identity paradigm. WIDE takes the opportunity to not only build decentralised identity bridges, but also connect governmental identity spheres with the emergent Web3 landscape.

WIDE is a direct response to the high market fragmentation and low interoperability, which originates from the identification of discrepancies between the state of the art in decentralised identity and the ARF. Thus, WIDE does not formally have a background that consists of artefacts or software code. In essence, WIDE fills the interoperability gap between eIDAS 2.0 and Web3 by developing a bridging service.

Holders, i.e. end-users, currently have to manage a number of different authentication mechanisms used by Verifiers to allow for their credentials to be verified. WIDE proposes a solution to the fragmentation of Holder claims being spread across multiple sources and multiple standards by bridging the gap between the different models. It provides the Holder with the ability to capture and store claims securely from different identity providers remotely, while linking such claims to their Web3 wallet. Furthermore, WIDE aims to provide Verifiers with the option to interact with the Holder via either OAuth or Web3 to ensure future-proofing.


## Scope of Work

WIDE brings together acurraent, a German innovation agency, the University of Malta and a technical expert in aim of creating a bridge for digital identities that will connect European trust frameworks with Web3. Today, students and recent graduates at the University of Malta already receive a digitally signed European Digital Credentials that can be uploaded to the Europass platform [EUROP]. Such credentials, however, do not empower holders to be part of the 'new work' paradigm. DAOs often value experience over university degrees — this may be due to the fact that even if DAOs are presented with such credentials, they cannot reliably verify their validity and applicability.

WIDE recognises the unnecessary complexity introduced by existing SSI applications and proposes to reshape the technology to fit better with the decentralised identity paradigm. Rather than trying to adapt existing digital identity applications to fit within technological requirements of existing decentralised technologies, aims to facilitate efficient user flows that are Web3-ready. More concretely, WIDE: (i) combines the transport protocols and personal identification data (PID) standard set laid out in the Architecture Reference Framework (ARF) [ARF]; (ii) re-configures Open Authentication (OAuth) [OAUTH] communication flows; and (iii) stores claims as data minimised attestations that are accessible to legacy and Web3 verifiers alike.

## Definitions

### Actors

#### Holders

The _Holder_ refers to the owner of the _Verifiable Credential_. They are seen as the ultimate end-users of WIDE. Holder contexts refer to code, written by either by WIDE or a 3rd party, that is executed on the Holder's machine. WIDE components residing within this context may be referred to as 'client-side' components. For WIDE components this is typically run on the Holder's browser (locally), or through applications written in technologies such as Node.js.

The Holder can be considered WIDE's end-user, and refers to the Identity Subject. The Holder will retrieve credentials from the Issuer using traditional protocols (depending on whatever the Issuer supports), but may then process these claims for Storage in WIDE.

#### Issuers

The _Issuer_ refers to the organisation or entity that issues the _Verifiable Credential_ to the _Holder_. Issuers act in the context of and are controlled by an **external** entity that issues the original claims to the subject (holder).

The Issuer does not directly interact with WIDE at any point. However, it is important to recognise its operations within the wider context of the WIDE technical architecture as the Issuer may be utilising different methods of issuing claim(s) which ultimately need to be processed by WIDE.

For the purposes of WIDE, the Issuer may either issue the verifiable credentials (VC) via an ID Wallet (such as using the _JWT-SD_, _JSON W3C VC_, _OIDC4VP_, or _SIOP_ protocols) or through more traditional OAuth mechanisms (such as Google Single Sign On).

#### Verifiers

The _Verifier_ refers to the entity, app or dApp, that requires one or more claims from the Holder, and needs to verify their authenticity. Here, web application requests claims from the Holder. Additionally this context may also utilise WIDE dApp libraries to additionally verify a claim's validity against the DLT.

#### WIDE

This is the only context under full control of WIDE. It is essentially a centralised database with encrypted claims and components that expose CRUD operations for encrypted claims.

#### Developers

 The _Developer_ is the individual or organisation that is developing the software for the _Verifier_, through the WIDE dApp library.

#### DLT

This context acts as a trustless layer for the verification of data. It will exclusively utilise appropriately salted hashes. The DLT domain is to be made up of a single smart contract that will contain a log of any claims fetched. The Log will comprise of appropriate salted hashes to prevent data leakage.

#### Relying Parties

TBD

## Systems

#### Digital Identity Bridge

WIDE balances individual interests for participation in emerging, atypical, and open networks with interests of organisations, which primarily are rooted in Web3. The digital identity bridge reconfigures rather than engineers towards an infrastructure that will abolish all others. As a result, WIDE is an enabling solution for centralised and DAOs alike.

#### Identity Proxy

TBD

#### WIDE Bridging Server

TBD

## Architecture

![WIDE_General_Architecture](https://github.com/Consortium-WIDE/wide-core/assets/104435781/ab467a05-f8be-49e9-ace2-7858f48297bd)

#### WIDE client

The WIDE Client is the main component that the Holder interacts with, in that it contains the UX/UI implementation (anticipated to be in angular.js) that the Holder interacts with.

##### Claim encryption

The Claims Processor obtains claim(s) from different sources through support of various protocols (such as OAuth or OIDC4VP), and sends the claim to the client for encryption. The encryption of the claims is carried out by interacting with the Client.

##### Claim decryption

The Claims Processer is also able to decrypt the claim. Claims may only be decrypted by the Claim(s) processor using the wallet's Private Key (through MetaMask's `eth\_decrypt` functionality).


### Verifier domain

As Verifiers are not necessarily expected to be Web 3 dApps, any claims they request are delivered to them via standardised OAuth protocols. This allows Web 2 applications to also be able to leverage the features provided by WIDE.

#### Verifier dApp library

Verifiers will be provided with a WIDE library that allows them to interact with the decentralised logging repository to independently verify the authenticity of the received claim(s).

### WIDE Server

The WIDE server platform is only concerned with handling the CRUD operations of the encrypted claims.

#### Claims storage module

The Claims Storage Module is a simple module that takes the encrypted claim and the user's public key and persists it in a permanent (centralised) storage. While a decision will be taken at a later stage (in line with the requirements of future deliverables), this may take the form of a NoSQL or flat-file database.

#### Claims deletion module

The Claims Deletion Module deals with the deletion of claim(s) data to ensure that the user always has the right to exercise their right to be forgotten under GDPR.

Since it is essential that we only delete claim(s) for authorised Holders, the Claims Deletion Module will also generate a unique message, that is signed using the Holder's public key. This Message is then decrypted by the WIDE Client and it serves to ensure that as verification that the Holder is the rightful owner of the wallet.

#### Claims fetcher module

The Claims Fetcher Module deals with retrieving claims from the permanent storage. Similarly to the Claims Deletion Module, this module will also generate a unique signed message to verify ownership of the Public/Private key pair.

Additionally, whenever claims are retrieved, an appropriately salted hash of the encrypted claim is logged onto a 3rd party trustless repository (such as a DLT network). This is what will allow the Verifier to independently verify the authenticity of the claim obtained by the user.

#### Claims processor module

The Claims Processor module manages claim(s) on the client side. It is solely responsible with reading (and where necessary decoding) claims from the Holder's authorised OAuth and/or Identity Wallet.

## Process Flows

The WIDE Library is concerned with 5 main process flows related to credential management:

- Storing Claims
- Viewing Claims
- Removing Claims
- Retrieving Claims

## Features

1. UI-based data export
2. Privacy-preserving cloud storage
3. Web3-based open authentication
4. Simple data sharing
5. Reliable identity storage
6. Native EVM-support
7. Portable and trustworthy data attestations
8. Simple UI-based identity card management

## Functionalities

The WIDE digital identity bridge enables users to export identity data from wallets of closed identity networks and use the identity data with their Ethereum-compliant key pairs throughout full identity lifecycles. All data is protected through client-side encryption and presented to relying parties by the wallet user, employing a reversed Open Identity Connect [OIDC] flow. In short, WIDE provides export, persistance, as well as encryption -, storage -, and presentation capabilities for long-lived any-wise identifiers in storage-scarce Web3 wallets. 

In this context, bridging refers to the privacy preserving, but server-based remote storage of encrypted claim and the assured availability for identity presentations by holders on demand over Web2 flows. When the wallet presents claims, it requests them from the WIDE bridging server. The wallet then acts as a proxy, waits for the WIDE server to return data, the wallet then decrypts the data and forwards it to the relying party. The relying party can verify that a dataset was hashed upon upload to the WIDE bridging server and did not change.

For this reason, WIDE logs entries over record uploads on Alastria Besu to enable trust assertions of verifiers (relying parties), because WIDE cannot attest to the validity or correctness of the data. Thus, bridging means that WIDE only attests to having seen a random but unique string at a given time from a specific address that signed the data. 

Its strength, however, is that WIDE covers the gap of Web3-based Web2-logins. There are many solutions that allow Web2 onboarding to Web3, but only few have used Web3 technologies for Web2 authentication flows. For this reason, WIDE reverse implements Web2 to Web3 onboarding solutions in dataflows optimised for verifiers.

WIDE uses the rich context of data from the European Digital Identity Wallet in the form of W3C verifiable credentials v.2 [W3CVC]. It associates and encrypts the contained claims using Ethereum-compliant key pairs and over secp256k curves with ECDSA signatures. The user keeps an overview in the cache of the wallet solution, but uploads the signed and encrypted data including a hash to the WIDE server over an authenticated session.

The bridging server then hashes the hash and stores it on chain. When a user requests the data from WIDE, assuming online-only use cases, the user authenticates using Log-in-with-Ethereum and requests structured, but encrypted claims. They then decrypt it on client side and act first as identity subject against a relying party to then return the requested information by the identity provider through acting as an identity provider.

### Functionality 1 - Storing claims

When the Holder obtains a Verifiable Credential from an Issuer, the Holder may present a Verifiable Presentation to WIDE composed of claims they want to store. The Holder is asked to encrypt the Verifiable Credentials they would like to store on WIDE using their Public Key (before any data is transmitted to the server) so that this data may only be decrypted on the client-side by the user using their own private key. Prior to encryption, the Verifiable Credential will be wrapped up in a payload that is appropriately timestamped and nonce'd.

The Holder is then asked to authenticate against a Web3 wallet (e.g. such as MetaMask) by signing a unique message, and presenting their public key to WIDE. A Hash of the Verifiable Credential payload (i.e. timestamped and nonce'd) is also stored to serve as a signature of the data we processed and 'extracted' the claims from.

The encrypted payloads are then stored on the WIDE database (DB), which is a centralised repository of encrypted claim(s).

### Functionality 2 - Viewing claims

Once the Holder authenticates via their Web3 Wallet, they will be able to obtain a list of previously stored encrypted claims. The claims may be decrypted locally on the client-side (potentially using MetaMask's `eth\_decrypt`), allowing for the user to identify what they claims pertain to.

### Functionality 3 - Removing claims

When removing a claim, the user is asked to authenticate their Web3 wallet through the signing of a unique message. They are then presented with a list of stored claims, which are decrypted on the client-side. The Holder may then select which of these claims are to be removed from WIDE, with all associated data being deleted accordingly.

### Functionality 4 - Retrieving claims

When a Verifier needs to obtain claims from a Holder, the Verifier may issue a request to the Holder via the WIDE Client module with the required credentials. The WIDE Client, on the Holder's approval, will retrieve the claims from the WIDE DB, and decrypt the claim(s) on the WIDE Client side (i.e the Holder), before sending them to the Verifier.

## References

[ARF] European Commission, 'The European Digital Identity Wallet Architecture and Reference Framework | Shaping Europe's digital future', Feb. 10, 2023. Accessed: Aug. 20, 2023. Available: https://digital-strategy.ec.europa.eu/en/library/european-digital-identity-wallet-architecture-and-reference-framework.

[EUROP] University of Malta, 'European Digital Credentials for Graduates'. Dec. 09, 2021. Accessed: Aug. 20, 2023. https://www.um.edu.mt/newspoint/news/2021/12/european-digital-credentials-for-graduates.

[OAUTH] D. Hardt, 'The OAuth 2.0 Authorization Framework', Internet Engineering Task Force, Request for Comments RFC 6749, Oct. 2012. doi: 10.17487/RFC6749.

[OIDC] O. Terbu, T. Lodderstedt, K. Yasuda, and T. Looker, 'OpenID for Verifiable Presentations - draft 18'. Apr. 21, 2023. Accessed: Aug. 20, 2023. [Online]. Available: https://openid.net/specs/openid-4-verifiable-presentations-1\_0.html.

[W3CVC] M. Sporny, O. Steele, M. B. Jones, G. Cohen, and O. Terbu, 'Verifiable Credentials Data Model v2.0'. Accessed: Aug. 29, 2023. [Online]. Available: https://www.w3.org/TR/vc-data-model-2.0/.

## Disclaimer

This research and development project is part of the **NGI TRUSTCHAIN #OC1**. All software code is provided as is and without warranty under permissible EUPL 1.2 licencing. This project is funded by a cascade funding partner through a Horizon Europe Grant under the TrustChain grant with grant agreement number: [101093274](https://doi.org/10.3030/101093274).

![NGI EU Funding](https://github.com/Consortium-WIDE/wide-core/assets/104435781/a4188f37-5e59-4100-a889-e6a6a18f7dbb)


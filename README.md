---
version: 0.1
Last Edit: 2023-09-22
tags: WIDE, EUDIW, DID, claims
email: bb@acurraent.com
authors: benedictvscriticus
---

![Group 57](https://github.com/Consortium-WIDE/wide-core/assets/104435781/b842c1f0-aa37-4079-9500-425732f286d3)

# WIDE Core Library

**WIDE** is short for Web3 Identity for DAOs and Education. The project was incepted in response to the 2023 #OC1 by the NGI TRUSTCHAIN consortium. **WIDE** is being developed and maintained by a consortium led by acurraent UG, coordinated by Joshua Ellul, Director of the Centre for Distributed Ledger Technologies at the University of Malta, and the technical lead Matthew Scerri .

For enabling Web3 identities to be used by DAOs and in education, **WIDE** enables users to export their 

## Executive Summary

## A Decentralised Identity Bridge

## Scope of Work

## Definitions

### Digital Identity Bridge

### Verifier

### Relying Party

### Identity Proxy

### WIDE Bridging Server

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



---
Finally, the relying party can integrate a WIDE claim validator to check Alastria for logs.

algorithms and in combination with SHA-256 compliant identifiers over 

---

  encrypt them, keep decentralised identity wallet that usesEuropean Digital Identity in the form of verifiable credentials according to the W3C verifiable credential data model v.2 [W3CVC] associate and ecnrypt the contained claims using Ethereum-compliant key pairs of the secp256k

## Architecture

### Overview

![WIDE_General_Architecture](https://github.com/Consortium-WIDE/wide-core/assets/104435781/ab467a05-f8be-49e9-ace2-7858f48297bd)


### Components

## Technologies


## Application & Use Cases

## Disclaimer

This research and development project is part of the **NGI TRUSTCHAIN #OC1**. All software code is provided as is and without warranty under permissible EUPL 1.2 licencing. This project is funded by a cascade funding partner through a European Horizon Grant under the ONTOCHAIN grant with grant agreement number: 957338.

![NGI EU Funding](https://github.com/Consortium-WIDE/wide-core/assets/104435781/a4188f37-5e59-4100-a889-e6a6a18f7dbb)


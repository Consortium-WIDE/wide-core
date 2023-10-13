---
version: 0.1
Last Edit: 2023-10-14
tags: WIDE, agile, claims, specification
email: bb@acurraent.com
authors: benedictvscriticus
---
# User Stories WIDE Core

The 'Core' user stories cover the fundamental and essential features that make up WIDE's framework. These stories describe the platform's default features, which are available to all users to ensure a consistent and reliable experience. "Core" user stories are grouped according to the functionalities they fulfil.

### Epic 1 - Claim Storage

- As a holder, I want to be able to present my credentials to the WIDE wallet.
- As a holder, I want to be able to connect my Google Workspace account (OAuth) and export my data, such as my name and email address, into WIDE.
- As a holder, I want to be able to encrypt the claims I export from OAuth providers using my MetaMask wallet before uploading the claims to WIDE.
- As a holder, I want to store my claims both as predicates and plain text on WIDE (both predicates and plain text claims are still encrypted when stored on WIDE).
- As a holder, I want to be able to choose which claims are encrypted before uploading them to WIDE.
- As a holder, I want to be able to choose which claims I want to import from the claims contained in the credentials I present.
- As a holder, I do not want the WIDE admins to know any details of my claims at any time.

### Epic 2 - Claim Management

- As a holder, I want to use a user interface to see an overview of my claims that are uploaded on WIDE.
- As a holder, I want to be able to revoke my consent for WIDE to store my credentials using a dedicated user interface.
- As a holder, I want to be able to select claims to associate them with my public WIDE profile.
- As a holder, I want to be able to access all functionalities I can use in WIDE wallet through a web page.
- As a holder, I want to be able to access and see which claims were presented to which verifier, even after the presentation.
- As a holder, I want to make sure that only I can download and manage my claims.
- As a holder, I want seamless integration with my Web 3 wallet to verify the authenticity of my credentials.

### Epic 3 - Claim Presentation

- As a verifier, I want to be able to suggest to the holder which claims I require.
- As a holder, I want to be able to propose claims satisfying the requirements of the verifier, which were not explicitly requested.
- As a verifier, I want to be able to request updated claims
- As a holder, I want any encrypted claims to be decrypted on my client before sending them to the verifier.
- As a holder, I want to be able to see who is requesting the data.
- As a holder, I want to make sure that only I can decrypt and present my claims.
- As a verifier, I want to be able to independently verify the authenticity of the claims I receive from a holder.
- As a verifier, I want to be able to independently verify that any claims I retain are still valid.
- As a verifier, I want to be able to retrieve claims from the holder via the OAuth standard.

### Epic 4 - Wide Administration

- As a WIDE Admin, I want to remove all data of a holder, who has requested to delete their data from WIDE.
- As a WIDE Admin, I want to identify holders by their public key.
- As a WIDE Admin, I want to verify that the holders have ownership of the associated private keys.
- As a WIDE Admin, I want to ensure that any claims-related data I have access to is fully encrypted at all times.
- As a WIDE Admin, I want to ensure that any storage of claims is aligned to the GDPR.

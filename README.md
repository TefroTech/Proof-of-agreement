
# Secure Agreement System with Improved Lamport Signatures for DAOs and Peer-to-Peer Contracts

## Table of Contents
1. [Project Overview](#project-overview)
    - [Overview](#overview)
    - [Key Features](#key-features)
    - [Process](#process)
        - [1. Creating and Signing an Agreement](#1-creating-and-signing-an-agreement)
        - [2. Verifying an Agreement](#2-verifying-an-agreement)
    - [Use Case: DAO Workflow](#use-case-dao-workflow)
    - [Conclusion](#conclusion)
2. [Running the Software Locally](#running-the-software-locally)
    - [Prerequisites](#prerequisites)
    - [Setup Steps](#setup-steps)

## Project Overview

### Overview

This project provides a decentralized system for creating, signing, and verifying agreements using cryptographically secure Lamport signatures. The system is designed to be used within Decentralized Autonomous Organizations (DAOs) and P2P parties to ensure transparency, security, and immutability of agreements. Agreements are stored on the blockchain, making them tamper-proof and publicly verifiable.

### Key Features

- **Deterministic Key Generation**: Generates private keys deterministically using the user's internet identity and agreement content, ensuring unique keys for each agreement.
- **Lamport Signatures**: Uses Lamport one-time signatures for high security and resistance to quantum attacks.
- **Blockchain Storage**: Stores agreements and their signatures on the blockchain, providing transparency and immutability.
- **Multi-Signature Support**: Enables collective decision-making within DAOs by supporting multi-signature schemes.
- **User-Friendly Interface**: Offers simplified interfaces for signing and verifying agreements.

### Process

#### 1. Creating and Signing an Agreement

- **Agreement Creation**: Two parties create an agreement with specific content.
- **Private Key Generation**: Private keys are deterministically generated for each party based on their internet identity and the agreement content.
- **Public Key Generation**: Public keys are derived from the private keys using the Lamport signature scheme.
- **Signing**: Each party uses their private key to sign the agreement content, generating unique signatures.
- **Embedding Signatures**: The signatures and public keys are embedded in the agreement document.
- **Blockchain Storage**: The signed agreement, along with the signatures and public keys, is stored on the blockchain.

#### 2. Verifying an Agreement

- **Retrieve Agreement**: The agreement is retrieved from the blockchain, including its content, signatures, and public keys.
- **Extract Data**: Extract the signatures, public keys, and original agreement content.
- **Signature Verification**: Verify the signatures using the extracted public keys against the agreement content. Ensure all parts of the signatures match the corresponding parts of the public keys. This is done automatically through our verification module.

### Use Case: DAO Workflow

1. **Proposal Creation**: A DAO member creates a proposal and generates a private key deterministically based on their identity and the proposal content. The member signs the proposal and submits it to the DAO.
2. **Submission and Voting**: The proposal is stored on the blockchain. DAO members are notified and can review the proposal. Members vote on the proposal by signing it with their keys.
3. **Threshold Verification**: Once the proposal receives enough votes (signatures), the signatures are verified. If the required threshold of valid signatures is met, the proposal is approved.
4. **Execution**: Upon approval, the proposal triggers a smart contract that executes the agreed-upon actions, such as fund transfers or project initiations.

### Conclusion

This system offers a robust and secure method for creating, signing, and verifying agreements within DAOs. By leveraging the strengths of Lamport signatures and blockchain technology, it ensures transparency, security, and immutability, making it an ideal solution for decentralized governance and decision-making.

## Running the Software Locally

### Prerequisites

- Make sure you have Rust installed. This is tested on rustc 1.75.0 (82e1608df 2023-12-21).
- Make sure you have DFX installed. It's tested on version 0.19.0.
- Make sure you have Node.js installed.

### Setup Steps

1. Clone the repository.
2. In the root directory, run the command:
    ```sh
    npm run local
    ```
3. Go to the URL provided in the terminal output to interact with the canister smart contracts through your browser.


### More ideas

   NFTs for Contract Ownership: When a contract is signed, mint a unique NFT (non-fungible token) representing that contract. The NFT can be stored in the parties’ wallets, serving as proof of ownership. Any attempt to steal the contract would involve stealing the associated NFT as well.

Secure Identity Verification: Your Proof of Identity protocol is crucial. Consider integrating biometric authentication (such as fingerprint or facial recognition) for identity verification. This adds an extra layer of confidence in the parties’ identities.
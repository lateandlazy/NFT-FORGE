# NFT FORGE
### Blockchain Identity NFT Manager

NFT Forge is a decentralized identity management system built on Ethereum that allows users to mint NFTs representing identity data, securely transfer ownership, and recover lost assets using a guardian-based recovery system.

The project demonstrates how blockchain, smart contracts, and Web3 wallets can be used to build a secure digital identity infrastructure.

It is deployed on the **Sepolia Ethereum Testnet** and interacts with the blockchain through **MetaMask and Ethers.js**.

---

# Project Overview

NFT Forge enables users to:

- Mint NFTs linked to identity hashes
- Verify NFT ownership
- Transfer NFTs securely with time-locked confirmation
- Assign guardians to protect identity assets
- Recover NFTs through a guardian approval system

This project simulates a decentralized identity wallet where NFTs act as proof of identity ownership.

---

# Key Features

## Identity NFT Minting

The contract allows minting of NFTs associated with a **wallet address and identity hash (bytes32)**.

- Only authorized users can mint NFTs
- Each NFT represents a unique identity record stored on-chain

Example data stored:

Wallet Address  
Identity Hash  
Token ID  

---

## Ownership Verification

Users can verify:

- NFT owner
- Associated identity hash
- Total NFT supply

Functions used:

ownerOf()  
getIdentity()  
totalSupply()  

---

## Secure NFT Transfer System

NFT Forge implements a **time-locked transfer mechanism**.

### Transfer Process

1. Request transfer  
2. Wait for security delay (5 minutes)  
3. Confirm transfer  

This protects users from accidental or malicious transfers.

Smart contract functions:

requestTransfer()  
confirmTransfer()  
cancelTransfer()  
getTransferRequest()  

---

## Guardian Protection System

Each NFT owner can assign up to **3 guardians**.

Guardians act as trusted entities who can help recover the NFT if the owner loses wallet access.

Functions:

addGuardian()  
removeGuardian()  
getGuardians()  

---

## NFT Recovery Mechanism

If the original owner loses access to their wallet, guardians can initiate a recovery process.

### Recovery Logic

- Recovery initiated for new owner
- Guardians approve recovery
- When **2 of 3 guardians approve**, ownership is transferred automatically

Functions used:

initiateRecovery()  
approveRecovery()  
cancelRecovery()  
getRecoveryStatus()  

---

# Technology Stack

### Blockchain
- Solidity
- OpenZeppelin ERC-721

### Development Environment
- Remix Ethereum IDE

### Frontend
- HTML
- CSS
- JavaScript
- Ethers.js

### Wallet Integration
- MetaMask

### Network
- Ethereum Sepolia Testnet

---

# Smart Contract Interaction

The frontend connects to the deployed smart contract using **ethers.js**.

Example connection:

provider = new ethers.BrowserProvider(window.ethereum);  
signer   = await provider.getSigner();  
contract = new ethers.Contract(CONTRACT_ADDRESS, ABI, signer);  

Users interact with the contract via MetaMask transactions.

---

# System Architecture

User  
│  
│ MetaMask Wallet  
▼  
Frontend (HTML + JS + Ethers.js)  
│  
│ Web3 RPC Calls  
▼  
Ethereum Sepolia Network  
│  
▼  
NFT Forge Smart Contract (Solidity)  
│  
├── NFT Minting  
├── Transfer Requests  
├── Guardian System  
└── Recovery Mechanism  

---

# User Interface Modules

The frontend interface contains multiple modules:

### Wallet Connection
Connect MetaMask and switch automatically to the Sepolia network.

### NFT Mint Panel
Mint new identity NFTs.

### Owner Verification
Check owner and identity information.

### Transfer Manager
Request, confirm, or cancel NFT transfers.

### Guardian Manager
Add or remove guardians.

### Recovery Panel
Initiate and approve recovery requests.

### Transaction Log
Displays real-time blockchain activity.

---

# Example Workflow

## Mint NFT

1. Connect MetaMask
2. Enter wallet address
3. Enter identity hash
4. Click **Mint NFT**

Transaction is executed on the Sepolia network.

---

## Transfer NFT

1. Request transfer
2. Wait security delay
3. Confirm transfer

---

## Recover NFT

1. Initiate recovery
2. Guardians approve
3. Ownership transferred after approval threshold

---

# Security Concepts Demonstrated

NFT Forge demonstrates multiple blockchain security concepts:

- Time-locked transfers
- Multi-party approval
- Guardian based recovery
- Immutable identity storage
- Decentralized ownership verification

These mechanisms help simulate a secure Web3 identity framework.

---

# Installation & Usage

## Clone Repository

git clone https://github.com/yourusername/nft-forge.git

---

## Deploy Smart Contract

Open **Remix IDE**

- Compile Solidity contract
- Deploy using **Injected Provider (MetaMask)**
- Select **Sepolia Network**

---

## Update Contract Address

In the frontend code replace:

const CONTRACT_ADDRESS = "YOUR_DEPLOYED_CONTRACT_ADDRESS";

---

## Run Frontend

Simply open:

index.html

in your browser.

---

## Connect Wallet

Click **CONNECT METAMASK**

MetaMask will automatically switch to the Sepolia network.

---

# Future Improvements

- IPFS storage for identity data
- ZK proofs for private identity verification
- DAO based guardian management
- Mobile wallet compatibility
- Multi-chain support
- Identity metadata standards (DID)

---

# Real World Applications

NFT Forge can be extended to support:

- Decentralized digital identity systems
- Academic credential verification
- Medical record ownership
- Web3 login authentication
- Secure asset recovery wallets

---

# Author

Developed as a **Blockchain Security and Identity Management Project** using Solidity and Web3 technologies.



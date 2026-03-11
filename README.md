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

## 1. Identity NFT Minting

The contract allows minting of NFTs associated with a **wallet address and identity hash (bytes32)**.

- Only authorized users can mint NFTs
- Each NFT represents a unique identity record stored on-chain

Example data stored:


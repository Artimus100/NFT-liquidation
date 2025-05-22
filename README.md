# 🧾 NFT Liquidation Protocol (Solana + Anchor)

This project is a basic implementation of an **NFT Liquidation Smart Contract** built using [Anchor](https://project-serum.github.io/anchor/) on the Solana blockchain. It enables users to **deposit NFTs as collateral** and **swap them for fungible tokens**, laying the foundation for NFT-backed DeFi use cases like lending, liquidation, and pawnshop-like protocols.

---

## 📦 Features

- 🔐 **NFT Collateralization**  
  Users can deposit NFTs into a secure PDA-managed vault.

- 🔄 **NFT-to-Token Swap**  
  Owners can swap their deposited NFT for SPL tokens through a trustless smart contract mechanism.

- 🧾 **Deposit Tracking**  
  All NFT deposits are linked with an account storing metadata (owner, mint, vault details, etc.).

- ✅ **Ownership Verification**  
  Validates that only the rightful NFT owner can deposit or withdraw assets.

---

## ⚙️ Smart Contract Functions

### `initialize_deposit_info`

Initializes a `DepositInfo` account to track NFT collateral data.

### `deposit_nft(nft_mint: Pubkey)`

- Verifies NFT ownership
- Transfers the NFT to the program vault (PDA)
- Stores metadata in the `DepositInfo` account

### `swap_nft_for_tokens(amount: u64)`

- Verifies the caller is the original NFT owner
- Transfers specified amount of tokens to the user’s account
- Simulates liquidation or buy-back scenario

---

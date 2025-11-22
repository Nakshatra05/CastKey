# **CastKey**

CastKey lets you mint and redeem **one-time posting keys** for Farcaster.
Each key is an NFT on **Celo**, and all validation, policy checking, and signature generation happen securely inside an **Oasis ROFL TEE**.
Redeemable directly through a **Farcaster MiniApp**.

**One key → one cast → instant burn.**

---

## **Features**

* Mint one-time posting keys as NFTs on Celo
* Store and enforce key rules inside an Oasis TEE
* Validate cast text through an LLM running in the TEE
* Generate Farcaster signer signatures securely
* Redeem keys inside a Farcaster MiniApp
* Auto-burn NFT after successful cast

---

## **Architecture**

* **Celo Smart Contracts**

  * ERC721 CastKey NFT
  * Registry for key status and attestations

* **Oasis ROFL Worker**

  * Stores key metadata privately
  * Runs LLM-based policy checks
  * Produces Farcaster signer signatures
  * Marks keys as used

* **Farcaster MiniApp**

  * Verifies NFT ownership
  * Sends cast text to ROFL
  * Publishes cast
  * Burns the NFT

---

## **Tech Stack**

* Solidity (Celo)
* Oasis ROFL (TEE runtime)
* Next.js
* Farcaster Frames / MiniKit
* Neynar API
* wagmi / Celo Composer

---

## **Setup**

### 1. Clone

```bash
git clone https://github.com/Nakshatra05/castkey
cd castkey
```

### 2. Install

```bash
npm install
```

### 3. Deploy Contracts

```bash
npx hardhat deploy --network celo
```

### 4. Start ROFL Worker

```bash
oasis run worker ./worker/dist/index.js
```

### 5. Run MiniApp

```bash
npm run dev
```

---

## **Basic Flow**

1. Mint CastKey NFT
2. Transfer or hold
3. Open MiniApp
4. Submit cast text
5. ROFL verifies rules and signs
6. Cast publishes
7. NFT burns

---

## **License**

MIT
* MiniApp frame code
* Branding + logo options

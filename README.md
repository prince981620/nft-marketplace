# NFT Marketplace

A decentralized NFT marketplace built on the Solana blockchain using Anchor and Rust, enabling users to mint, list, buy, and delist NFTs. This project demonstrates a secure and extensible programmatic framework for on-chain NFT trading and rewards.

## Table of Contents

- [Features](#features)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
- [Program Structure](#program-structure)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- **Mint and List NFTs:** Users can mint NFTs and list them for sale on the marketplace.
- **Buy and Sell:** Buyers can purchase listed NFTs directly from the marketplace.
- **Delist NFTs:** Sellers can remove their NFTs from the marketplace at any time.
- **Marketplace Fees:** Configurable platform fee for each transaction, collected in a treasury account.
- **Rewards:** Users interacting with the platform can receive rewards.
- **Solana Native:** All tokens and accounts are SPL and Metaplex compatible.
- **Programmatic Security:** Uses Anchor framework for secure Solana smart contract development.

## Architecture

- **Solana Program (Rust):** Implements the core marketplace logic (initialize, list, purchase, delist).
- **Anchor Framework:** Provides structured account validation, events, and CPI support.
- **Metaplex Token Metadata:** Ensures NFTs are standard-compliant and verifiable.
- **SPL Token Program:** Handles token transfers and account management.

## Getting Started

### Prerequisites

- [Rust](https://www.rust-lang.org/tools/install)
- [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
- [Node.js & npm](https://nodejs.org/)
- [Anchor CLI](https://project-serum.github.io/anchor/getting-started/installation.html)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/prince981620/nft-marketplace.git
   cd nft-marketplace
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Build the Solana program:**
   ```bash
   anchor build
   ```

4. **Configure your localnet:**
   ```bash
   solana-test-validator
   # In another terminal
   anchor deploy
   ```

5. **Run tests:**
   ```bash
   anchor test
   ```

## Program Structure

### Key Instructions

- **initialize:** Sets up a new marketplace with admin, fee, treasury, and reward configuration.
- **list:** Allows a user to list their NFT for sale, transferring it to the marketplace vault.
- **purchase:** Buyer purchases an NFT, facilitating payment, fee collection, reward distribution, and NFT transfer.
- **delist:** Removes an NFT from the marketplace and returns it to the seller.

### Key Accounts

- **Marketplace:** Stores marketplace configuration (admin, fee, treasury, rewards, name).
- **Listing:** Represents a listed NFT, including price and seller info.
- **Vault:** Holds NFTs during listing.
- **Treasury:** Collects platform fees.
- **Rewards:** Distributes interaction rewards to users.

### Technologies Used

- **Solana** (Rust, Anchor)
- **@solana/web3.js** (tests, scripts)
- **@coral-xyz/anchor** (tests)
- **@metaplex-foundation/mpl-token-metadata** (NFT verification)
- **SPL Token** (token operations)

## Testing

- Tests are written using TypeScript and Anchor's Mocha framework.
- Example test: `tests/amm-nft-market-place.ts` demonstrates setup, minting, airdrop, listing, and purchasing flows.

## Contributing

PRs and Issues are welcome! Please open an issue to discuss any major changes before submitting a pull request.

1. Fork the repo.
2. Create your feature branch (`git checkout -b feature/my-feature`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature/my-feature`).
5. Open a Pull Request.

## License

This project is open source. Please include a license file for your preferred open source license.

---

**Repository:** [prince981620/nft-marketplace](https://github.com/prince981620/nft-marketplace)

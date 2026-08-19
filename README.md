# docs-examples

Code samples referenced from the [Circle](https://developers.circle.com/) and
[Arc](https://developers.arc.network/) developer documentation.

Each subdirectory is a self-contained example with its own `package.json`. Clone
the repo, change into the example you want to run, install dependencies, and
follow the instructions in that example's documentation page or local README.

## Examples

### [`app-kit-bridge-evm`](./app-kit-bridge-evm)

Browser app that bridges USDC from Ethereum Sepolia to Arc Testnet using
[App Kit](https://www.npmjs.com/package/@circle-fin/app-kit) with the viem
adapter. Connects to any EIP-6963 browser wallet (e.g., MetaMask).

Run with `npm install && npm run dev`.

### [`app-kit-bridge-solana`](./app-kit-bridge-solana)

Browser app that bridges USDC from Solana Devnet to Arc Testnet using App Kit
with both the viem and Solana adapters. Connects an EVM wallet for the
destination and a Solana wallet for the source.

Run with `npm install && npm run dev`.

### [`app-kit-send`](./app-kit-send)

Browser app that estimates and sends USDC on Arc Testnet using
[App Kit](https://www.npmjs.com/package/@circle-fin/app-kit) with the viem
adapter. Connects to any EIP-6963 browser wallet (e.g., MetaMask).

Run with `npm install && npm run dev`.

### [`app-kit-swap`](./app-kit-swap)

Browser app that estimates and swaps USDC for EURC on Arc Testnet using
[App Kit](https://www.npmjs.com/package/@circle-fin/app-kit) with the viem
adapter. Connects to any EIP-6963 browser wallet (e.g., MetaMask).

Run with `npm install && npm run dev`.

### [`app-kit-transfer-widget`](./app-kit-transfer-widget)

React app that embeds a USDC transfer widget with
[App Kit](https://www.npmjs.com/package/@circle-fin/app-kit). Supports same-chain
`send()` and crosschain `bridge()` flows for EVM and Solana browser wallets,
including estimate, review, and retry.

Run with `npm install && npm run dev`.

### [`app-kit-unified-balance`](./app-kit-unified-balance)

Browser app that deposits USDC into a unified balance from Base Sepolia and
Solana Devnet, reads the balance, and spends it on Arc Testnet using
[App Kit](https://www.npmjs.com/package/@circle-fin/app-kit) with the viem and
Solana adapters. Connects an EVM wallet and a Solana wallet.

Run with `npm install && npm run dev`.

### [`entity-secret-setup`](./entity-secret-setup)

Node.js script that generates a new entity secret, registers it with Circle,
writes the recovery file to disk, and adds `CIRCLE_ENTITY_SECRET` to `.env`.
Intended for first-time setup of
[developer-controlled wallets](https://developers.circle.com/w3s/developer-controlled-create-your-first-wallet).
See [`entity-secret-setup/README.md`](./entity-secret-setup/README.md) for
prerequisites and security notes.

## License

Apache 2.0 — see [LICENSE](./LICENSE).

## Security

To report a vulnerability, see [SECURITY.md](./SECURITY.md).

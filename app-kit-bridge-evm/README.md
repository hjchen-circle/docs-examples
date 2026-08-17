# Bridge USDC between EVM chains

Use [`@circle-fin/app-kit`](https://www.npmjs.com/package/@circle-fin/app-kit)
to bridge USDC from Ethereum Sepolia to Arc Testnet with a browser wallet and
the viem adapter.

This Vite + TypeScript page connects an EIP-6963 wallet (for example MetaMask),
creates a Circle adapter from the provider, then calls `bridge()` and
`retryBridge()` when needed.

## Prerequisites

- [Node.js 22 or later](https://nodejs.org/)
- An EIP-6963 browser wallet such as MetaMask
- Testnet USDC on Ethereum Sepolia
- Native gas token on Ethereum Sepolia for the wallet transaction

This project does not require environment variables or API keys.

## Install and run

```bash
npm install
npm run dev
```

Open the local Vite URL in a browser with your wallet installed.

```bash
npm run build
```

## What this example does

1. Discovers an EIP-6963 browser wallet and requests account access.
2. Creates a viem adapter with `createViemAdapterFromProvider()`.
3. Bridges 1 USDC from `Ethereum_Sepolia` to `Arc_Testnet` with `kit.bridge()`.
4. Retries with `kit.retryBridge()` if the result state is `"error"`.
5. Streams App Kit action events into the on-page output panel.

## Key file

- `src/main.ts` — wallet connect, adapter creation, bridge, and retry.
  Change `from` / `to` `chain` and `amount` in the bridge call for different
  chains or amounts.

# Swap USDC on Arc Testnet

Use [`@circle-fin/app-kit`](https://www.npmjs.com/package/@circle-fin/app-kit)
to estimate and swap USDC for EURC on Arc Testnet with a browser wallet and the
viem adapter.

This Vite + TypeScript page connects an EIP-6963 wallet (for example MetaMask),
creates a Circle adapter from the provider, then calls `estimateSwap()` and
`swap()`.

## Prerequisites

- [Node.js 22 or later](https://nodejs.org/)
- An EIP-6963 browser wallet such as MetaMask
- Testnet USDC on Arc Testnet
- Native gas token on Arc Testnet for the wallet transaction

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
3. Estimates the swap with `kit.estimateSwap()`.
4. Swaps 1 USDC for EURC on `Arc_Testnet` with `kit.swap()`.

## Thin liquidity on Arc Testnet

Arc Testnet swap pools are often thin or imbalanced. Quotes and swaps can fail
even when your code and wallet setup are correct. This is an environment
limitation on testnet, not a bug in your integration.

Common errors:

- **No route available** — the swap router could not find a quote for that pair
  or amount (liquidity path missing or temporarily unavailable).
- **On-chain simulation failed** — a quote existed, but the pool could not meet
  the minimum output under the configured slippage.

If you hit either error:

1. Retry with a smaller `amountIn` (for example `0.1` or `1` USDC).
2. Prefer `EURC → USDC` when probing for available depth — Arc Testnet pools
   are often USDC-heavy, so that direction usually has less price impact.
3. Optionally raise `config.slippageBps` above the default `300` (3%) for
   testnet experiments.
4. Retry later — testnet liquidity and routing availability change over time.

Use mainnet liquidity expectations only after you move off Arc Testnet.

## Key file

- `src/main.ts` — wallet connect, adapter creation, estimate, and swap.
  Change `chain`, `tokenIn` / `tokenOut`, and `amountIn` in the swap params
  for a different chain, pair, or amount.

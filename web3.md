# Web3 Basic


## Basics

Mnemonic (seed phrase) → private key → public key → address

## Keys, signatures, and verification

- A **private key** signs a transaction.
- The network verifies the signature using the corresponding **public key** (derived from the private key). In many chains, the **address** is derived from the public key (or from its hash).

## How a transaction gets "on-chain"

The **consensus layer** (e.g., PoW / PoS) orders transactions into blocks and finalizes them.

## Smart contracts (high level)

Private key signs call data → contract executes → on-chain state changes.

## Business (examples)

### How "pay" could work (smart account)

1. User passkey + OKX passkey sign data → store public keys in a smart account.
2. Smart account creates an address mapping for the user to receive deposits.
   1. or one user has one smart contract, the smart contract address is the deposit address
3. User signature + OKX signature → smart contract verifies → transfers funds.

### How "swap" works (AMM)

- AMM pool (constant product): **x \* y = k**
  - x/y are token reserves; trades move the reserves and therefore the price.

### How "earn" works

Deposit funds → protocol/contract calculates yield → user claims rewards (or auto-compounds, depending on the protocol).

## How a DEX works (high level)

1. **Liquidity**: liquidity providers (LPs) deposit token pairs into pools.
2. **Pricing**: pool reserves determine price (AMM), or an order book matches bids/asks (order-book DEX).
3. **Trade execution**: user signs a swap transaction → DEX contract validates inputs (amounts, slippage, deadline) → updates pool reserves and transfers tokens.
4. **Fees**: each trade pays a fee; fees are distributed to LPs (and sometimes to a protocol treasury).
5. **Slippage & MEV**: large trades create slippage; common protections include slippage limits, deadlines, MEV-protected relays/private RPC, and (protocol-dependent) oracle/TWAP checks.

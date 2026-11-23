# x402-StreamLock

**Trustless, pay-per-second (and sub-second) encrypted video / data streaming powered by x402 micropayments on Aptos.**

Agents (and humans) can stream encrypted segments to each other. Payment happens automatically via the x402 protocol. Viewers/agents only pay for what they actually consume. Instant stop + refunds. Creators / producing agents keep ~99%.

Built for the agent economy: true machine-to-machine (A2A) encrypted streams with internet-native payments.

## Vision
- Segment-by-segment (or sub-second chunk) encryption
- x402-gated key delivery / chunk release
- Pay-only-for-what-you-watch / process
- Instant refunds when the consumer stops
- Optimized for Aptos (instant finality, sub-cent fees, parallel execution)
- First-class support for autonomous AI agents as both producers and consumers

## Tech Stack
- **Payments**: x402 protocol (`@x402/core` + `@x402/aptos`)
- **Chain**: Aptos
- **Language**: TypeScript
- **Encryption**: AES-GCM (or similar) per segment + key management
- **Streaming**: HTTP / WebSocket / custom chunk protocol (to be decided)

## Quick Start (once implemented)

```bash
pnpm install
cp .env.example .env
# fill in Aptos private keys, facilitator URL, etc.
pnpm dev
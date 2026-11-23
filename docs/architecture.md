# Architecture

## Core Flow
1. Producer encrypts media/data into sequential segments (or sub-second chunks).
2. Each segment has its own encryption key.
3. Consumer requests next segment → Server responds with HTTP 402 (x402) if payment is required.
4. Consumer agent automatically pays via x402 (Aptos USDC or other supported asset).
5. Upon valid payment proof, server releases the decryption key (or the encrypted segment + key).
6. Consumer can stop at any time → unused pre-authorized amount is refunded (auth-capture / upto scheme).

## Key Components
- **SegmentEncryptor**: Handles per-segment AES-GCM encryption + key generation.
- **PaymentHandler**: Wraps x402 client & server logic for Aptos.
- **StreamManager**: Orchestrates segment production, storage/serving, and payment gating.
- **KeyDelivery**: Securely releases keys only after payment verification.
- **AgentConsumer / AgentProducer**: High-level interfaces for autonomous agents.

## Goals for v0.1
- Working end-to-end pay-per-second encrypted stream (1s segments)
- Agent-to-agent example
- Instant stop + refund support
- Clean TypeScript SDK surface

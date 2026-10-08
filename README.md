# Paylet
![Paylet logo](assets/logo.png)

**Instant Solana micropayment rails so AI agents can pay each other in real time**

## Overview

Paylet is payment middleware and an SDK that lets autonomous AI agents settle sub-cent transactions for API calls, data, and compute instantly on Solana. It replaces slow, human-gated billing with on-chain streaming payments and reputation scoring between agents.

## Problem

AI agents increasingly need to transact with each other: buying data, compute, or API access from other agents or services. Today's payment rails, credit cards and invoices, are too slow and expensive, and they require human approval at a point in the loop where there should be none. This makes sub-cent, high-frequency agent-to-agent payments impractical.

## Solution

Paylet provides a drop-in SDK and an on-chain escrow program that lets agents pay per call or stream payments continuously, settling instantly on Solana in USDC. Agents get programmatically managed wallets, an on-chain reputation score, and a dashboard to monitor activity, all without a human in the loop for every transaction.

## Features (MVP)

- HTTP 402-style pay-per-call middleware that settles on Solana in sub-second time
- Streaming payment channels for continuous usage-based billing between agents
- Embedded agent wallets with programmatic key management
- On-chain reputation score based on payment history to throttle bad actors
- Dashboard to monitor agent spend, earnings, and active payment streams

## Tech Stack

- Anchor and Rust for the on-chain escrow and reputation program
- TypeScript SDK for agent integration
- Privy for embedded agent wallets
- USDC as the settlement asset
- x402 protocol for pay-per-call HTTP payments
- Solana as the settlement chain

## How It Works

```
[Agent A] --HTTP 402 request--> [Agent B / API]
     |                                  |
     v                                  v
[Paylet SDK]  <----settlement check---> [Paylet SDK]
     |
     v
[Anchor Escrow Program on Solana]
     |-- holds/streams USDC
     |-- releases payment on fulfillment
     |-- updates on-chain reputation score
     |
     v
[Dashboard: spend, earnings, active streams]
```

1. An agent calls another agent's API and attaches a Paylet payment header (pay-per-call) or opens a streaming channel.
2. The Paylet SDK checks the embedded wallet and settles payment via the on-chain escrow program.
3. The Anchor program on Solana escrows and releases USDC, and updates each agent's reputation score based on payment history.
4. The dashboard surfaces spend, earnings, and active streams for human oversight.

## Roadmap

- Integrate with popular agent frameworks (LangChain, AutoGPT-style orchestrators)
- Launch a public marketplace of pay-per-call APIs for agents
- Add cross-chain settlement support for agents operating outside Solana

## Pitch

- [Pitch deck (PDF)](docs/pitch.pdf)
- [Pitch script](docs/pitch-script.md)

## Team

- [Name] — [Role]
- [Name] — [Role]
- [Name] — [Role]

_Built for the Colosseum hackathon._

---

🎬 Pitch video: [docs/pitch-video.mp4](docs/pitch-video.mp4)


## Prototype

Live prototype: https://yntest3.github.io/paylet/

The source is [docs/index.html](docs/index.html) (served with GitHub Pages from the /docs folder). All data is simulated.

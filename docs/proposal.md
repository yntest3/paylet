# Paylet

_Instant Solana micropayment rails so AI agents can pay each other in real time_

## Summary

Paylet is a payment middleware and SDK that lets autonomous AI agents settle sub-cent transactions for API calls, data, and compute instantly on Solana. It replaces slow, human-gated billing (credit cards, invoices) with on-chain streaming payments and reputation scoring between agents.

## Target users

AI agent developers, API/data providers, autonomous agent platforms

## Problem

AI agents increasingly need to transact with each other (buying data, compute, API access) but today's payment rails are too slow, expensive, and require human approval for micropayments.

## Solution

Paylet provides a drop-in SDK and on-chain escrow program that lets agents pay per call or stream payments continuously, settling instantly on Solana with USDC.

## MVP features

- HTTP 402-style pay-per-call middleware that settles on Solana in sub-second time
- Streaming payment channels for continuous usage-based billing between agents
- Embedded agent wallets with programmatic key management
- On-chain reputation score based on payment history to throttle bad actors
- Dashboard to monitor agent spend, earnings, and active payment streams

## Chains

Solana

## Tech

Anchor, Rust, TypeScript SDK, Privy embedded wallets, USDC, x402 protocol

## Category

AI

## Why now

The explosion of autonomous AI agents needing to transact with each other makes fast, trust-minimized micropayment rails urgently necessary, and Solana's speed/cost profile is uniquely suited for it.

## Roadmap

- Integrate with popular agent frameworks (LangChain, AutoGPT-style orchestrators)
- Launch a public marketplace of pay-per-call APIs for agents
- Add cross-chain settlement support for agents operating outside Solana

# Agent Authority

> Exploring verifiable chains of authority for autonomous AI agents.

## The Problem

As AI agents become increasingly autonomous and delegate tasks to other agents, a critical question emerges:

**Who authorized this agent to act?**

Existing identity systems can help identify an agent, but identity alone does not explain the authority behind its actions.

This project explores a verifiable system for answering:

- Who granted authority to an agent?
- What permissions were granted?
- Can those permissions be delegated?
- Can an agent delegate more authority than it received?
- Is the authority still valid?
- Can the chain of authority be independently verified?

## Core Concept

```text
Human / Organization
        │
        │ grants authority
        ▼
      Agent A
        │
        │ delegates limited authority
        ▼
      Agent B
        │
        │ delegates limited authority
        ▼
      Agent C

      ## Current Research Direction

Agent Authority is currently exploring how autonomous AI agents can carry verifiable chains of delegated authority.

The current research direction investigates combining:

- Decentralized Identifiers (DIDs) for cryptographic identity
- Macaroon-style capabilities for delegated and restricted authority
- Status Lists or similar mechanisms for revocation

This architecture is experimental and subject to change as research continues.

## Core Question

> When an autonomous AI agent performs an action, can we cryptographically verify who authorized it and how that authority reached the agent?
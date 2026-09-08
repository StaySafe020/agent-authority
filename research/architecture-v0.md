# Agent Authority Architecture v0

> Status: Research hypothesis. This is not the final architecture.

## Current Direction

The current architectural direction is to explore a combination of:

- Decentralized Identifiers (DIDs)
- Macaroon-style authorization and delegation
- Status Lists for revocation

The goal is to investigate whether these technologies can work together to support verifiable authority chains for autonomous AI agents.

---

# 1. Identity Layer — DIDs

Each agent could have a decentralized identifier.

The DID would provide a cryptographic identity that can be independently verified.

Example:

did:agent:123

The identity layer answers:

> Who is this entity cryptographically?

However, identity alone does not define authority.

---

# 2. Authority Layer — Macaroon-Style Delegation

Authority could be represented using cryptographically restricted capabilities.

When authority moves from one agent to another, permissions should only become more restricted.

Example:

Human
  ↓
Agent A

Permissions:
- Access financial API
- Maximum transaction: $10,000

Agent A
  ↓
Agent B

Permissions:
- Access financial API
- Maximum transaction: $500

Agent B cannot increase its authority beyond what Agent A received.

Principle:

Authority(Child) ⊆ Authority(Parent)

---

# 3. Revocation Layer — Status Lists

A major challenge with decentralized or offline verification is revocation.

If authority is revoked, systems need a way to determine whether an identity or authorization remains valid.

One approach being explored is a cryptographically verifiable status list.

Instead of requiring every verifier to contact every authority in the delegation chain, a verifier may check a compact status mechanism.

Possible approaches being researched include:

- Bitmaps
- Status lists
- Short-lived credentials
- Expiring keys

---

# Potential Verification Flow

Human
  ↓
Agent A
  ↓
Agent B
  ↓
Agent C
  ↓
Tool / API

When Agent C requests an action, the verifier could potentially check:

1. Agent C identity
2. Agent C authority
3. Delegation chain
4. Permission restrictions
5. Revocation status

The objective is to minimize unnecessary server-to-server communication while maintaining verifiable authority.

---

# Open Questions

This architecture has not been validated.

Important questions include:

- Are DIDs necessary for the system?
- Are Macaroons the best delegation primitive?
- How should delegation chains be represented?
- How can revocation work efficiently?
- Can verification happen locally?
- How large can delegation chains become?
- What happens when a parent authority is revoked?
- How do we prevent privilege escalation?

---

# Architecture Principle

The architecture should follow this rule:

> Identity proves who an entity is. Authority proves what it is allowed to do.

Agent Authority is primarily concerned with the second problem and the chain connecting authority back to its source.
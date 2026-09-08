# AI Agent Identity Research

## Research Question

What exactly is an AI agent identity, and what existing identity and authorization systems are already trying to solve this problem?

---

## What is an AI Agent?

An AI agent is more than a chatbot.

It is a software system capable of reasoning, planning, using tools, and executing actions to achieve a goal.

As agents become more autonomous, they will interact with APIs, databases, financial systems, users, and other agents.

This creates an important question:

> How do we know who or what an autonomous agent is, and who gave it permission to act?

---

# Existing Technologies

## Decentralized Identifiers (DIDs)

DIDs provide globally unique decentralized identifiers controlled through cryptographic keys.

They can help establish cryptographic identity without relying entirely on centralized identity providers.

However, identity alone does not explain:

- Who authorized an agent
- What permissions it has
- Where its authority originated
- Whether its authority was delegated

---

## Verifiable Credentials

Verifiable Credentials are cryptographically signed digital statements.

They can be used to prove claims about an identity or permissions granted to an entity.

For AI agents, this could potentially represent information such as:

- Who created the agent
- Which organization issued permissions
- What role the agent has

---

## OAuth Delegation

OAuth allows users or organizations to authorize applications to access resources on their behalf.

It provides strong centralized authorization and revocation mechanisms.

However, multi-agent delegation can become more complex when authority moves across multiple agents or systems.

---

## Macaroons

Macaroons are authorization tokens that support delegation and attenuation.

Attenuation allows permissions to become more restricted as authority moves from one entity to another.

For example:

Agent A:
- Read and write access
- $10,000 transaction limit

Agent B:
- Read-only access
- $100 transaction limit

The delegated authority should not exceed the authority of the parent.

This can be represented as:

Authority(Child) ⊆ Authority(Parent)

---

# Initial Observation

Existing technologies solve different parts of the problem:

| Technology | Primary Focus |
|---|---|
| DIDs | Identity |
| Verifiable Credentials | Verifiable claims |
| OAuth | Authorization and delegation |
| Macaroons | Restricted delegation |

The potential gap being explored is the ability to verify the complete chain of authority behind autonomous AI agents.

---

# Key Questions

When an AI agent performs an action, a verifier may need to answer:

1. Who is this agent?
2. Who created or controls it?
3. Who authorized it?
4. What permissions does it have?
5. Was that authority delegated?
6. Can the full authority chain be verified?
7. Has any authority in the chain been revoked?

---

# Current Hypothesis

Agent Authority may not primarily be an identity system.

Instead, it may be a system for representing and verifying how authority moves between autonomous entities.

Example:

Human
  ↓ authorizes
Agent A
  ↓ delegates restricted authority
Agent B
  ↓ delegates further
Agent C

A system interacting with Agent C should be able to verify the origin and validity of its authority.

---

# Status

Research stage.

No final architecture has been selected.

Current focus:

- AI agent identity
- Authorization
- Delegation
- Authority attenuation
- Delegation chains
- Revocation
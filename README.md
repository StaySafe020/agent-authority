h# Agent Authority

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
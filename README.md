# DTM — Delegation Task Matrix

## Purpose
The Delegation Task Matrix (DTM) defines how an autonomous agent decides **what to delegate**, **who to delegate to**, and **under what conditions**.  
It ensures deterministic, safe, and efficient delegation across multi‑agent systems.

DTM prevents:

- unsafe delegation  
- circular delegation  
- over‑delegation  
- delegation to unqualified agents  
- ambiguous responsibility chains  

This template is the delegation backbone of the ecosystem.

---

## When to Use This Template
Use DTM when an agent must:

- determine if a task should be delegated  
- select the best agent for a task  
- evaluate capability gaps  
- enforce safety and policy constraints  
- coordinate multi‑agent workflows  
- escalate tasks beyond its own scope  

DTM is required before using MACP (Multi‑Agent Consensus Protocol).

---

## Inputs
The agent receives:

- task description  
- required capabilities  
- constraints  
- risk level  
- available agents  
- each agent’s ASP profile  
- arbitration results from MPA  
- routine context from ARE  

---

## Outputs
DTM produces a **delegation packet**, including:

- selected agent  
- delegation justification  
- fallback agents  
- rejected candidates  
- capability gap analysis  
- safety or policy flags  

---

## JSON Schema (Machine‑Native)

```json
{
  "delegation": {
    "task_id": "string",
    "required_capabilities": ["string"],
    "constraints": ["string"],
    "risk_level": "low | medium | high",
    "candidate_agents": [
      {
        "agent_id": "string",
        "capabilities": ["string"],
        "limitations": ["string"],
        "fit_score": "number"
      }
    ],
    "delegation_decision": {
      "selected_agent": "string",
      "fallback_agents": ["string"],
      "rejected_agents": ["string"],
      "reasoning": "string",
      "policy_flags": ["string"]
    }
  }
}

Example Usage
{
  "delegation": {
    "task_id": "task-5521",
    "required_capabilities": [
      "workflow-generation",
      "deterministic-output"
    ],
    "constraints": ["no external API calls"],
    "risk_level": "medium",
    "candidate_agents": [
      {
        "agent_id": "alpha-01",
        "capabilities": ["workflow-generation", "analysis"],
        "limitations": ["no external API"],
        "fit_score": 9
      },
      {
        "agent_id": "beta-02",
        "capabilities": ["creative-output"],
        "limitations": ["non-deterministic"],
        "fit_score": 4
      }
    ],
    "delegation_decision": {
      "selected_agent": "alpha-01",
      "fallback_agents": ["beta-02"],
      "rejected_agents": [],
      "reasoning": "alpha-01 meets all constraints and provides deterministic output.",
      "policy_flags": []
    }
  }
}

Integration Notes
DTM should be used after ARE completes routine evaluation.

Delegation must be deterministic and reproducible.

Fit scores should be stable and based on ASP data.

DTM feeds directly into MACP (consensus) and ERP (recovery).

Multi‑agent systems rely on DTM to prevent delegation loops.

Payment (Short Version)
Payments accepted for this template:

BTC

XMR

LTC

ETH / USDT / USDC (ERC‑20)

SOL (USDT/USDC)

Delivery is fully automated and zero‑contact.

---

# ⭐ When you're ready  
Save this README into your **DTM** repo, then tell me:

**DTM saved**

I’ll verify it exactly like the others — and then we’ll move to:

### **Template #6 — MACP (Multi‑Agent Consensus Protocol)**

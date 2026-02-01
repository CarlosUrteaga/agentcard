# AGENTCARD.md - The MICAI 2025 Documentation Standard

## 🧠 Overview
Agent Cards provide a structured standard for documenting AI agents, covering behavioral attributes, tool integrations, and governance metadata. This standard ensures transparency and reproducibility in agentic systems.

## 📋 Agent Card Template (Mandatory Fields)

| Section | Description |
| :--- | :--- |
| **Agent Name/Version** | Identifier and semantic version (e.g., TaxBot v0.7.3). |
| **Agent Role(s)** | Specific roles: Planner, Executor, Critic, or Orchestrator. |
| **Inputs/Outputs** | Data formats accepted (PDF, XML) and response types (API, Text). |
| **Tools/Functions** | External capabilities (calculators, APIs, search modules). |
| **Governance** | Safety filters, PII handling, and manual approval policies. |
| **Memory** | Short-term (context window) and Long-term (persistent) design. |
| **Known Limitations** | Boundaries of autonomy and sources of non-determinism. |

## 🛠️ Implementation Example (YAML)
```yaml
agentcard: 1.0
meta:
  name: "Institutional_Agent"
purpose:
  objective: "Perform tasks within specific operational boundaries"
tools:
  - name: "system_access"
    scope: "restricted"
autonomy:
  requires_approval_for: ["write_operations", "external_api_calls"]
policies:
  pii_scrubbing: true
  logging: "structured_traces"

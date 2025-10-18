# 🛡️ Cyber Security Guard Defense Stack

Multi-layered adaptive cybersecurity framework integrating AI-driven threat detection, real-time monitoring, VPN anonymity, and pre-entry link validation. Designed for ethical, defensive use with automated workflows and SOAR logic.

---

## ⚙️ Overview

The Cyber Security Guard Stack is a comprehensive defensive ecosystem designed for maximum resilience. It combines multiple modules:

CSG (Core AI-XDR): Central intelligence and adaptive monitoring

CG (AI-SOC & Threat Intel): Threat correlation and analytical support

VPN.CSG: Secure, decentralized anonymity and routing

Link.CSG: Pre-entry AI-based link validation

This framework allows seamless automation and coordination between modules via secure APIs and workflow orchestration (e.g., N8N).

Visual overview of the workflow is provided below:

![Workflow Diagram](docs/en/n8n-en.jpg)

---

## 🧩 Architectural Components

| Component | Technical Role | Position in Stack |
|-----------|----------------|-----------------|
| CSG       | AI-XDR Core    | Central/Internal |
| CG        | AI-SOC & Threat Intel | Supportive/Analytical |
| VPN.CSG   | Decentralized Anonymity | Perimeter/Boundary |
| Link.CSG  | Pre-Entry AI Validation | Perimeter/Gateway |

![System Architecture](docs/en/architecture.png)

---

## 🧰 Prerequisites

- OS: Linux/Windows Server or Containerized Environment
- Automation: N8N installed (Docker recommended)
- Dependencies: Install or build all four modules (CSG, CG, VPN.CSG, Link.CSG)
- Development Environments: Python / Rust / Node.js depending on module

---

## 🚀 Deployment & N8N Integration

### Step 1: Install Modules
Follow instructions for each component to deploy them in your environment. Ensure APIs are enabled and reachable.

### Step 2: Configure N8N for Automati

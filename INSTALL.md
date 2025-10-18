# 🧰 Installation Guide — Cyber Security Guard Defense Stack

This guide provides step-by-step instructions to install and configure the full defense stack, including all four modules and automation via N8N.

---

## 📦 Prerequisites

- Operating System: Linux (Ubuntu recommended), Windows Server, or Docker-compatible environment  
- Development Tools:
  - Python 3.10+ (for CG and Link.CSG)
  - Rust (for CSG core)
  - Node.js 18+ (for N8N and VPN.CSG)
- Docker & Docker Compose (recommended for modular deployment)
- GitHub CLI (optional for cloning repositories)

---

## 🔽 Step 1: Clone the Repositories

```bash
gh repo clone Alasarmamhd/Cyber-Security-Guard-Defense-Stack
gh repo clone Alasarmamhd/cyber-guard-pro
gh repo clone Alasarmamhd/cyber-security-guard-pro
gh repo clone Alasarmamhd/VPN-GUARD.-SCG-
gh repo clone Alasarmamhd/linkgarde.csg

------
⚙️ Step 2: Install N8N (Automation Engine)
Option A: Docker (Recommended)
bash
docker run -it --rm \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  n8nio/n8n
Option B: Local Installation
bash
npm install n8n -g
n8n start
🧠 Step 3: Configure Each Module
CSG (Core AI-XDR)
Navigate to the cyber-security-guard-pro directory

Build using Rust or run precompiled binary

Ensure API service is running on port 5050

CG (AI-SOC & Threat Intelligence)
Navigate to cyber-guard-pro

Install Python dependencies

bash
pip install -r requirements.txt
Start the service

bash
python main.py
VPN.CSG (Decentralized VPN)
Navigate to VPN-GUARD.-SCG-

Install Node.js dependencies

bash
npm install
Run the VPN service

bash
node vpn.js
Link.CSG (Pre-entry Validation)
Navigate to linkgarde.csg

Install Python dependencies

bash
pip install -r requirements.txt
Start the validation engine

bash
python linkguard.py
🔗 Step 4: Connect Modules via N8N
Use N8N workflows to automate:

Incident response triggers from CSG

Threat correlation via CG

Link scanning via Link.CSG

VPN routing updates via VPN.CSG

Refer to the visual diagrams in docs/ar/ and docs/en/ for workflow examples.

✅ Final Check
All modules should expose their APIs and respond to health checks

N8N should be able to trigger and coordinate actions across modules

Logs and alerts should be visible in terminal or dashboard (if configured)

For advanced deployment (TLS, Docker Compose, monitoring), refer to future updates in the Wiki or GitHub Pages.

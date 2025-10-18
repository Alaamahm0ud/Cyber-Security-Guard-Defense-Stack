````markdown
# 🧰 Installation Guide — Cyber Security Guard Defense Stack

This guide provides step-by-step instructions to install and configure the full defense stack, including all four modules and automation via N8N.

---

## 📦 Prerequisites
- Operating System: Linux (Ubuntu recommended), Windows Server, or any Docker-compatible environment  
- Development Tools:
  - Python 3.10+ (for CG and Link.CSG)
  - Rust (for CSG core)
  - Node.js 18+ (for N8N and VPN.CSG)
- Docker & Docker Compose (recommended for modular deployment)
- GitHub CLI (optional for cloning repositories)

---

## ⚙️ Step 1: Clone the Repositories
Open your terminal and run the following commands to clone all required repositories:

```bash
gh repo clone Alasarmamhd/Cyber-Security-Guard-Defense-Stack
gh repo clone Alasarmamhd/cyber-guard-pro
gh repo clone Alasarmamhd/cyber-security-guard-pro
gh repo clone Alasarmamhd/VPN-GUARD.-SCG-
gh repo clone Alasarmamhd/linkgarde.csg
````

---

## 🧩 Step 2: Install N8N (Automation Engine)

You can install N8N using Docker (recommended) or locally via Node.js.

### Option A — Docker (Recommended)

```bash
docker run -it --rm \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  n8nio/n8n
```

### Option B — Local Installation

```bash
npm install n8n -g
n8n start
```

---

## 🔧 Step 3: Configure Each Module

### 1. CSG (Core AI-XDR)

```bash
cd cyber-security-guard-pro
# Build using Rust or run the precompiled binary
# Ensure API service is running on port 5050
```

### 2. CG (AI-SOC & Threat Intelligence)

```bash
cd cyber-guard-pro
pip install -r requirements.txt
python main.py
```

### 3. VPN.CSG (Decentralized VPN)

```bash
cd VPN-GUARD.-SCG-
npm install
node vpn.js
```

### 4. Link.CSG (Pre-entry Validation)

```bash
cd linkgarde.csg
pip install -r requirements.txt
python linkguard.py
```

---

## 🔗 Step 4: Connect Modules via N8N

Use N8N workflows to automate and coordinate processes between modules:

* Incident response triggers from CSG
* Threat correlation and intelligence via CG
* Link scanning and validation via Link.CSG
* VPN routing updates via VPN.CSG

Refer to the visual diagrams in `docs/ar/` and `docs/en/` for workflow examples.

---

## ✅ Final Check

After setup, verify the following:

* Each module exposes an API and responds to health checks.
* N8N can trigger and coordinate actions across modules.
* Logs and alerts are visible in the terminal or dashboard (if configured).

---

## 🛠️ Advanced Deployment

For production or advanced deployment, consider:

* Enabling TLS / HTTPS (SSL certificates)
* Using Docker Compose or Kubernetes
* Monitoring with ELK Stack or Prometheus + Grafana
* Enforcing Role-Based Access Control (RBAC) and audit logs
* Setting up backups and disaster recovery

Refer to the Wiki or GitHub Pages for more advanced details and examples (`.env` files, Docker configurations, TLS setup, etc.).

---

## 📂 Suggested Repository Structure

```
.
├── cyber-security-guard-pro/     # CSG Core
├── cyber-guard-pro/              # CG (AI-SOC)
├── linkgarde.csg/                # Link.CSG
├── VPN-GUARD.-SCG-/              # VPN.CSG
├── n8n-workflows/                # Exported N8N workflows
├── docs/
│   ├── en/
│   └── ar/
└── INSTALL.md                    # This installation guide
```

---

```
```

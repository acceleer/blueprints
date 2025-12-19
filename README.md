![Acceleer B L U E P R I N T S](media/blueprints.png)

# The Future of Industrial Process Automation

- 🔥🚀 Accelerate  : Engineer 10x faster.
- 🕺🕺 Collaborate : Process Engineers x Automation Engineers x AI Agents
- ⚙️🏗️ Generate    : Deterministic Code-Generation at Scale
- 🤖✅ Trusted AI  : Agentic Functional Design > Human Review > Deterministic Code

# Purpose of B L U E P R I N T S

- Demonstrate a CLI-based Design-Ops workflow (for GUI-based: subscribe to Acceleer)
- Share and collaborate on Template Packages for different systems (Siemens, Rockwell, Beckhoff, ...) 

# Quick Start

## 1. Install Acceleer CLI

Run this command in PowerShell:

```powershell
irm https://github.com/acceleer/acceleer-cli/releases/latest/download/install.ps1 | iex
```

## 2. Clone this repo

```powershell
gh repo clone acceleer/blueprints
```



## 3. Generate PLC Code from FDS

```powershell
cd blueprints
```

```powershell
acceleer generate
```

## 4. What just happened 🤯✨? (Quick FAQ)

**Q: What just happened?**  
**A:** The CLI reads the functional design (FDS) from ./inputs/functional-design and generates a.o PLC Code to ./outputs

**Q: Is this for real projects?**  
**A:** YES! This is not a research project.  
This workflow is already used by multiple teams to bring real projects to production.  
The focus is on Food, Pharma, Fine Chemicals and other process manufacturing.   
From small skids to multi-plant standardizations.

**Q: The textual FDS looks cumbersome to edit.**  
**A:** This is only for demonstration and Agentic usage.  
There is a collaborative and convenient GUI Editor available when using the Acceleer platform.

**Q: How to import the generated PLC/DCS code in the relevant IDE?**  
**A:** The Acceleer platform comes with an agent that allows the import into different target systems.

**Q: Is there a community edition?**  
**A:** Yes, reserved for open-source and educational projects.

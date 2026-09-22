\# Enterprise Power BI CI/CD \& Semantic Model Governance



!\[Semantic Model BPA Gatekeeper](https://github.com/Muskanbhagat123/powerbi-semantic-ci-cd/actions/workflows/bpa-scan.yml/badge.svg)

!\[Power BI](https://img.shields.io/badge/Power\_BI-PBIP\_%2B\_TMDL-F2C811?logo=powerbi\&logoColor=black)

!\[DevOps](https://img.shields.io/badge/DevOps-GitHub\_Actions-2088FF?logo=githubactions\&logoColor=white)

!\[Tabular Editor](https://img.shields.io/badge/Engine-Tabular\_Editor\_CLI-0078D4)



A production-grade Enterprise Semantic Model repository demonstrating continuous integration (CI), version control via Power BI Project (`.pbip`) and Tabular Model Definition Language (TMDL), automated Best Practice Analyzer (BPA) gatekeeping, and branch protection enforcement.



\---



\## 🏗️ Architecture Overview



Traditional monolithic Power BI binaries (`.pbix`) lack true Git version control, change tracking, and automated linting. This project utilizes developer-mode `.pbip` to serialize model metadata into human-readable TMDL scripts, enabling enterprise-scale collaborative workflows.



```text

&#x20;      Developer Workspace

&#x20; ┌───────────────────────────┐

&#x20; │  Power BI Desktop (.pbip) │

&#x20; └─────────────┬─────────────┘

&#x20;               │

&#x20;               ▼ (Serialize metadata)

&#x20; ┌───────────────────────────┐

&#x20; │      TMDL Data Models     │

&#x20; └─────────────┬─────────────┘

&#x20;               │

&#x20;               ▼ (git push)

&#x20; ┌───────────────────────────┐

&#x20; │ Feature Branch \& PR Stage │

&#x20; └─────────────┬─────────────┘

&#x20;               │

&#x20;               ▼ (Triggers Workflow)

&#x20; ┌───────────────────────────┐

&#x20; │   GitHub Actions Runner   │

&#x20; └─────────────┬─────────────┘

&#x20;               │

&#x20;        (te-scan engine)

&#x20;        ┌──────┴──────┐

&#x20;        ▼             ▼

&#x20; ┌─────────────┐ ┌─────────────┐

&#x20; │ Rule Breach │ │ 100% Passed │

&#x20; └──────┬──────┘ └──────┬──────┘

&#x20;        ▼               ▼

&#x20;  ❌ Build Blocked  ✅ Merge Allowed to main


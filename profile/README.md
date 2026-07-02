# Welcome to Atlas-Orbit 🛰️

Atlas-Orbit is building the next generation of open operations infrastructure, focusing on seamless integration, intelligent coordination, and living documentation for distributed systems.

## Our Ecosystem

### 🌐 Core Projects

- **[Orbit](https://github.com/Atlas-Orbit/orbit)** — The living documentation and repo-context layer for the Atlas & Orbit ecosystem. Serving as the knowledge foundation for our entire platform.

- **[OpenOps Core - Interlink](https://github.com/Atlas-Orbit/openops-core-interlink)** — The foundational interlink project for OpenOps Core. Building the bridges between systems.

- **[Control Tower MCP](https://github.com/Atlas-Orbit/control-tower-mcp)** — A governed MCP bridge connecting work-trackers, GitHub Projects, Linear, manifests, receipts, and enabling agent-agnosti[...]

- **[Demo Repository](https://github.com/Atlas-Orbit/demo-repository)** — Showcasing the best GitHub has to offer.

### 📋 Templates & Resources

- **[Repository Template](https://github.com/Atlas-Orbit/repo-template)** — A starter template for creating new repositories within the Atlas-Orbit ecosystem.

## Architecture: Atlas & Orbit ecosystem

This diagram shows the high-level components and interactions across the Atlas and Orbit subsystems.

```mermaid
graph LR
  %% Atlas cluster
  subgraph Atlas["Atlas"]
    direction TB
    A_Web["Atlas Web App"]
    A_Mobile["Atlas Mobile"]
    A_API["Atlas API"]
    A_DB[("Atlas DB")]
    A_Workers["Atlas Workers / Jobs"]
    A_SDKs["Atlas SDKs & Clients"]
  end

  %% Orbit cluster
  subgraph Orbit["Orbit"]
    direction TB
    O_Panel["Orbit Control Panel"]
    O_Agents["Orbit Agents"]
    O_API["Orbit API"]
    O_DB[("Orbit DB")]
    O_Telemetry["Telemetry / Observability"]
    O_Autonomy["Autonomy Engine"]
  end

  %% Shared infrastructure
  subgraph Infra["Shared Infrastructure"]
    direction TB
    Bus["Event Bus / Message Queue"]
    CDN["CDN / Static Assets"]
    Reg["Container / Package Registry"]
    CI["CI/CD (GitHub Actions)"]
    Auth["Auth / Identity Provider"]
    Monitoring["Monitoring & Alerting"]
    Secrets["Secrets Manager"]
  end

  %% External
  Users["Users / Customers / Admins"]
  ThirdParty["3rd-party Integrations / APIs"]
  GitHub["GitHub Repos & Issues"]

  %% Core flows
  Users --> A_Web
  Users --> A_Mobile
  A_Web --> A_API
  A_Mobile --> A_API
  A_API --> A_DB
  A_API --> Bus
  A_Workers --> A_DB
  A_Workers --> Bus

  Bus --> O_API
  O_API --> O_DB
  O_Agents --> O_API
  O_Agents --> Bus
  O_Autonomy --> O_Agents
  O_Autonomy --> O_API
  O_Telemetry --> Monitoring

  CI --> Reg
  CI --> CDN
  CI --> A_Web
  CI --> A_API
  CI --> O_Panel
  CI --> O_API

  GitHub --> CI
  GitHub --> A_SDKs
  A_SDKs --> Users

  ThirdParty --> A_API
  ThirdParty --> O_API

  Auth --> A_API
  Auth --> O_API
  Secrets --> A_API
  Secrets --> O_API

  Monitoring --> A_Telemetry["Atlas Telemetry"]
  A_Telemetry --> Monitoring
  Monitoring --> Ops["On-call / PagerDuty"]

  %% Cross-system integrations
  A_API --- O_API
  A_DB --- O_DB
  Reg --- O_Agents
```

## What We're Building

Atlas-Orbit focuses on:

- 🔗 **Interoperability** — Seamless connections between tools and platforms
- 📚 **Documentation** — Living docs that stay in sync with code and systems
- 🤖 **Intelligence** — Agent-agnostic coordination and automation
- 🏗️ **Infrastructure** — Open, governed, and extensible systems

## Getting Started

All repositories in Atlas-Orbit are currently private. To get involved:

1. Check out the [Orbit documentation](https://github.com/Atlas-Orbit/orbit) for project context and architecture
2. Review our [repository template](https://github.com/Atlas-Orbit/repo-template) for our standards
3. Reach out to the team to learn about contribution opportunities

## Contributing

We welcome contributions! For details on how to contribute to any Atlas-Orbit project, please check the individual repository's `CONTRIBUTING.md` file.

---

**Atlas-Orbit** — _Building the future of open operations infrastructure_

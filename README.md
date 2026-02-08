<img width="955" height="652" alt="Hivemind_Logo_No_Background" src="https://github.com/user-attachments/assets/3454c312-92d4-4f68-be25-90db874803ea" />
<div align="center">

# Hivemind
<p>
<em><b>Hivemind</b> is a self-hosted <b>orchestration</b> system and <b>control panel</b> for managing multiple <b><a href=https://foundryvtt.com/>FoundryVTT</a></b> instances.</em>
</p>
</div>

  

Hivemind allows a single host to easily manage games for multiple GMs and dozens of players. Whether you are hosting for your own groups or acting as the server admin for a collective of friends, Hivemind provides a centralized, resource-efficient way to deploy, manage, and play. 

> [!NOTE]
> ### Project Status: Planning Phase 💡
> This project is currently in the initial design and planning stage. No features are currently implemented. The documentation below outlines the *intended* architecture and feature set.

## The Goal

Existing solutions often require complex manual port management, lack centralized asset handling, or are designed for enterprise-grade hosting services.

Hivemind aims to be:

1. **Deployment Friendly:** A pre-configured Nix configuration and Docker Compose setup to get a fully functional system running in minutes.
2. **Resource Efficient:** Intelligently spins containers up and down based on activity to save RAM and CPU.
3. **Storage Smart:** Deduplicates module data using symbolic links, so you don't store "Dice So Nice" 50 times.
4. **Seamless:** Single Sign-On (SSO) removes the need for individual world passwords. A ForgeVTT exclusive no more!

##  Planned Features

### Orchestration & Resource Management

* **Containerized Instances:** The Orchestrator (running in Docker) manages Podman containers for each individual Foundry instance.
* **Auto-Sleep/Wake:** Instances are monitored for player activity to save system resources during downtime.
* **Wake-on-Demand:** Players can wake an "Idle" world directly from the Front Page.
* **Shared Module Library:** Modules are downloaded to a single source directory and symbolically linked to instances. This prevents data duplication and saves massive amounts of disk space.

### Authentication & Security

* **Modern Auth:** Support for standard passwords, Passkeys (Biometrics/Password Managers), and Social Login (Google, Apple, etc.).
* **Centralized SSO:** A single login for the entire Hivemind system. No more "Join Game" screens or per-world passwords.
* **Bypass FoundryVTT Join Page:** When a user launches a world, Hivemind injects a per-user key into the Foundry instance, automatically logging them in as their per-world user.
* **Role-Based Access:** The Orchestrator enforces visibility. Players only see the games they are invited to.

### Administration & Tools

* **Instanced Package Manager:** A UI for GMs and Admins to manage modules per instance.
* **Template Worlds:** GMs can create "Template Worlds" (e.g., a pre-configured D&D 5e setup) to use as a template for new instances.
* **World Import:** Easy tools to ingest existing Foundry worlds from outside of Hivemind.
* **Per-User Assets:** Segregated asset storage for players and GMs.

## Contributing

We are currently in the planning phase. If you are interested in the architecture or have suggestions for the roadmap, please open a Discussion ticket!

Ultimately, this project is being designed for my own uses but as an opportunity to give back to the FoundryVTT community, I am publishing and sharing my work under a permissive license.

---

*Hivemind is an independent project and is not affiliated with Foundry Gaming, LLC.*

# Vindicta Platform Roadmap

## The Vindicta Meso-Repo Roadmap

This roadmap adopts the C4 Container structure and assigns development priority to the **Foundation** and **Scribe** modules to enable the rest of the swarm.

### Phase 1: Core Bootstrapping (`foundation` & `scribe`)

**Objective:** Establish the "DNA" and the "Input" stream.

1. **`vindicta-foundation`:** Implement the `constitution.json` and the **Axiom Registry**. Every other module will pull these as a submodule/dependency.
2. **`warscribe-system`:** Build the SATO parser. It must output a standard JSON event stream that `platform` and `engine` can consume.
3. **`vindicta-portal`:** Initial API Gateway setup. This will be the "Console" where you view the WARScribe logs.

### Phase 2: Simulation & Search (`engine`)

**Objective:** Building the "Chess Engine."

1. **Physics & Dice:** Implement the **Axiom of Probability** logic in the `engine`.
2. **Zobrist State Manager:** Build the 64-bit state-hashing system.
3. **Primordia Core:** Build the **Alpha-Beta Search** and **Root Parallelization** logic within this module.

### Phase 3: Prediction & Orchestration (`oracle` & `agents`)

**Objective:** The "Intelligence" Layer.

1. **`vindicta-oracle`:** Feed historical WARScribe logs (from your matches) into a transformer model to begin **Advantage Inference** training.
2. **`vindicta-agents`:** Deploy the **Quantum Leap** swarm. These agents will use the `agents` SDK to perform automated "Self-Play" matches between the `engine` and `oracle`.

### Phase 4: Commercialization & Governance (`economy`)

**Objective:** Sustainability.

1. **`vindicta-economy`:** Implement the "Computation Ledger." This tracks how many "Searches" or "Simulations" each agent or user consumes, preventing your home server from redlining.

## Infrastructure Alignment

To support this Meso-repo format on your home server:

- **CI/CD:** You should use **GitHub Actions** or a local **Runner** that triggers builds across the organization when `foundation` is updated (The "Ripple Effect").
- **Networking:** The `portal` acts as the ingress, while `agents` and `engine` communicate over a low-latency gRPC or Message Bus (like RabbitMQ) to handle the `warscribe` event stream.

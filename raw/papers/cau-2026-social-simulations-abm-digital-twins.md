---
source_url: https://arxiv.org/abs/2607.13693
ingested: 2026-07-22
sha256: c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f8
---

# Social Simulations: from Agent-Based Modeling to Digital Twins

**Authors:** Erica Cau (University of Pisa), Andrea Failla (ISTI-CNR), Valentina Pansanella (ISTI-CNR), Giulio Rossetti (ISTI-CNR)

**Publication:** Entry for Encyclopedia of Social Network Analysis and Mining, July 2026

**License:** CC BY-NC-ND 4.0

## Abstract

Social simulation is a computational approach for studying how social phenomena emerge from interactions among individuals, groups, organizations, and their environments. This article surveys the progression from classical agent-based modeling to large-language-model-enhanced agent-based simulations and social digital twins. It outlines their core modeling assumptions, architectural components, advantages, limitations, and the scope of claims that these approaches can support.

## Three Paradigms of Social Simulation

### 1. Classical Agent-Based Modeling (ABM)
- **Origin:** Schelling's segregation model (1971), Axelrod's dissemination of culture (1997), Sugarscape (1996)
- **Architecture:** Agents defined by attributes (stable characteristics), states (evolving properties), and rules (behavioral algorithms)
- **Interaction:** Typically through network structures (random, small-world, scale-free)
- **Time:** Discrete steps, synchronous or asynchronous updating
- **Key advantage:** Causal mechanism tracing — vary parameters systematically to identify causal effects
- **Key limitation:** "Built on assumptions about behavioral mechanisms that, though theory-informed, may be arbitrary, without validation"
- **Applications:** Opinion dynamics, innovation diffusion, voting behavior, epidemic modeling

### 2. LLM-Enhanced Agent-Based Modeling
- **Shift:** From mechanistic rules → natural language-driven agent reasoning and interaction
- **Architecture:** LLM-powered agents prompted with roles/behaviors, optional memory mechanisms, network embedding
- **Key findings:**
  - In mean-field settings: LLM agents tend toward agreement through structured persuasion
  - In network settings with bounded confidence rules: polarization and echo chamber formation emerge
  - Confirmation bias prompts amplify polarization
- **Advantage:** Captures "argumentation and persuasion strategies" beyond simple state updates
- **Limitation:** "LLMs are statistical models trained on incomplete datasets, which might reflect cultural and demographic biases"; "apparent realism does not guarantee epistemic validity"

### 3. Social Digital Twins (SDTs)
- **Definition:** "A virtual replica of a specific physical, biological, or social system, designed to mirror its structure, state, and behavior using empirical data"
- **Key shift:** From "what happens, in general?" → "what will happen here, now, under these conditions?"
- **Three categories:**
  1. DTs of mechanical systems (cars, bridges)
  2. DTs of biological/cognitive systems (patients, athletes)
  3. DTs of socio-technical systems (hospitals, social media platforms) — **most relevant to social simulation**
- **Advantages:** Controlled counterfactual testing, reusability, augmented forecast granularity, substitute data generation
- **Challenges:** Resource-intensive, validation (structural, behavioral, predictive levels), risk of overfitting
- **Key caution:** "Greater realism is not inherently an epistemic virtue... apparent realism does not guarantee epistemic validity"

## Epistemic Scope of Claims
- **Exploratory use:** Generating hypotheses, testing counterfactuals ✓
- **Explanatory use:** Identifying mechanisms ✓
- **Predictive use:** Conditional projections only — NOT precise point predictions ✗
- **Warning:** "High-fidelity outputs create an illusion of accuracy"

**Keywords:** Agent-based modeling, Generative Agent-Based Modeling, LLM-based Agent-based Modeling, Digital Twin, Social Digital Twin

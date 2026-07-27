---
source_url: https://arxiv.org/abs/2605.19745
ingested: 2026-07-27
sha256: TBD
---

# Making Uncertainty Visible: Multiverse Analysis for Robust Computational Social Science

**Authors:** Maximilian Linde, et al. (GESIS - Leibniz Institute for the Social Sciences)

**Date:** May 2026

**Subjects:** Other Statistics (stat.OT)

**License:** CC BY 4.0

## Abstract

Through case studies, we demonstrate how multiverse analysis can strengthen the robustness and transparency of computational social science findings against alternative methodological decisions. We conduct multiverse analyses of three published social science studies that use: Bayesian analysis, network generative modeling, and machine learning with or without large language models. These methods are applied frequently in computational social science studies, yet entail a greater degree of arbitrariness in terms of methodological choices, or "researcher degrees of freedom." Our multiverse analyses reveal how the empirical findings in these studies vary as a function of various plausible decision combinations. Our three case studies also expose an often-ignored motivation for conducting multiverse analysis: Showing which methodological combinations lead to computational failure. These failed cases are usually not communicated in the published reports, even though these sophisticated computational methods have a much higher likelihood of failure.

## Key Concepts

### Multiverse Analysis
Instead of reporting ONE analysis path, systematically explore ALL plausible decision combinations:
1. List all decisions that could possibly be varied
2. Find legitimate alternatives for these decisions
3. Extract plausible decision combinations
4. Conduct analyses for each remaining combination
5. Report the full distribution of results

### Researcher Degrees of Freedom
The phenomenon that results vary depending on which decisions were made in the research process (Simmons, Nelson, & Simonsohn, 2011). CSS has MORE degrees of freedom than traditional quantitative social science due to:
- Data preprocessing choices
- Parameter tuning
- Model selection
- Algorithm configuration

### Three Case Studies
1. **Bayesian analysis** study
2. **Network generative modeling** study
3. **ML with/without LLMs** study (Birkenmaier et al.)

### Key Finding: Computational Failure
A major motivation for multiverse analysis: showing WHICH methodological combinations lead to computational failure. These failures are rarely reported in published papers, despite sophisticated computational methods having higher failure likelihood.

## Related Methods
- Specification curve analysis
- Multimodel analysis
- Vibration analysis
- Computational model robustness analysis
- Extreme bounds analysis

## Implications for CSS
- CSS exhibits higher researcher degrees of freedom than traditional quantitative social science
- Multiverse analysis should become standard practice in CSS
- Transparency about methodological choices is essential
- Computational failures should be reported, not hidden

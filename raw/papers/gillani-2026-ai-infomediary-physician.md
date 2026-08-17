---
source_url: https://arxiv.org/abs/2608.14399
ingested: 2026-08-17
sha256: fa448a2a97bb894771e0f771bcee038269979a9b8c9396e74cfa521e7f7cfbcb
---

# Whose doctor does the AI recommend? An algorithm audit of reputation and demographic signals in large language model–assisted physician choice

###### Abstract

Background: Patients increasingly ask large language model
(LLM) assistants which doctor to see. These systems have become *AI
infomediaries*: algorithms that intermediate a person’s choice among other
people and thereby decide, silently and at scale, which physicians become
visible. What causally moves their recommendations, and whether physician
names signaling gender or ethnicity play a role, is undocumented, because
existing audits observe correlated real-world profiles from which causal
weights cannot be identified.

Objective: To estimate the causal effect of reputation
signals (patient rating, review volume and recency, feedback response,
hospital affiliation, visit fee, telehealth availability, years in practice),
name-signaled demographics, and list position on the probability that an LLM
recommends a physician.

Methods: Prespecified algorithm audit using a randomized
choice-based conjoint. Across three patient personas and nine prompt
paraphrases, each audited model chose among five synthetic family-medicine
physician cards whose attributes were independently randomized (3,024
choice sets; nine experimental arms probing decoding temperature, response
format, and presentation order). Physician gender and ethnicity were signaled
through names following correspondence-audit methodology. Average marginal
component effects (AMCEs) were estimated by linear probability models with
choice-set–clustered standard errors; effects are also expressed as
visit-fee equivalents.

Results: Across seven models (six open-weight;
gpt-4o-mini) and 40,068 scored responses, reputation signals dominate:
moving a rating from 3.9 to 4.7 raises choice probability by 31.4 pp (95%
CI 30.5–32.3) and a $90→\to$190 fee lowers it by 20.0 pp (CI
19.1–21.0). Demographic parity is rejected in an unexpected direction:
female-signaled names gain 2.5 pp (CI 1.8–3.2) and Hispanic-,
South-Asian–, and Black-signaled names gain 1.3–2.9 pp over
White-signaled names, tilts worth $7–$14 per visit in fee-equivalent
terms; being listed first is worth $11. Yet models mentioned gender or
ethnicity in ≤\leq0.03% of their stated reasons and abstained in 0.39% of
trials: the demographic and position effects were invisible in the models’
own explanations. A reasoning model (deepseek-r1:7b) failed the
prespecified auditability gate outright.

Conclusions: AI infomediaries neither reproduce the
anti-minority discrimination documented in human audit studies nor achieve
neutrality: they silently apply systematic demographic tilts of their own.
The divergence between revealed weights and stated reasons means
transparency obligations that rely on model self-report would not surface
these effects; only behavioral audits can. The
frozen design makes the audit repeatable: any new model can be assessed
against identical stimuli with a single command, converting this study from
a one-time snapshot into a recurring monitoring instrument for AI-mediated
access to care.

Keywords: large language models; algorithm audit;
algorithmic fairness; health equity; physician ratings; conjoint analysis;
patient choice; algorithmic gatekeeping; AI transparency; intersectional
bias; digital determinants of health; correspondence audit

## 1 Introduction

Choosing a doctor has always run on reputation. Patients weigh word of mouth,
online ratings, credentials, and cost, and a large literature documents how
these signals shape provider choice ([Hanauer et al. 2014](#bib.bib10); [Emmert et al. 2013](#bib.bib6); [Yaraghi et al. 2018](#bib.bib16)). A new intermediary has now inserted itself into that decision:
conversational assistants built on large language models (LLMs). Instead of
scanning a directory of physician profiles, a patient can simply ask an
assistant, “Which of these doctors should I book?” A growing share do, as
LLM assistants absorb search, comparison, and triage tasks that
previously belonged to rating platforms and search engines
([Ayers et al. 2023](#bib.bib2)). When an assistant answers, it collapses a multi-attribute
comparison into a single recommendation. The weights it applies, whether to
a star rating, a consultation fee, a hospital affiliation, or, more
troublingly, to a physician’s name, take effect silently, at scale, and
without any of the professional accountability that governs human referral.
The assistant has become an *AI infomediary*: an algorithm that
intermediates one person’s choice among other people, and in doing so
allocates visibility, and ultimately patients, across physicians.

This paper asks a simple causal question: *what moves an LLM’s physician
recommendation?* We answer it with a prespecified algorithm audit
([Sandvig et al. 2014](#bib.bib15); [Metaxa et al. 2021](#bib.bib11)) built on a randomized choice-based conjoint
design ([Hainmueller et al. 2014](#bib.bib9)). Audited models repeatedly choose among five
synthetic family-medicine physician cards whose attributes are independently
randomized: patient rating, review volume, review recency, whether the
practice responds to feedback, hospital-system affiliation, new-patient visit
fee, telehealth availability, years in practice, and gender and ethnicity,
which are signaled through physician names using correspondence-audit
methodology ([Bertrand and Mullainathan 2004](#bib.bib4); [Gaddis 2017](#bib.bib7)). Because every attribute varies
independently of every other and of display order, differences in choice
probability identify the average marginal component effect (AMCE) of each
signal, and the fee attribute converts any effect into an interpretable
dollars-per-visit equivalent.

The design speaks to three literatures at once. First, it extends the
economics of online physician reputation ([Gao et al. 2012](#bib.bib8); [Yaraghi et al. 2018](#bib.bib16)) from
human choosers to algorithmic ones: prior conjoint evidence shows how
*patients* trade off ratings and other attributes; we provide the
matching causal estimates for the AI assistants now advising them. Second, it
extends the algorithmic-fairness literature in health care
([Obermeyer et al. 2019](#bib.bib12); [Zack et al. 2024](#bib.bib17); [Omiye et al. 2023](#bib.bib13)), which has concentrated on
clinical decisions (triage, diagnosis, treatment), to the consumer-facing
question of *which humans the algorithm makes visible*. Existing audits
of chatbot specialist recommendations are descriptive, asking models to name
real physicians and characterizing who appears ([Parikh et al. 2024](#bib.bib14)); because real
physicians’ attributes are correlated, such designs cannot separate a rating
effect from a name effect. Our synthetic-profile randomization can. Third, it
contributes to the emerging study of AI infomediaries and generative engine
optimization ([Aggarwal et al. 2024](#bib.bib1)), where a companion audit in the travel
domain ([Baig et al. 2026](#bib.bib3)) found that assistants reproduce human valence-price
primacy while introducing content-free position effects; identical rating and
recency levels here permit the first cross-domain comparison of LLM
signal weights.

Concretely, we make four contributions. (1) We provide, to our knowledge, the
first randomized conjoint audit of LLM physician recommendation, across a
panel of widely deployed models, three patient personas, nine prompt
paraphrases, and nine prespecified experimental arms. (2) We estimate
fee-equivalent values for every signal, including the dollar value of a
first-listed position and of name-signaled demographic attributes, with
uncertainty quantified by cluster-robust inference and Krinsky–Robb
simulation. (3) We test demographic parity directly, at the group level and
at the intersection of gender and ethnicity, using prespecified equivalence
bounds, so that a null is informative rather than merely underpowered, and
we characterize when models abstain from choosing or spontaneously flag
demographic attributes. (4) We compare the models’ *stated* reasons against their
*revealed* weights, quantifying how faithfully AI explanations track AI
behavior in a health context. Beyond these estimates, the
frozen-design instrument makes every finding falsifiable and repeatable:
auditing any future model against identical stimuli is a single command, so
the parity verdicts reported here can be re-issued, or revoked, with each
model release.

Across seven models and 40,068 scored responses, three findings emerge.
First, LLM recommenders run on reputation: patient rating alone carries
37.7% of total attribute importance and fee 24.1%, with a 3.9→\to4.7
rating step worth $157 per visit in fee-equivalent terms. Second,
demographic parity fails, but not in the direction human audit studies
would predict: female-signaled and minority-signaled names *gain* one
to three percentage points, tilts worth $7–$14 per visit, and no
gender×\timesethnicity cell meets the prespecified equivalence bound.
Third, none of this is visible in the models’ own explanations: gender and
ethnicity appear in fewer than 0.03% of stated reasons, and models
abstained from choosing in only 0.39% of trials, so the demographic and
position effects operate entirely below the models’ self-reported
rationale.

The remainder of the paper reviews the relevant literatures and derives
hypotheses (Section 2), details the design, model panel, and estimation
strategy (Section 3), reports results (Section 4), and discusses implications
for platforms, regulators, and health-services research (Section 5).

## 2 Background and hypotheses

### 2.1 Online reputation and physician choice

Physician-rating websites have made service reputation legible in health
care. Public awareness and use of these ratings grew rapidly through the
2010s ([Hanauer et al. 2014](#bib.bib10)), physician coverage on rating platforms expanded in
parallel ([Gao et al. 2012](#bib.bib8)), and systematic reviews document that valence and
volume of reviews influence patients’ stated willingness to select a provider
([Emmert et al. 2013](#bib.bib6)). The causal benchmark most relevant to our design is
[Yaraghi et al. 2018](#bib.bib16), a choice-based conjoint in which patients chose between
physician profiles with randomized quality ratings: higher ratings raised
choice odds substantially, and nonclinical (service) ratings mattered
alongside clinical ones. Beyond ratings, patients weigh access attributes
(wait time, fees, telehealth) and credential attributes (experience,
affiliation) in ways that vary with their situation: an uninsured patient
weighs fees differently from a chronically ill one. Our persona manipulation
mirrors that heterogeneity.

If LLM assistants have internalized the regularities of human choice
documented in this literature, as their training corpora suggest they
should, their revealed weights should reproduce the canonical ordering:
valence first, then price, with secondary signals (volume, recency,
responsiveness, affiliation, experience, telehealth) positive but smaller.
Hypotheses H1–H8 formalize this expectation attribute by attribute
(Table [4](#S4.T4 "Table 4 ‣ 4.2 What moves the recommendation: AMCEs ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice") lists the full prespecified family):
higher patient ratings (H1), more reviews (H2), more recent reviews (H3),
practices that respond to feedback (H4), university-hospital affiliation
(H5), lower visit fees (H6), telehealth availability (H7), and more years in
practice (H8) each increase the probability of recommendation.

### 2.2 Names as treatments: discrimination audits meet AI advice

Correspondence audits established that names alone shift decisions: résumés
signed “Emily” or “Greg” received 50% more callbacks than identical
résumés signed “Lakisha” or “Jamal” ([Bertrand and Mullainathan 2004](#bib.bib4)), and the
methodology for selecting demographically distinctive names is now standard
([Gaddis 2017](#bib.bib7)). Field experiments extended the finding to platform
markets ([Edelman et al. 2017](#bib.bib5)). In health care specifically, algorithmic systems
have repeatedly encoded group disparities: a widely used care-management
algorithm systematically under-referred Black patients ([Obermeyer et al. 2019](#bib.bib12)),
and LLMs have been shown to propagate race-based medicine
([Omiye et al. 2023](#bib.bib13)) and to generate clinical vignettes and treatment
recommendations that vary with patient demographics ([Zack et al. 2024](#bib.bib17)).

That literature concerns the algorithm’s treatment of *patients*. The
question here is different and unexamined: when the algorithm chooses among
*physicians*, does a name signaling gender or ethnicity move the
recommendation, holding every reputational attribute fixed? Three outcomes
are possible, and all are informative. The assistant may reproduce human
discrimination absorbed from training data; it may be neutral, because
alignment training suppresses demographic reasoning; or it may overcorrect.
We therefore prespecify parity nulls with equivalence bounds rather than
directional predictions: name-signaled gender (H9) and ethnicity (H10) have
no effect on recommendation probability, tested jointly across the panel and
bounded by two one-sided tests at ±\pm1.5 percentage points. Because
demographic effects in health care are often intersectional, with
clinical-bias audits reporting disparities for specific
gender×\timesethnicity combinations that neither main effect anticipates
([Zack et al. 2024](#bib.bib17)), we additionally test
whether the two signals combine additively (H13) and estimate all ten
gender×\timesethnicity cell effects. Finally, an abstention is not
necessarily a defect: when only names distinguish otherwise-comparable
physicians, a model that declines to choose behaves more defensibly than one
that silently lets names decide. We therefore treat abstention and whether
responses explicitly acknowledge demographic attributes as outcomes in their
own right.

### 2.3 Position, personas, and explanation faithfulness

Two further properties of LLM choice behavior carry over from algorithm
audits outside health. First, display position: retrieval and recommendation
interfaces reward rank, and our companion travel-domain audit
([Baig et al. 2026](#bib.bib3)) found a causal first-listed advantage worth real money per
booking. Because position is content-free, any position effect in physician
recommendation is a pure artifact of the medium, consequential for
provider-directory platforms whose orderings feed AI assistants. Second,
context sensitivity: H11 predicts that the fee penalty is larger for a
persona paying out of pocket, and H12 that review volume moderates the rating
effect (a 4.7 average over 400 reviews is more diagnostic than over 12
([Yaraghi et al. 2018](#bib.bib16))). Finally, models explain their picks on request, but
stated reasons need not track revealed weights; in the travel audit they
tracked imperfectly ([Baig et al. 2026](#bib.bib3)). We quantify that gap here, with
particular attention to whether demographic attributes that move choices are
ever *mentioned* in explanations, the failure mode with the clearest
governance implications.

## 3 Methods

### 3.1 Design overview

We conducted a randomized choice-based conjoint embedded in an algorithm
audit. Each trial presented one audited model with a persona, a prompt
template, and five synthetic physician cards, and asked it to recommend one.
Cards described board-certified family-medicine physicians accepting new
patients with a practice near the user (all held constant), while eight
reputational attributes varied independently and uniformly at random per
card: patient rating (3.9, 4.3, or 4.7 of 5), number of reviews (12, 85, or
400), most recent review (3 days or 11 months ago), whether the practice
responds to patient feedback (present or absent), affiliation (university
hospital system vs. independent practice), new-patient visit fee ($90,
$140, or $190), telehealth availability (present or absent), and years in
practice (8, 18, or 28).
Rating and recency levels replicate our travel-domain audit ([Baig et al. 2026](#bib.bib3))
to permit cross-domain comparison. Display order (slot 1–5) was randomized
independently of content, identifying list-position effects.
Figure [1](#S3.F1 "Figure 1 ‣ 3.1 Design overview ‣ 3 Methods ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice") summarizes the pipeline from frozen design to
inference; Figure [2](#S3.F2 "Figure 2 ‣ 3.1 Design overview ‣ 3 Methods ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice") shows one card verbatim.

Physician gender (female/male) and ethnicity (White, Black, Hispanic, East
Asian, South Asian) were randomized per card and signaled through names
(“Dr. Priya Sharma”), with four first names and four surnames per
gender×\timesethnicity cell drawn from the correspondence-audit tradition
([Bertrand and Mullainathan 2004](#bib.bib4); [Gaddis 2017](#bib.bib7)). Analysis is at the cell level; a
prespecified placebo tests that the specific name exemplar within a cell has
no effect. Within a choice set, no two cards shared a surname or a full
attribute profile.

### 3.2 Stimuli, personas, and arms

Prompts crossed three patient personas (new in town; managing a chronic
condition; uninsured and paying out of pocket) with nine paraphrased
templates, and requested a JSON response naming the chosen physician and a
one-to-two-sentence reason. The design comprises 3,024 main-arm choice sets
(112 per persona×\timestemplate stratum), fixed across all audited models:
every model sees identical stimuli, so model comparisons are within-trial.
Eight prespecified secondary arms re-present stratified subsets of the same
trials under altered conditions: temperature 0 (594 trials), grounded
web-snippet formatting (297), top-3 ranking (297), reason-before-choice field
order (189), five-repetition test–retest (108), a letter-labeled logprob arm
separating position from letter-token preference (297), a persona-free
control (297), and reversed card-line order (189). A 20-repetition
manipulation check asked each model to define board certification. The design
matrix was generated once (seed 20260702), hashed (SHA-256), and frozen
before any non-pilot model call, and the analysis plan (hypotheses,
estimators, equivalence bounds, and exclusion rules) was written and fixed
before any confirmatory data were analyzed.

### 3.3 Model panel and execution

The audited panel comprises six widely deployed open-weight
instruction-tuned models executed locally via Ollama (llama3.2:3b,
qwen2.5:3b, phi3:mini, mistral:7b-instruct-q4\_K\_M, gemma3:4b, and
llama3.1:8b) and one proprietary production model (gpt-4o-mini, accessed
through an Azure OpenAI deployment, API version 2025-01-01-preview) under
the identical protocol, including seed control and, on the letter arm,
token-level log probabilities; exact identifiers and inference dates are
recorded in the design metadata. A seventh open-weight candidate, deepseek-r1:7b, was
subject to a prespecified pilot gate and excluded before full-run
collection (Results). Generation used
temperature 0.7 (top-pp 0.9) except in the temperature arm, with
per-call deterministic seeds derived from (model, arm, trial, repetition).
Responses failing JSON parsing or naming no listed physician were retried up
to twice with a stricter reminder; remaining failures are analyzed as
missingness (prespecified exclusion of model×\timesarm cells exceeding 5%
failure). All calls are checkpointed and the pipeline is resume-safe.

### 3.4 Exploratory frontier-model pilot and archived forecasts

Because API access to frontier models was not available at collection time, we
additionally piloted four Claude-family models (claude-haiku-4-5,
claude-sonnet-5, claude-opus-4-8, claude-fable-5) on the first 50 main-arm
choice sets of the frozen design. These responses were *not* collected
under the audit protocol above: they were gathered interactively inside an
agentic coding environment (Claude Code, Anthropic), one fresh subagent per
trial with no shared context, using the pipeline’s own stimulus renderer and
parser (verbatim frozen prompts; one stricter re-ask on unparseable output;
0/200 parse failures). This collection mode leaves decoding parameters at the
harness defaults rather than the protocol’s temperature 0.70.7/top-pp 0.90.9,
embeds each response in an agent system prompt rather than a bare API call,
and is not seed-reproducible. The 200 resulting records are therefore
quarantined from the analysis pipeline, enter no confirmatory test, and are
reported only descriptively (Table [10](#S4.T10 "Table 10 ‣ 4.9 Exploratory: frontier-model session pilot ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")).

We put this pilot to a second, falsifiable use. For each piloted model we fit
a conditional logit to its 50 choice sets and computed out-of-sample forecast
probabilities of being chosen for every card in all 3,024 main-arm choice
sets. These forecasts, which are model-based extrapolations rather than
observations, were
archived, with a timestamp, *before* any full API run of these
models, so that a subsequent protocol-compliant run (claude-haiku-4-5 is the
designated target) can grade them: agreement would suggest small
harness-contaminated pilots cheaply approximate full audits; disagreement
would itself measure the harness and decoding effects described above.

### 3.5 Estimation

The estimand is the AMCE of each attribute level on the probability of
being recommended ([Hainmueller et al. 2014](#bib.bib9)). Primary estimator: linear
probability regression of an indicator for being chosen on attribute-level
dummies and slot dummies, with standard errors clustered on choice set,
estimated per model and pooled with model fixed effects. Secondary:
conditional (McFadden) logit per choice set. Thirteen prespecified hypotheses
are tested by joint Wald tests with Holm correction; demographic parity
hypotheses (H9–H10) are additionally assessed by two one-sided tests with a
smallest-effect-size-of-interest of ±\pm1.5 percentage points, and are
pooled estimands, because a Monte-Carlo precision analysis showed per-model power
for plausible demographic effect sizes is inadequate, whereas the pooled
panel yields a minimum detectable effect below 1 percentage point. Because a
linear-probability interaction can be nonzero under a purely additive
logit process, H12 is corroborated only if the conditional-logit interaction
agrees in sign and significance. H13 tests intersectionality, that is,
whether name-signaled gender and ethnicity combine additively, as a joint test of
their interaction terms; we additionally report all ten gender×\timesethnicity
cell effects relative to the White-male reference, each with an equivalence
verdict. Separately and descriptively, we classify each response as an
abstention (declining to choose) and as demographic-aware (referring to a
physician’s name, gender, ethnicity, or race), the latter measuring how often
a model’s own words reveal that a name-signaled attribute was salient. Fee-equivalents divide each AMCE by the
per-dollar fee AMCE (linearized over the $100 range), with 95% intervals by
Krinsky–Robb simulation (10,000 draws), gated on monotonicity of the fee
response. Stated reasons are coded for attribute mentions by a validated
dictionary and an independent judge model (gemma2:2b, excluded from the
audited panel), and compared with revealed importance shares.

### 3.6 Validation and reproducibility

The complete pipeline (stimulus rendering, execution, parsing, and every
analysis module) was validated end-to-end against a mock data-generating
process with known conditional-logit effects, including planted name-signaled
effects (female +0.10+0.10; Black −0.15-0.15 on the logit scale) and true-null
ethnicity effects. The validation suite (18 assertions) confirms recovery of
signs, magnitudes, true nulls, the fee-monotonicity gate, the name-exemplar
placebo, and figure/table generation. Every call is checkpointed, and the
frozen design matrices are hash-verified at load time, so a full audit is
reproducible from the design seed. All physician identities are
synthetic, and the demographic manipulation audits model behavior, not real
physicians.

## 4 Results

### 4.1 Data quality and manipulation checks

The confirmatory panel comprises seven models: six open-weight
instruction-tuned models (llama3.2:3b, qwen2.5:3b, phi3:mini,
mistral:7b-instruct, gemma3:4b, llama3.1:8b) and one proprietary production
model (gpt-4o-mini, accessed via Azure OpenAI), yielding 40,068 scored
responses across the nine arms. Parse-failure rates were 0% for gpt-4o-mini
on every arm and below 2% for nearly all model–arm cells
(Table [1](#S4.T1 "Table 1 ‣ 4.1 Data quality and manipulation checks ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")); the exceptions were mistral on the retest (32.0%)
and top-3 ranking (14.1%) arms, which enter the missingness analysis in
Section 4.7. An eighth candidate, deepseek-r1:7b, failed its prespecified
pilot gate (100% parse failures: its chain-of-thought exhausted the fixed
output budget before emitting the required JSON) and was excluded before any
full-run data were collected. This is itself a finding about the auditability of
reasoning models under fixed-format protocols. Test–retest consistency was
high: the modal choice was repeated in 73% (mistral) to 99% (gemma3) of
five-fold repetitions (Table [2](#S4.T2 "Table 2 ‣ 4.1 Data quality and manipulation checks ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")).

| Model | card\_reversed | field\_order | grounded | letter | main | nopersona | rank\_top3 | retest | temp0 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| gemma3:4b | 0.0 | 0.0 | 0.0 | 0.0 | 0.8 | 0.0 | 0.0 | 0.0 | 0.0 |
| gpt-4o-mini | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |
| llama3.1:8b | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |
| llama3.2:3b | 0.0 | 0.0 | 0.0 | 1.7 | 0.0 | 0.0 | 0.7 | 0.0 | 0.0 |
| mistral:7b-instruct-q4\_K\_M | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 14.1 | 32.0 | 0.0 |
| phi3:mini | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 7.1 | 0.0 | 0.0 |
| qwen2.5:3b | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |

Note. Parse-failure rate (%) by model and arm; pilot and manipulation-check calls excluded.

| Model | Modal share | Entropy |
| --- | --- | --- |
| gemma3:4b | 0.993 | 0.015 |
| gpt-4o-mini | 0.967 | 0.064 |
| llama3.1:8b | 0.919 | 0.155 |
| llama3.2:3b | 0.856 | 0.295 |
| mistral:7b-instruct-q4\_K\_M | 0.732 | 0.560 |
| phi3:mini | 0.822 | 0.368 |
| qwen2.5:3b | 0.865 | 0.274 |

Note. Mean over test–retest choice sets (5 repetitions each).

### 4.2 What moves the recommendation: AMCEs

Reputation signals dominate (Figure [3](#S4.F3 "Figure 3 ‣ 4.2 What moves the recommendation: AMCEs ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice");
Table [3](#S4.T3 "Table 3 ‣ 4.2 What moves the recommendation: AMCEs ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")). Pooled across
models, moving a card’s rating from 3.9 to 4.7 raises its choice probability
by 31.4 percentage points (pp) against a 20% baseline (95% CI
30.5–32.3); raising the fee from $90 to $190 lowers it by 20.0 pp (CI
19.1–21.0). Review volume (400 vs. 12 reviews: +8.4+8.4 pp), review recency
(+3.8+3.8 pp), telehealth availability (+2.8+2.8 pp), responding to feedback
(+2.1+2.1 pp), and 28 vs. 8 years in practice (+2.1+2.1 pp) all move choices in
the expected direction. Hospital-system affiliation does not (+0.3+0.3 pp,
P=.35P=.35), the lone prespecified reputation hypothesis (H5) not supported.
In share-of-importance terms, rating accounts for 37.7% of the total
attribute range, price 24.1%, volume 10.1%, and list position 8.2%
(Table [5](#S4.T5 "Table 5 ‣ 4.2 What moves the recommendation: AMCEs ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")). Confirmatory hypotheses H1–H4 and H6–H8 were
all supported after Holm correction (Table [4](#S4.T4 "Table 4 ‣ 4.2 What moves the recommendation: AMCEs ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")).

| Attribute | AMCE (pp) | 95% CI | PP |
| --- | --- | --- | --- |
| Rating 4.3 (vs 3.9) | 8.06 | [7.34, 8.78] | ¡.001 |
| Rating 4.7 (vs 3.9) | 31.38 | [30.48, 32.29] | ¡.001 |
| 85 reviews (vs 12) | 4.79 | [3.93, 5.64] | ¡.001 |
| 400 reviews (vs 12) | 8.44 | [7.56, 9.31] | ¡.001 |
| Recent review (vs 11 mo.) | 3.80 | [3.09, 4.51] | ¡.001 |
| Responds to patient feedback | 2.09 | [1.37, 2.80] | ¡.001 |
| Hospital-affiliated (vs independent) | 0.34 | [-0.37, 1.04] | .349 |
| \{}$140 fee (vs \{}$90) | -14.46 | [-15.45, -13.46] | ¡.001 |
| \{}$190 fee (vs \{}$90) | -20.02 | [-20.96, -19.08] | ¡.001 |
| Telehealth available | 2.78 | [2.08, 3.49] | ¡.001 |
| 18 yrs in practice (vs 8) | 0.85 | [-0.01, 1.72] | .052 |
| 28 yrs in practice (vs 8) | 2.08 | [1.21, 2.96] | ¡.001 |
| Female name (vs male) | 2.51 | [1.81, 3.20] | ¡.001 |
| Black name (vs White) | 1.33 | [0.25, 2.42] | .016 |
| Hispanic name (vs White) | 2.81 | [1.69, 3.93] | ¡.001 |
| East Asian name (vs White) | 0.25 | [-0.84, 1.34] | .653 |
| South Asian name (vs White) | 2.88 | [1.74, 4.01] | ¡.001 |
| Position 2 (vs 1) | 0.68 | [-0.54, 1.89] | .274 |
| Position 3 (vs 1) | -0.23 | [-1.42, 0.97] | .711 |
| Position 4 (vs 1) | -3.31 | [-4.48, -2.14] | ¡.001 |
| Position 5 (vs 1) | -6.15 | [-7.26, -5.04] | ¡.001 |

| Hypothesis | Wald | df | PP (raw) | PP (Holm) |
| --- | --- | --- | --- | --- |
| H1\_rating | 4636.25 | 2 | ¡.001 | ¡.001\*\*\* |
| H2\_volume | 363.61 | 2 | ¡.001 | ¡.001\*\*\* |
| H3\_recency | 111.31 | 1 | ¡.001 | ¡.001\*\*\* |
| H4\_response | 32.42 | 1 | ¡.001 | ¡.001\*\*\* |
| H5\_network | 0.88 | 1 | .349 | .349 |
| H6\_price | 1745.92 | 2 | ¡.001 | ¡.001\*\*\* |
| H7\_telehealth | 59.80 | 1 | ¡.001 | ¡.001\*\*\* |
| H8\_experience | 22.08 | 2 | ¡.001 | ¡.001\*\*\* |
| H9\_gender | 49.90 | 1 | ¡.001 | ¡.001\*\*\* |
| H10\_ethnicity | 44.67 | 4 | ¡.001 | ¡.001\*\*\* |
| H11\_persona\_x\_price | 834.63 | 6 | ¡.001 | ¡.001\*\*\* |
| H12\_rating\_x\_volume | 170.90 | 4 | ¡.001 | ¡.001\*\*\* |
| H13\_intersectional | 9.51 | 4 | .050 | .099 |

Note. Holm-corrected over the H1–H12 confirmatory family. ∗p<.05{}^{\*}p<.05, p∗⁣∗<.01{}^{\*\*}p<.01, ∗∗∗p<.001{}^{\*\*\*}p<.001.

| Attribute | Range (pp) | Share |
| --- | --- | --- |
| Patient rating | 31.38 | 0.377 |
| Visit fee | 20.02 | 0.241 |
| Review volume | 8.44 | 0.101 |
| List position | 6.83 | 0.082 |
| Recency | 3.80 | 0.046 |
| Ethnicity (name-signaled) | 2.88 | 0.035 |
| Telehealth | 2.78 | 0.033 |
| Gender (name-signaled) | 2.51 | 0.030 |
| Feedback response | 2.09 | 0.025 |
| Experience | 2.08 | 0.025 |
| Affiliation | 0.34 | 0.004 |

### 4.3 Name-signaled gender and ethnicity

Demographic parity is rejected, in a direction the bias literature would
not predict. Physician cards bearing female-signaled names were chosen 2.5
pp more often than male-signaled ones (CI 1.8–3.2; H9 PHolm<.001P\_{\text{Holm}}<.001), and ethnicity effects are jointly significant (H10
PHolm<.001P\_{\text{Holm}}<.001): relative to White-signaled names,
Hispanic-signaled (+2.8+2.8 pp), South-Asian–signaled (+2.9+2.9 pp), and
Black-signaled (+1.3+1.3 pp) names were chosen *more* often, with
East-Asian–signaled names indistinguishable from White (+0.3+0.3 pp,
P=.65P=.65). The conditional-logit specification corroborates the linear
estimates (pooled odds ratios 1.22 for female, 1.15–1.24 for the elevated
ethnicity cells). Because the prespecified TOST bounds of ±\pm1.5 pp are
excluded by several of these intervals, the correct summary is not
“parity holds” but “models exhibit a systematic *pro-female,
pro-minority* tilt of one to three percentage points.” The prespecified
name-exemplar placebo, however, is violated: choice shares differ across
name exemplars *within* gender×\timesethnicity cells (LR =370.0=370.0,
df =30=30, P<.001P<.001), so cell-level effects should be read as
perceived-category effects entangled with name-specific familiarity, and
the demographic estimates as audit-level signals rather than precise
category parameters.

#### 4.3.1 Intersectional effects

The gender×\timesethnicity interaction is not jointly significant after
correction (H13, PHolm=.099P\_{\text{Holm}}=.099), indicating approximately additive
effects, but the additive combination concentrates advantage: relative to
White-male cards, female-Hispanic cards gain 5.7 pp (CI 4.0–7.3),
female–South-Asian 5.1 pp, and female-Black 3.9 pp
(Table [6](#S4.T6 "Table 6 ‣ 4.3.1 Intersectional effects ‣ 4.3 Name-signaled gender and ethnicity ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")). No cell meets the prespecified
equivalence criterion, so no gender×\timesethnicity combination can be
certified as neutrally treated.

| Gender ×\times ethnicity cell | AMCE (pp) | 95% CI | PP | TOST PP |
| --- | --- | --- | --- | --- |
| White male (ref.) | 0.00 | – | – | – |
| Black male | 0.52 | [-1.02, 2.05] | .510 | .104 |
| Hispanic male | 1.74 | [0.19, 3.30] | .028 | .620 |
| East Asian male | 0.77 | [-0.79, 2.32] | .333 | .177 |
| South Asian male | 2.41 | [0.81, 4.01] | .003 | .868 |
| White female | 1.81 | [0.26, 3.35] | .022 | .651 |
| Black female | 3.93 | [2.39, 5.46] | ¡.001 | .999 |
| Hispanic female | 5.65 | [4.04, 7.27] | ¡.001 | 1.000 |
| East Asian female | 1.46 | [-0.06, 2.99] | .060 | .482 |
| South Asian female | 5.12 | [3.50, 6.74] | ¡.001 | 1.000 |

Note. Effect of each name-signaled cell vs. White male, from a single 10-level categorical (choice-set–clustered SEs). TOST p<.05p<.05 indicates statistical equivalence within ±\pm1.5 pp.

#### 4.3.2 Abstention and demographic-aware responses

Abstention is rare and indiscriminate: models declined to choose in 0.39%
of responses overall, and spontaneously flagged demographic attributes in
only 0.01% (Table [7](#S4.T7 "Table 7 ‣ 4.3.2 Abstention and demographic-aware responses ‣ 4.3 Name-signaled gender and ethnicity ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")). The models that let names move
their choices essentially never said so.

| Model | nn | Abstain (%) | Demographic-aware (%) |
| --- | --- | --- | --- |
| gemma3:4b | 3024 | 0.0 | 0.0 |
| gpt-4o-mini | 3024 | 0.0 | 0.0 |
| llama3.1:8b | 3024 | 0.1 | 0.0 |
| llama3.2:3b | 3024 | 0.0 | 0.0 |
| mistral:7b-instruct-q4\_K\_M | 3024 | 0.6 | 0.0 |
| phi3:mini | 3024 | 1.2 | 0.1 |
| qwen2.5:3b | 3024 | 0.2 | 0.0 |

Note. Main arm. *Abstain* = declines to choose or calls the options equal; *demographic-aware* = the response text refers to a physician’s name, gender, ethnicity, or race.

### 4.4 Position effects

Position effects are content-free and economically meaningful: cards in
slot 5 lose 6.2 pp (CI 5.0–7.3) and slot 4 loses 3.3 pp relative to slot
1, holding all content constant (Figure [5](#S4.F5 "Figure 5 ‣ 4.4 Position effects ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")). The letter-labeled arm decomposes
label from position using gpt-4o-mini token logprobs: both components are
small in isolation (partial R2=.005R^{2}=.005 for slot given letter, .008.008 for
letter given slot), with a residual anti-“E” letter preference (−7.3-7.3
pp, P=.03P=.03) (Table [8](#S4.T8 "Table 8 ‣ 4.4 Position effects ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")).

| Term | Coef. (pp) | SE (pp) | PP |
| --- | --- | --- | --- |
| Position 2 (vs 1) | 4.42 | 3.50 | .206 |
| Position 3 (vs 1) | 7.95 | 3.59 | .027 |
| Position 4 (vs 1) | 3.99 | 3.44 | .246 |
| Position 5 (vs 1) | 1.24 | 3.30 | .707 |
| Letter B (vs A) | 0.82 | 3.68 | .824 |
| Letter C (vs A) | 2.90 | 3.75 | .438 |
| Letter D (vs A) | -0.73 | 3.61 | .839 |
| Letter E (vs A) | -7.28 | 3.26 | .025 |

Note. Position block incremental R2R^{2} = 0.0050; letter-token block = 0.0077. Slot and letter are independently randomized by design.

### 4.5 Fee-equivalents

Converting effects through the fee gradient (monotonic, as required by the
prespecified gate) prices each signal in dollars per visit
(Table [9](#S4.T9 "Table 9 ‣ 4.5 Fee-equivalents ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")). The 3.9→\to4.7 rating step is worth $157 per
visit (CI 147–167); recency $19; telehealth $14; responding to feedback
$10. The demographic tilts are worth real money: a female-signaled name is
equivalent to a $12.50 fee discount (CI 9–16), Hispanic- and
South-Asian–signaled names to $14, and being listed first to $11 per
visit, a pure interface artifact priced like a clinical credential.

| Attribute | Pooled | New in town | Chronic care | Budget |
| --- | --- | --- | --- | --- |
| Rating 4.3 (vs 3.9) | 40.3 [36.1, 44.6] | 85.2 [72.5, 100.4] | 93.0 [78.8, 110.0] | 14.2 [10.3, 18.1] |
| Rating 4.7 (vs 3.9) | 156.8 [147.4, 167.2] | 366.4 [321.9, 425.1] | 343.5 [301.3, 396.6] | 46.5 [42.1, 51.1] |
| 85 reviews (vs 12) | 23.9 [19.4, 28.5] | 66.6 [52.4, 83.1] | 57.3 [43.3, 73.3] | 4.3 [0.4, 8.2] |
| 400 reviews (vs 12) | 42.2 [37.2, 47.3] | 106.5 [89.4, 127.1] | 105.9 [89.0, 126.2] | 7.6 [3.6, 11.7] |
| Recent review (vs 11 mo.) | 19.0 [15.4, 22.7] | 42.6 [31.3, 55.6] | 41.8 [30.6, 54.2] | 6.8 [3.5, 10.0] |
| Responds to patient feedback | 10.4 [6.9, 14.1] | 13.7 [3.0, 25.1] | 22.3 [11.7, 33.0] | 5.7 [2.3, 9.1] |
| Hospital-affiliated (vs independent) | 1.7 [-1.8, 5.2] | 10.4 [0.0, 21.7] | 19.1 [8.5, 30.4] | -5.8 [-8.9, -2.7] |
| Telehealth available | 13.9 [10.3, 17.5] | 25.6 [14.9, 37.0] | 28.8 [18.8, 40.1] | 6.1 [2.9, 9.4] |
| 18 yrs in practice (vs 8) | 4.3 [-0.1, 8.5] | 13.3 [0.4, 26.6] | 7.5 [-4.9, 20.3] | 2.8 [-1.0, 6.7] |
| 28 yrs in practice (vs 8) | 10.4 [6.1, 14.9] | 21.0 [8.0, 34.9] | 31.3 [18.4, 45.0] | 3.1 [-0.9, 7.0] |
| Female name (vs male) | 12.5 [9.0, 16.0] | 31.4 [20.9, 43.3] | 28.0 [18.0, 39.2] | 2.4 [-0.8, 5.6] |
| Black name (vs White) | 6.7 [1.3, 12.2] | 5.0 [-11.0, 21.3] | 18.7 [3.0, 35.4] | 5.4 [0.5, 10.4] |
| Hispanic name (vs White) | 14.1 [8.4, 19.8] | 28.6 [12.3, 46.0] | 17.4 [1.0, 34.7] | 8.9 [3.5, 14.1] |
| East Asian name (vs White) | 1.2 [-4.3, 6.8] | -0.2 [-15.7, 15.2] | 2.8 [-12.5, 18.6] | 1.0 [-4.3, 6.1] |
| South Asian name (vs White) | 14.3 [8.7, 20.3] | 23.3 [6.6, 40.6] | 23.2 [6.7, 40.9] | 8.3 [3.0, 13.6] |
| First-listed (vs avg 2-5) | 11.3 [6.5, 16.0] | 39.3 [24.9, 55.0] | 19.9 [7.0, 33.3] | 0.0 [-3.7, 3.7] |

### 4.6 Persona and interaction effects

Fee sensitivity is persona-dependent (H11, PHolm<.001P\_{\text{Holm}}<.001): the uninsured persona’s price penalty far exceeds the insured
personas’ (Figure [6](#S4.F6 "Figure 6 ‣ 4.6 Persona and interaction effects ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")). Rating and volume interact (H12,
PHolm<.001P\_{\text{Holm}}<.001), with high volume amplifying the high-rating
premium (Figure [7](#S4.F7 "Figure 7 ‣ 4.6 Persona and interaction effects ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")); the sign replicates in the
conditional logit, though probability-scale interactions under a
logit-additive process must be interpreted cautiously (Methods).

### 4.7 Stated versus revealed importance

Stated reasons track reputation but conceal demographics and position
(Figure [8](#S4.F8 "Figure 8 ‣ 4.7 Stated versus revealed importance ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice"); 21,143 coded reasons). Rating is mentioned in 57–91% of
reasons across models and price in 42–56%, roughly commensurate with
their revealed weights. Gender is mentioned in ≤0.03%\leq 0.03\% of reasons and
ethnicity in ≤0.03%\leq 0.03\%, against revealed importance shares of 3.0% and
3.5%, and position in ≤4%\leq 4\% against a revealed share of 8.2%. An
explanation mandate that relied on model self-report would have detected
none of the demographic or position effects measured here.

### 4.8 Robustness

The reputation hierarchy is stable across every prespecified perturbation
(Figure [9](#S4.F9 "Figure 9 ‣ 4.8 Robustness ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")): grounded web-snippet formatting, reversed
card layout, field order, and the plausibility-filtered subsample each
shift headline AMCEs by at most a few points without sign changes, and
temperature-0 decoding reproduces the ordering.
Removing the persona raises rating weight (+8.4+8.4 pp on the 4.7 step) and
halves the fee penalty (−9.7-9.7 pp), consistent with personas carrying real
budget information. The missingness model finds parse failures unrelated to
card content. The gate-excluded deepseek-r1 and the mistral retest arm
are the only material data-quality caveats.

### 4.9 Exploratory: frontier-model session pilot

To extend the audit’s reach beyond open-weight models, four frontier
Claude-family models were piloted on the first 50 choice sets of the same
frozen design, and quantitative forecasts of their full-run behavior were
archived before any full-scale measurement (Methods). All four models
completed the pilot with no parse failures (200/200 calls; collection
caveats in Methods; numbers from
results/tables/pilot\_frontier.csv). Descriptively, the pilot
reproduces the reputation-signal ordering: cards rated 4.7 were chosen
39–43% of the time against a 20% null while cards rated 3.9 were chosen
0–1%, the $90 fee roughly quintupled choice share relative to $190
(35–37% vs. 5–8%), and higher review volume and recency moved choice in
the expected directions in all four models
(Table [10](#S4.T10 "Table 10 ‣ 4.9 Exploratory: frontier-model session pilot ‣ 4 Results ‣ Whose doctor does the AI recommend? An algorithm audit of reputation
and demographic signals in large language model–assisted physician choice")). Two demographic patterns appear
consistently across the piloted models and merit confirmatory scrutiny in a
protocol-compliant run: physicians with female-signaled names were chosen
more often than male-signaled ones (22–24% vs. 16–19%), directionally
matching the confirmatory panel’s pro-female tilt, and
East-Asian–signaled names were chosen more often (31–36%) than
White-signaled (12–19%) or Black-signaled (9–13%) names, a pattern the
confirmatory panel does not show. At n=50n=50 choice sets per model these are
directional readings only; none is a hypothesis test.

|  | Haiku 4.5 | Sonnet 5 | Opus 4.8 | Fable 5 |
| --- | --- | --- | --- | --- |
| Rating 3.9 | 0.01 | 0.00 | 0.01 | 0.01 |
| Rating 4.3 | 0.14 | 0.18 | 0.18 | 0.16 |
| Rating 4.7 | 0.43 | 0.40 | 0.39 | 0.40 |
| Fee $90 | 0.36 | 0.37 | 0.35 | 0.35 |
| Fee $140 | 0.17 | 0.17 | 0.17 | 0.17 |
| Fee $190 | 0.06 | 0.05 | 0.08 | 0.08 |
| 12 reviews | 0.11 | 0.09 | 0.07 | 0.05 |
| 85 reviews | 0.18 | 0.20 | 0.18 | 0.23 |
| 400 reviews | 0.30 | 0.29 | 0.34 | 0.30 |
| Recent review (3 days) | 0.27 | 0.26 | 0.26 | 0.27 |
| Stale review (11 mo.) | 0.14 | 0.15 | 0.15 | 0.14 |
| Female name | 0.22 | 0.22 | 0.23 | 0.24 |
| Male name | 0.19 | 0.19 | 0.17 | 0.16 |
| White name | 0.19 | 0.12 | 0.12 | 0.12 |
| Black name | 0.09 | 0.11 | 0.13 | 0.13 |
| Hispanic name | 0.16 | 0.14 | 0.16 | 0.16 |
| East Asian name | 0.31 | 0.36 | 0.31 | 0.33 |
| South Asian name | 0.24 | 0.25 | 0.25 | 0.24 |

The archived pilot-based forecasts of full-run choice probabilities
(Methods) could not be graded at analysis freeze because no
protocol-compliant API run of a forecast-target model was available; they
remain archived, timestamped, and ungraded, available for scoring the day
such a run is executed.

## 5 Discussion

### 5.1 Principal findings

Three results anchor the audit. First, LLM physician recommendation is
reputation-driven to a degree exceeding human benchmarks: rating carries
37.7% of attribute importance and fee 24.1%, and the models weight the
rating step at $157 per visit, signal weights directionally consistent
with, but steeper than, those estimated from human physician-choice
conjoints ([Yaraghi et al. 2018](#bib.bib16)). Second, demographic parity is rejected in
the direction opposite to the discrimination documented in human audit
studies: female-, Hispanic-, South-Asian–, and Black-signaled names gain
one to three percentage points over male White-signaled names (worth
$7–$14 per visit), and no gender×\timesethnicity cell meets the
prespecified ±\pm1.5 pp equivalence bound. Third, a content-free position
effect persists (first-listed worth $11 per visit), and neither the
demographic nor the position effects ever surface in the models’ stated
reasons.

### 5.2 Comparison with prior work

Where human patients discount female and minority physicians in
correspondence and field settings ([Bertrand and Mullainathan 2004](#bib.bib4); [Gaddis 2017](#bib.bib7)), the
audited models tilt modestly the other way, a pattern more consistent with
post-training fairness interventions overshooting neutrality than with
learned representativeness. Relative to clinical-bias audits
([Zack et al. 2024](#bib.bib17); [Omiye et al. 2023](#bib.bib13)), which find LLMs importing human clinical
disparities, the consumer-facing recommendation layer studied here behaves
differently: the risk is not replicated prejudice but *unaudited,
opaque tilts of either sign*. Relative to descriptive chatbot-referral
audits ([Parikh et al. 2024](#bib.bib14)), the randomized design shows what they cannot:
that name effects exist net of every other attribute. And relative to the
travel-domain companion audit ([Baig et al. 2026](#bib.bib3)), the same valence-price
primacy and content-free position bias reappear with identical anchor
levels, establishing cross-domain stability of the infomediary signal
hierarchy.

### 5.3 An audit framework for AI infomediaries

Beyond the physician-choice findings, the study demonstrates a reusable
template for auditing *infomediaries*, that is, AI systems that
intermediate a person’s choice among options or among other people. The same frozen-design,
randomized-conjoint machinery produced causal signal weights in two domains
(hotels ([Baig et al. 2026](#bib.bib3)); physicians here) with identical anchor levels,
and the full pipeline spans design generation, execution, estimation,
equivalence testing, and monetary equivalents: auditing a new model against
the frozen design is a single command. Because model updates can
silently reweight signals, parity verdicts expire; we propose treating
audits of this form as *recurring* monitoring rather than one-shot
evaluation. The observed heterogeneity underscores this: the pro-female
tilt ranges from near-zero (gemma3) to clearly positive across models, one
candidate model failed the auditability gate entirely, and the exploratory
frontier pilot hints at ethnicity orderings the confirmatory panel does not
show. Verdicts are therefore model-specific and version-specific, motivating
per-release audits.

### 5.4 Implications

For platforms: provider-directory orderings feed AI assistants; a
content-free first-position effect worth $11 per visit means interface
choices allocate patient flow. For health-equity monitoring: group-level
parity testing with prespecified equivalence bounds detected tilts that
favor minority physicians, a reminder that “bias” in deployed systems
need not match the direction of historical discrimination, and that
monitoring must test for departures in both directions. For physicians and
practices: the fee-equivalent table prices controllable signals such as
recent reviews ($19), telehealth ($14), and responding to feedback
($10), against the dominant rating step ($157). For regulators: the stated-vs-revealed
gap is the paper’s sharpest governance result. Demographic attributes moved
choices but were mentioned in ≤\leq0.03% of reasons; transparency
obligations that rely on model self-report would not have detected the
effects measured here. For the alignment debate on refusals: abstention was
rare (0.39%) and indiscriminate rather than concentrated on
demographically contrastive choice sets: these models did not “know when
not to answer.”

### 5.5 Limitations

Synthetic profiles bound external validity: real directories embed correlated
attributes and photographs; we audit text-only cards. Name signaling
identifies perceived-category effects, not mechanisms, and the significant
name-exemplar placebo shows specific names carry information beyond their
gender×\timesethnicity cell, so cell-level estimates are audit-level
signals rather than clean category parameters. The audited panel comprises
six small open-weight models and one proprietary production model
(gpt-4o-mini); open-weight models under-represent the proprietary
assistants patients most use, and findings are a snapshot of specific model
versions (identifiers and dates recorded). The frontier-model
session pilot narrows but does not resolve this gap: four Claude-family
models were probed on the identical frozen design, and quantitative
forecasts of their full-run behavior were archived in advance of
measurement, a falsifiable-prediction step we propose as standard practice
for staged audits. The pilot remains exploratory by construction
(harness-embedded collection, default decoding, n=50n=50 choice sets per
model), and the forecasts carry evidential weight only once graded against
a protocol-compliant API run. Choice sets held
specialty, board certification, and distance constant; effects of those
attributes are outside this design. Equivalence bounds of ±\pm1.5 pp are a
prespecified judgment call; smaller systematic effects could persist below
them.

### 5.6 Conclusions

A prespecified randomized audit of seven LLMs establishes causally that AI
physician recommendation runs on ratings and price, carries a content-free
position premium, and applies small systematic demographic tilts, favoring
female- and minority-signaled names, that the models never disclose in
their own explanations. None of these properties is observable from model
self-report; all of them are measurable, cheaply and repeatably, with a
frozen randomized instrument. As AI infomediaries absorb the referral
function, recurring behavioral audits of this form, rather than explanation
mandates, are the monitoring technology fit for purpose, and a frozen-design
instrument of this kind makes each new model release auditable in a day.

## References

## Instructions for reporting errors

We are continuing to improve HTML versions of papers, and your feedback helps enhance accessibility and mobile
support. To report errors in the HTML that will help us improve conversion and rendering, choose any of the
methods listed below:

**Tip:** You can select the relevant text first, to include it in your report.

Our team has already identified [the following issues](https://github.com/arXiv/html_feedback/issues). We appreciate your time reviewing and reporting rendering errors we
may not have found yet. Your efforts will help us improve the HTML versions for all readers, because disability
should not be a barrier to accessing research. Thank you for your continued support in championing open access for
all.

Have a free development cycle? Help support accessibility at arXiv! Our collaborators at LaTeXML maintain a [list of packages that need conversion](https://github.com/brucemiller/LaTeXML/wiki/Porting-LaTeX-packages-for-LaTeXML), and welcome [developer contributions](https://github.com/brucemiller/LaTeXML/issues).

![Simons Foundation](/static/base/1.0.1/images/funders/simons-foundation.png)
![Simons Foundation International](/static/base/1.0.1/images/funders/simons-foundation-international.png)
![Schmidt Sciences](/static/base/1.0.1/images/funders/schmidt-sciences.png)
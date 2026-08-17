---
source_url: https://arxiv.org/abs/2607.05404
ingested: 2026-08-17
sha256: 71597eb741aba8d1caaacf249ca8f9447a77536e2d53a227715dc28eac8c940c
---

# The Jagged Global Economy: Frontier AI Unevenly Exposes National Economies

###### Abstract

Frontier AI’s labor-market effects matter to workers, firms, and policymakers, but current evidence generally comes from a handful of high-income economies.
The capabilities of frontier AI are jagged across work tasks and national economies diverge in how they allocate human labor.
We introduce a national AI exposure metric that combines occupation-level exposure scores and international employment data for 141 countries. We find that high income countries are substantially more exposed than low income countries and that Europe & Central Asia are 50% more exposed than Sub-Saharan Africa.
We also find a gender gap: women are more exposed than men in 91% of countries, driven by their concentration in white-collar and sales occupations. The exceptions are countries where women’s employment remains concentrated in agriculture and household enterprises.
We validate our national AI exposure estimates by showing they predict national AI adoption statistics published by Anthropic, Microsoft, and OpenAI.
Beyond direct exposure, we identify a new mechanism for indirect exposure due to cross-country income dependencies.
Some nations such as Tajikistan depend heavily on foreign workers remitting money back to their home countries: Tajikistan’s direct exposure to frontier AI is below-average but because 37% of Tajikistan GDP is Russian remittance and Russia is very exposed, Tajikistan’s remittance-accounted exposure becomes above-average.
Our research shows that national variation in exposure is large enough that policy responses calibrated to U.S. or European labor markets will not generalize.

## 1 Introduction

How frontier AI will reshape national economies is central to workers, firms, and governments.
Around the world, the public already expects AI to reshape work: a majority of respondents in the 2025 Stanford AI Index report that AI will change how people do their jobs within five years, while the 2025 Ipsos AI Monitor finds that more people think AI will worsen than improve their local job market ([56](#bib.bib20); [34](#bib.bib21)).
Policymakers frame frontier AI as a strategic priority ([61](#bib.bib22); [10](#bib.bib23); [17](#bib.bib24)) and, reciprocally, frontier AI firms target national AI sovereignty agendas ([48](#bib.bib25)).
AI investment is seen as critical for future growth: the UN projects that the global AI market will expand to $4.8 trillion by 2033 ([62](#bib.bib26)).

These effects are likely to be very unevenly distributed across countries.
Frontier AI capabilities are jagged across tasks ([14](#bib.bib32)), and national economies differ substantially in how they allocate workers to jobs.
Consider call center work. [9](#bib.bib31) find that deploying generative AI in a large call center increases issues resolved per hour by 15% with larger gains for less experienced and lower-skilled workers.
A productivity shock of this level at scale would disproportionately disrupt nations like India or the Philippines where a large share of the national labor force is tied to call center work.
The same frontier AI technologies could complement workers in one nation, reorganize entry-level labor markets in another, and have little effect in a third.

We introduce a national AI exposure metric to capture this heterogeneity.
Our approach combines occupational exposure estimates from the economics of frontier AI literature with internationally comparable statistics on how countries allocate human labor across occupations.11
1
Concurrent with our work, [26](#bib.bib30) introduce a national AI exposure metric with a similar methodology but do not publish per-country exposure estimates at the time of writing.
The metric summarizes how strongly a national economy’s current labor allocation aligns with the tasks that frontier AI can already accelerate or transform.
The resulting object is not a forecast of adoption, wages, or net employment losses.
Rather, it is a comparable measure of exposure at the national level: a way to quantify which countries are more exposed, through the composition of their labor markets, to the jagged capabilities of frontier AI.
This exposure is not necessarily positive or negative: it signals opportunities for productivity gains but these gains are not certain, they may contribute to economic growth, and they may reduce the comparative advantage of human labor but could also increase it via certain patterns of augmentation.

We find substantial variation in national exposure ([Figure 1](#S1.F1 "Figure 1 ‣ 1 Introduction ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies")): the most exposed nation (Luxembourg) is 2.6×2.6\times more exposed than the least exposed nation (Burundi).
The most exposed regions are North America and Europe & Central Asia, which are at least 50% more exposed than the least-exposed region of Sub-Saharan Africa.
We study different explanations for this result and find that disparities in the prevalence of white collar work explain much of the observed variation.

Given the overall trends in national exposure, we disaggregate to study specific country and worker characteristics.
At the country level, we find that higher income countries are more exposed.
At the worker level, we find a pervasive gender gap: women in 91% of studied nations are more exposed than men because of their occupational composition.
In many countries, women already face barriers to labor force entry and receive lower wages for comparable work product ([31](#bib.bib34); [7](#bib.bib35)).
The groups we find to be more exposed (i.e. richer countries, women) also poll less optimistically about AI work ([41](#bib.bib38)), so our results may explain why these groups are less optimistic.

We test the predictive validity of our national AI exposure metric by predicting national AI adoption according to usage statistics published by Anthropic, Microsoft, and OpenAI.
We find strong monotonic relationships between our exposure estimates and all of these adoption statistics.
We estimate that 0.100.10 increase in national AI exposure corresponds to 12×12\times growth in national per-capita Claude usage and 19 percentage-point increase in the national generative AI adoption rate.

Since the economic impacts of frontier AI are not only determined by domestic activity but also cross-country relationships, we study indirect exposure channels.
We identify a novel mechanism for national exposure: foreign workers sending remittance back to their families in their home countries.
We show that this channel substantially increases national exposure for several countries where foreign remittance is a sizable fraction of national GDP.
For example, 25% of the GDP of Honduras, Guatemala, and El Salvador is remittance and more than 80% for all three countries is remitted from the United States.
Since the national AI exposure of these three Central American countries is below average but the United States is highly exposed, accounting for this indirect effect substantially raises national AI exposure in Honduras, Guatemala, and El Salvador.
National policymakers in these countries should track how the foreign labor economies they depend on are changing because of frontier AI adoption and the resulting second-order effects on their national income.
Overall, our research identifies critical heterogeneity that should inform national AI and economic policy.

## 2 Data

To estimate national exposure to frontier AI, we combine occupational employment statistics from the International Labour Organization (ILO) with occupational exposure estimates from Gmyrek et al.

### 2.1 Occupational employment statistics

To study the impact of AI on labor economies around the world, we use country-level data compiled by the ILO.
The ILO publishes employment statistics based on the International Standard Classification of Occupations (ISCO-08), which is a four-level hierarchy that spans 436 occupational categories.
As an example, one of the 436 occupational categories is ‘‘Generalist Medical Practitioners’’ (code 2211; code 2 = Professionals, code 22 = Health Professionals, code 221 = Medical doctors).22
2
For brevity, we will sometimes refer to occupational categories as “occupations” where the distinction is immaterial.

We use the most recent annual statistics for each country’s employment counts for the 43 2-digit (sub-major group) ISCO-08 occupational categories, along with available ILO wage statistics for wage-weighted extensions.
The counts are produced by national statistical offices through country-level data collection (e.g. labor force surveys, census, administrative records) and then compiled and disseminated by the ILO.
We describe data processing in [Appendix A](#A1 "Appendix A Data ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies"), including the country filters and the exclusion of armed-forces, aggregate, and residual occupational rows.
We end up with employment data for 40 occupational categories across 141 countries.
This provides strong coverage of the world’s nations, with most missing nations being very small countries with less mature government labor data infrastructure.33
3
We lack 2-digit ISCO-08 data for a few major economies (e.g. China, Canada, Saudi Arabia).

[Figure 2](#S2.F2 "Figure 2 ‣ 2.1 Occupational employment statistics ‣ 2 Data ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies")visualizes how employment composition varies around the world.
For example, office- and knowledge-intensive work (ISCO major groups 1--4) accounts for 61% of employment in the United States, but only 14% in India and 5% in Mozambique.
And agriculture (ISCO 6) accounts for 73.0% of employment in Mozambique and 35% in India but only 0.4% in the United States.
Beyond labor compositional differences, wages also vary greatly: the average monthly white-collar wage is PPP $7,778 in the United States, compared with PPP $1,740 in India.44
4
PPP denotes purchasing-power-parity-adjusted U.S. dollars to account for local price levels across countries.
White-collar work earns 74.2% of the wage bill in the United States to 30.4% in India.

### 2.2 Occupational exposure estimates

AI capabilities can impact labor through multiple mechanisms.
A critical mechanism is productivity.
AI could reduce the time spent performing tasks.
Exposure measures the time spent by a worker performing a task (or occupation) that could be saved by current technological capabilities.
Exposure estimates bridge technological progress with economic task-based models, a standard framework in the economics of technological change that studies how technologies substitute for, complement, and create tasks rather than affecting occupations as undifferentiated bundles ([5](#bib.bib6); [1](#bib.bib7); [2](#bib.bib8)).

[16](#bib.bib1) popularized the application of exposure to the economic impacts of frontier AI.
To estimate occupational exposure, they average across an occupation’s tasks based on whether AI capabilities would save half the time spent on the task while preserving quality.
To encode the level of capability at the time, they specified primitives that models could do (e.g. summarize medium-length documents) and could not do (e.g. repair physical equipment).
Their empirical estimates use human and GPT-4 annotations to determine task exposure, leading to an overall estimate that “80% of the U.S. workforce could have at least 10% of their work tasks affected by the introduction of LLMs, while approximately 19% of workers may see at least 50% of their tasks impacted.”
Prior to the work of [16](#bib.bib1), earlier works estimated occupational exposure to machine learning and AI based on occupational abilities ([19](#bib.bib9); [20](#bib.bib10)), patents ([63](#bib.bib11)), and by mapping cognitive abilities required for tasks to benchmarks ([58](#bib.bib12)).
Following their work, others have expanded exposure estimates to multimodal capabilities ([21](#bib.bib13)), complementarity rather than pure substitution ([54](#bib.bib14)), and to integrate evidence from observed usage ([40](#bib.bib16)).

While exposure pervades empirical research on frontier AI, critiques target (i) the aggregation from tasks to occupations or (ii) the divergence between theorized and observed exposure.
The standard aggregation of averaging task-level exposure to yield occupation-level exposure may incorrectly imply a linear production structure: occupations with the same average exposure may face different impacts when exposed tasks appear in chains or when tasks are quality complements and bottlenecks ([15](#bib.bib17); [22](#bib.bib18)).
Further, the impact on wages or employment may be better predicted not by the tasks that are automated, but by the expertise requirements of the residual tasks ([6](#bib.bib19)).
[16](#bib.bib1) emphasize that exposure quantifies technical feasibility rather than observed productivity: [46](#bib.bib2) posit a variety of diffusion bottlenecks and [40](#bib.bib16) quantify large gaps between theoretical exposure and observed usage in several occupations.

Most AI exposure estimates use the U.S. occupational classification system.
Our focus is global and not limited to the U.S., so we use exposure estimates for the international ISCO occupational classification system prepared by researchers at the ILO ([25](#bib.bib27)).
Since the ISCO occupations do not have rich task-level decompositions, they first use Polish occupational data that maps occupations to 29,753 distinct tasks and gather human judgments about the automation potential of a representative sample of 2,861 tasks from 1,640 workers.
Experts review these worker assessments and they use the resulting expert-adjusted annotations to train a model to predict task-level exposure, which is then aggregated for all 4-digit ISCO-08 occupations.

## 3 National AI Exposure Estimates

We quantify national exposure to frontier AI based on nation-agnostic occupational exposure estimates and nation-specific occupational employment statistics.55
5
This neglects heterogeneity (e.g. task composition) in the same occupation across countries. However, intra-occupation heterogeneity may be dominated by intra-category cross-occupational heterogeneity at the 2-digit ISCO level. [26](#bib.bib30) attempt to address this via a more complex nation-sensitive estimation procedure for occupation exposure.
Prior work applies similar approaches using different estimates for occupational AI exposure ([11](#bib.bib28); [35](#bib.bib29); [26](#bib.bib30)).
We define national AI exposure as the employment-share-weighted average exposure of a country’s occupational structure.

For an occupation jj, let eje\_{j} quantify its exposure and ci,jc\_{i,j} count its employment in nation ii.

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
|  | ni\displaystyle{n}\_{i} | =∑jci​j​ej∑jci​j\displaystyle=\frac{\sum\_{j}c\_{ij}e\_{j}}{\sum\limits\_{j}c\_{ij}} |  | (1) |

National AI exposure varies substantially across countries ([Figure 1](#S1.F1 "Figure 1 ‣ 1 Introduction ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies")): the most-exposed country (Luxembourg, n=0.37{n}=0.37) is 2.6×2.6\times more exposed than the least-exposed country (Burundi; n=0.14{n}=0.14).
Luxembourg’s unusually large finance-and-insurance sector drives its high exposure: business and administration professionals and associate professionals together account for 38.7% of total exposure, with legal, social and cultural professionals contributing another 10.0%. This pattern is consistent with Luxembourg’s unusually large finance-and-insurance sector.66
6
Luxembourg had the European Union’s highest employment share in finance and insurance ([18](#bib.bib53)).
Singapore also demonstrates high exposure through a similar but more technical/managerial mechanism: national exposure is 0.37, the white-collar share is 73.8%, and business, administration, and managerial occupations together account for 45.1% of total exposure ([44](#bib.bib54)).
At the bottom, Burundi shows how strongly the index is pulled down by agrarian employment structure.
It has the sample’s lowest exposure (0.1440), the lowest white-collar share (3.1%), and a strongly negative white-collar residual (-0.0468).
Nearly 69.3% of Burundi’s total exposure comes from subsistence farmers, fishers, hunters and gatherers alone ([64](#bib.bib55)).
[§B.1](#A2.SS1 "B.1 Alternative Occupational Exposure Estimates ‣ Appendix B Exposure Analysis ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies") shows that the results are robust to the choice of occupational exposure estimates.

On top of the large variation in national exposure, we find a persistent gender gap: women are more exposed than men in 126 of the 138 countries we study.
The median gender gap is 13.7% of national exposure and is driven by occupational composition.77
7
[36](#bib.bib41) observe this pattern for the U.S. labor economy.
Cross-country differences in male and female white-collar shares explain about half of the variation in the gender gap (50.3%), and including sales raises that explanatory power to 87.8%, indicating that women’s greater concentration in white-collar and sales work is the dominant structural mechanism.
The pattern is visible in concrete cases.
Women are substantially more exposed in the Philippines (0.2964 for women versus 0.2214 for men) and Jamaica (0.3173 versus 0.2276), where official statistics show women concentrated in service-and-sales, clerical, and professional work ([53](#bib.bib56); [57](#bib.bib57)).
By contrast, women are less exposed in Pakistan (0.1970 for women versus 0.2338 for men) and India (0.2001 versus 0.2240), where women’s employment remains more concentrated in agriculture and household-enterprise work ([51](#bib.bib58); [45](#bib.bib59)).
This result that women may be more prone to AI-mediated labor disruption warrants concern given preexisting challenges for women to find gainful employment.
In many countries, women experience barriers to labor force participation ([31](#bib.bib34)) and receive lower wages than men, including within occupations and after accounting for standard observable characteristics ([7](#bib.bib35)).
And on the topic of AI, women are less likely to adopt the technology for work ([29](#bib.bib36); [50](#bib.bib37)) and have less positive impressions of the technology ([41](#bib.bib38)).
Consequently, women workers may be more disrupted by AI because of men adopting AI in work.

### 3.1 Explaining national AI exposure

Cross-national variation in labor composition yields substantial differences in national AI exposure.
Can these differences be explained by more basic properties of the countries or their workforces?
[Figure 3](#S3.F3 "Figure 3 ‣ 3.1 Explaining national AI exposure ‣ 3 National AI Exposure Estimates ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies") shows national exposure as a function of the white collar share of the country’s labor force.
We find that the white collar share is highly predictive of exposure (R2=0.91R^{2}=0.91).
We also find that gross income is predictive of exposure, but less so than white collar share: log gross national income (log GNI) explains 77% of cross-country variation in national AI exposure.
Together, the two predictors have an R2R^{2} of 0.930.93, indicating that the workforce-specific white collar share statistic is more explanatory than the broader national-level income statistic.
We further explore how the exact classification of occupations as white collar or blue collar affects this result: changing the label of a single occupational category by classifying sales occupations (ISCO-08 code 52) as white collar instead of blue collar substantially increases explanatory power (R2=0.96R^{2}=0.96).
In [§B.4](#A2.SS4 "B.4 Predicting National AI Exposure ‣ Appendix B Exposure Analysis ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies"), we test other predictors, generally finding that measures related to computer use, written comprehension, administrative work, and information processing are good predictors.

The correlation between national AI exposure, white collar work, and national income manifests via other channels.
Cross-country surveys find substantial heterogeneity in public opinion on AI on matters spanning trust in the technology, confidence in its benefits, concerns about its risks, and desire for regulation.
For example, respondents in advanced economies generally report less trust and perceive less benefit from frontier AI relative to respondents from developing economies ([52](#bib.bib39); [23](#bib.bib40); [34](#bib.bib21)).
Anthropic interviewed 81k Claude users, finding that workers in occupations with more observed exposure are more likely to express concern about job displacement ([38](#bib.bib62)).
Beyond heterogeneity, many of these studies do report an overarching concern that the public fears and expects AI-driven job loss ([33](#bib.bib5)), which reflects a common interpretation of exposure as displacement risk even if exposure need not imply worse labor-market outcomes ([30](#bib.bib49)).

## 4 Predicting National AI Adoption

While exposure estimates translate from technological capabilities to economic quantities, they can be prone to misunderstanding ([16](#bib.bib1); [36](#bib.bib41); [30](#bib.bib49)).
Exposure identifies where AI could plausibly increase productivity, not which jobs will necessarily disappear.
For past technologies, economics research substantiates that task- and occupation-level exposure estimates predict downstream labor outcomes ([63](#bib.bib11); [6](#bib.bib19)).
For frontier AI, emerging evidence also shows that exposure estimates predicted observed frontier AI adoption ([59](#bib.bib42); [13](#bib.bib43); [27](#bib.bib44)) and AI-mediated employment reduction ([8](#bib.bib45); [60](#bib.bib48)).

We test whether national AI exposure estimates predict observed national outcomes.
As [12](#bib.bib4) notes, current data is insufficient to study broad cross-national wage or employment changes attributable to AI.
Therefore, we focus our attention on predicting national AI adoption using statistics published by frontier AI companies based on chatbot usage data.
We use data from Anthropic’s Anthropic Economic Index for Claude usage ([39](#bib.bib65)), Microsoft’s AI Diffusion adoption measures ([43](#bib.bib61); [42](#bib.bib66)), and OpenAI’s ChatGPT usage statistics ([13](#bib.bib43); [49](#bib.bib47)) with details in [§A.5](#A1.SS5 "A.5 Usage data statistics ‣ Appendix A Data ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies").

(a) Anthropic Claude usage

(b) OpenAI Signals rank percentile

(c) Microsoft GenAI adoption

We find that our national AI exposure estimates predict all three observed AI usage measures, although the three companies publish different types of statistics.
Using the Anthropic data, we find that national Claude usage scales approximately exponentially in national AI exposure: in the fitted relationship, a 0.10 increase in national AI exposure yields a 12×12\times increase in national Claude usage per 100,000 working-age people.
Since OpenAI ranks countries rather than publishing per-country statistics, we study ranking correlation within the 88 countries shared across our data and OpenAI Signals.
The top quintile by exposure (average exposure percentile = 90%) has high ChatGPT usage with an average OpenAI percentile of 86.5%.
Conversely, the bottom quintile by exposure (average exposure percentile = 10%) has low ChatGPT usage with an average OpenAI percentile of 14.9%.
Using the Microsoft data, we find that national generative AI adoption rate88
8
Adoption counts visits to generative AI sites/apps: Alice, ChatGPT, Character.ai, Claude, ClOVA X, DeepSeek, ERNIE Bot (Yiyan.baidu), GigaChat, Google Gemini, Grok, Khanmigo.ai, Meta.ai, Microsoft Copilot, Midjourney, Mistral.ai, NanoSemantics AI Assistant, Perplexity, Tongyi Qianwen, and Xiaowei. scales linearly in national AI exposure: in the fitted relationship, a 0.10 increase in national AI exposure yields an additional 203 national adopters per 1,000 working-age people.

Given our previous results ([§3.1](#S3.SS1 "3.1 Explaining national AI exposure ‣ 3 National AI Exposure Estimates ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies")) that national AI exposure is itself predictable from national white-collar share and gross national income (GNI), we test whether national AI exposure provides additional explanatory power over these standard national metrics in predicting national AI adoption.
Exposure alone strongly predicts all three adoption measures, with R2=0.77R^{2}=0.77 for Anthropic Claude usage, R2=0.81R^{2}=0.81 for OpenAI Signals, and R2=0.61R^{2}=0.61 for Microsoft AI Diffusion.
However, once white-collar share and log GNI are included, adding national AI exposure contributes little additional explanatory power: the full-model R2R^{2} is unchanged for Anthropic and Microsoft after rounding, and increases by only 0.001 for OpenAI (see [Table 6](#A2.T6 "Table 6 ‣ B.5 Predicting National AI Adoption ‣ Appendix B Exposure Analysis ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies")).

## 5 Indirect Channels for National AI Exposure

While the direct impact of AI on domestic workers is central to determining how national labor economies change because of AI, it is not the sole determinant.
National economic outcomes depend on the activities of other nations (e.g. trade, tariffs, outsourcing).
Given concerns that AI-driven automation may reduce labor demand and domestic wages ([3](#bib.bib3); [6](#bib.bib19); [8](#bib.bib45)), we consider how this may be mediated by the impacts of AI on foreign countries.

We observe that while the concern is often expressed as AI suppressing wages, the underlying concern is that individuals will not be able to generate the income required to sustain their lives.
In most countries, this can be restated in terms of wages, because individual income and individual wages are essentially equal.
However, we observe that in some nations, a second mechanism meaningfully contributes to income: remittance.
Remittance is the transfer of money by a foreign worker (usually a migrant) to their home country to serve as income for their families.
We hypothesize that remittance introduces a second channel for national exposure: if income in country A is sourced via remittance from country B, then national exposure in country B indirectly exposes country A.

To study this hypothesis, we use the KNOMAD database from the World Bank on global migration and development ([§A.4](#A1.SS4 "A.4 World Bank KNOMAD remittance ‣ Appendix A Data ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies"); [65](#bib.bib50); [66](#bib.bib51)).
The KNOMAD country-country remittance matrix estimates annual remittance flows between source and target countries by partitioning total target-side remittance inflow proportional to bilateral migration distributions ([55](#bib.bib52)).
For example, since Mexico received $52 billion from the U.S. in remittance during 2021, a decline in U.S. labor demand could indirectly reduce income in Mexico via remittance reduction.

We find that the remittance channel generally raises measured exposure among highly remittance-dependent countries: 18 of the 19 countries with remittances above 10% of GDP move above the diagonal in [Figure 5](#S5.F5 "Figure 5 ‣ 5 Indirect Channels for National AI Exposure ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies").
Tajikistan is the clearest example.
It received $6.80 billion in personal remittances in 2024, equal to 47.9% of GDP.
The latest KNOMAD bilateral matrix is for 2021; in that matrix, Russia accounts for $2.31 billion of Tajikistan’s $2.92 billion in measured bilateral remittance inflows, or 79.0%.
Tajikistan’s direct national AI exposure is low (n=0.222{n}=0.222, 21st percentile among countries with measured exposure), but its remittance inflows come primarily from more exposed economies, led by Russia (n=0.298{n}=0.298, 75th percentile) and Germany (n=0.333{n}=0.333, 96th percentile).
As a result, Tajikistan’s remittance-accounted exposure rises to n=0.300{n}=0.300, comparable to a 75th-percentile country in the direct exposure distribution.

This result illustrates that even if countries are not directly exposed to frontier AI, or that theoretical exposure is unlikely to convert into observed productivity (e.g. due to the digital divide and lack of internet access), they should prepare for the ripple effects of AI adoption elsewhere.
In particular, while policymakers in these countries currently account for remittance in strategic planning given its scale, they may not account for the second-order remittance-mediated effect of AI on their economy.

## 6 Discussion

Frontier AI development is concentrated in a few nations like the United States and China, but its economic impacts are globally diffuse.
The national AI exposure metric we introduce provides an initial lens for clarifying how frontier AI capabilities may impact countries around the world in different ways and the specific occupational categories within those labor markets.
This encodes two forms of heterogeneity: occupations are differentially exposed and national labor markets are differentially composed of occupations.
To make the most of these metrics, we believe they should be integrated with measures that operate at other levels of abstraction in reasoning about the impacts of (frontier) AI on the economy.
In turn, this introduces a third form of heterogeneity: data availability varies substantially across the world.

#### Heterogeneity in data availability.

As we also consider in this work, usage data is especially useful in the study of frontier AI’s economic impacts because it directly reflects the actual tasks and workflows where AI is adopted ([37](#bib.bib63)).
From the international perspective, usage data is attractive because it centralizes data pertinent to many different countries at a single entity, namely the AI provider.
Notably, several frontier AI companies signed onto the New Delhi Frontier AI Commitments at the 2026 India AI Impact Summit to publish usage data reports.99
9
The commitment to Advance Analysis on Real-World AI Usage states that “Participating organizations will work to enhance analysis regarding global
AI adoption for economic purposes …Publish — by the next AI Summit — statistical insights derived from anonymised,
aggregated and taxonomized usage data, either directly or (where relevant)
through contributions to international efforts.”
For similar reasons, other private datasets such as payroll or payments information may help characterize frontier AI adoption while being naturally consolidated ([8](#bib.bib45), e.g.).
On the other hand, many forms of traditional labor economics data hinge on government data collection infrastructure.
Therefore, data quality and quantity may vary greatly across the world, generally leading to greater availability for advanced economies.
As our results show, frontier AI’s impacts on advanced economies are unlikely to resemble impacts on developing nations.
Therefore, making the most of other data sources and sensibly imputing data in cases of missingness will be essential for characterizing the impacts of frontier AI on developing economies.

#### Limitations.

The primary limitations of our work relate to limits of the underlying data we rely upon for occupational exposure estimates and national employment statistics.
First, we treat an occupation as identically exposed for every country.
While most work neglects within-country variation in an occupation (e.g. software engineers in San Francisco may differ from those in New York City), we more strongly neglect cross-country intra-occupation variation (e.g. software engineers in San Francisco may differ from those in New Delhi).
Second, we operate at the ISCO 2-digit level which collapses many distinct occupations into a single category.
For example, group 26 combines lawyers (2611) with musicians, singers, and composers (2652), even though their task bundles are qualitatively different. Third, the underlying occupational classification system (ISCO-08) was developed in 2008 and may not capture occupational emergence in the past two decades.
Looking forward, this extends to occupations that emerge due to frontier AI (e.g. prompt engineers).
Fourth, we do not have complete coverage of the world’s nations and we inherit the ways in which the ILO and World Bank handle national data for contentious regions of the world.
Perhaps most critically, we do not have national AI exposure estimates for China, Canada, and Saudi Arabia as a result.1010
10
We encourage future work to explore data imputation for these countries from domestic data surveys if data via the ILO is unavailable, though we refrained from doing this for analytic simplicity.

## Acknowledgements

We thank Alex Spangher, Alexander Wan, Bharat Chandar, Diyi Yang, Dylan Clement, Erik Brynjolfsson, Sam Manning, Sarah Bana, Satya Krishna, Stephane Hatgis-Kessell, and Tom Cunningham for helpful discussion.

## References

## Appendix A Data

### A.1 ILO employment

| Status | Countries |
| --- | --- |
| Included in baseline sample (medium/high reliability) | 141 |
| Observed but excluded for low reliability | 6 |
| Excluded: TOTAL/NEC only | 2 |
| Excluded: ISCO-88 only | 9 |
| Excluded: major-group only | 9 |

Baseline sample counts reflect the current merged ILO refresh and include countries with medium or high reliability only.

We use employment data published by the International Labour Organization (ILO), taking the most recent annual country observation available in the local ILO mirror accessed in April 2026.
The total-employment country-years in the underlying panel range from 2009 to 2025, with most observations from 2024 or 2025.
The employment data used in the main analysis are reported at the 2-digit (sub-major group) level of ISCO-08, yielding up to 40 occupation groups per country once armed-forces, aggregate, and residual categories are excluded.
The three excluded armed-forces sub-major groups are ISCO-08 codes 01, 02, and 03; we also drop aggregate TOTAL rows and residual X rows rather than redistributing them.
In the ILO mirror EMP\_TEMP\_SEX\_OC2\_NB\_A, 113 countries report nonzero employment in the armed-forces groups.
Among those countries, the excluded armed-forces share is usually small (median 0.42%) but reaches 5.11% in Iraq, 4.61% in Palestine, 4.46% in Lebanon, and 2.95% in Sudan.
While the data nominally covers 167 nations, we analyze the 141 where the ILO ascribes greater confidence to the underlying data quality and data collecting procedures. Gender-disaggregated exposure estimates use the same ILO occupational-employment pipeline restricted to sex-disaggregated country-occupation cells.
For the main white-collar measure, we classify ISCO-08 major groups 1–4 (managers, professionals, technicians and associate professionals, and clerical support workers) as white-collar work.
Sales occupations are treated separately in the mechanism analysis because ISCO-08 code 52 is a boundary case: including sales with white-collar work substantially increases the explanatory power of the simple labor-composition split.

### A.2 ISCO exposure estimates

| Level | Count | Aggregation rule | Use in this paper |
| --- | --- | --- | --- |
| Task-by-occupation rows in the Gmyrek workbook | 3,265 | Exposure score assigned to each task row within a 4-digit ISCO-08 occupation | Raw exposure source layer |
| 4-digit occupations (ISCO-08) | 427 | Mean task-level exposure score within each 4-digit occupation | Occupation-level exposure estimates |
| 2-digit occupations | 40 | Mean 4-digit occupation score within each 2-digit ISCO-08 group | Matched to ILO employment shares in the main cross-country analysis |
| 1-digit occupation groups | 9 | Aggregation of 2-digit occupations to ISCO major groups | Descriptive summaries and wage-weighted extensions |

Note: Counts are based on the Gmyrek et al. (2025) exposure workbook used in our pipeline. The workbook contains 3,219 predicted rows and 46 reconciled rows.

We use the occupational exposure estimates for ISCO-08 [[24](#bib.bib15)].
We describe these estimates in terms of their relationship to the ISCO-08 multi-level hierarchy in [Table 2](#A1.T2 "Table 2 ‣ A.2 ISCO exposure estimates ‣ Appendix A Data ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies").
Since we only have employment data at the 2-digit level of ISCO-08, we average the occupational exposure estimates for all occupations within the same 2-digit category.
Of the 436 ISCO-08 4-digit occupations, the Gmyrek et al. data score 427.
The nine unscored 4-digit codes are six “not elsewhere classified” residual codes (1439, 3139, 3435, 5249, 7319, 8189) and three armed-forces codes (0110, 0210, 0310).
We do not impute exposure scores for these unscored residual or armed-forces occupations.

### A.3 World Bank national statistics

We merge the occupational exposure panel with World Bank national statistics used in the descriptive and regression analyses, including GNI per capita in PPP terms, internet penetration, population, and remittance indicators.
GNI and internet penetration enter the appendix predictor regressions as country-level development and infrastructure controls.

### A.4 World Bank KNOMAD remittance

We use World Bank WDI data on personal remittances received to measure remittance inflows in current U.S. dollars and as a share of GDP, using reported WDI values directly where available.
We use the KNOMAD bilateral remittance matrix (WB.KNOMAD.BRE) to estimate source-country shares for remittance-receiving countries, again using the reported matrix values directly; the latest bilateral matrix available in our data is for 2021.
The remittance examples therefore combine the latest available WDI remittance totals or remittance-to-GDP shares, generally 2024, with 2021 KNOMAD bilateral source-country shares.
We do not impute missing bilateral corridors, extrapolate bilateral shares to later years, or assign synthetic exposure values.

### A.5 Usage data statistics

The observed adoption analysis uses three external usage statistics: Anthropic Economic Index country-level Claude usage, OpenAI Signals country rankings for population-normalized ChatGPT use, and Microsoft AI Diffusion country-level generative AI adoption rates [[4](#bib.bib46), [27](#bib.bib44), [49](#bib.bib47), [43](#bib.bib61), [42](#bib.bib66)].
We match these external country statistics to the 141-country exposure panel using ISO-3 country codes where publishers provide them and otherwise using unambiguous country or economy names.
We do not adjudicate contested political status or reassign entities across source definitions: labels such as Taiwan, China, Korea, or other country/economy groupings are retained as reported by the source, and an observation is used only when it maps unambiguously to an entity in the exposure panel.
If a source reports an entity that does not cleanly match the exposure panel, we omit it rather than imputing or reallocating it.
Each adoption regression uses the complete-case country sample available for the corresponding outcome and covariates.
The resulting complete-case samples are 114 countries for Anthropic Claude usage, 88 for OpenAI Signals, and 106 for Microsoft AI Diffusion.

### A.6 Reproducibility and asset provenance

The anonymous release for reviewers has two parts.
The dataset release contains the derived measured CSV tables used in the paper, Croissant metadata, a data dictionary, and a source-data manifest.
The reviewer code package contains validation scripts, figure and table builders, and two clean notebooks (01\_dataset\_tour.ipynb and 02\_reproduce\_main\_results.ipynb) that reproduce paper-facing values, regression tables, and release-supported figures from the released derived tables where redistribution permits.
The analysis consists of deterministic data validation, aggregation, crosswalks, plotting, and ordinary least squares regressions run in Python on CPU; no model training or GPU computation is required.
The released derived tables freeze the values used in this submission.
Raw-source rebuilds are deterministic conditional on the source snapshots listed in [Table 3](#A1.T3 "Table 3 ‣ A.6 Reproducibility and asset provenance ‣ Appendix A Data ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies"), but some upstream ILO and World Bank mirrors may be revised over time; for this reason, the reviewer workflow does not require live API pulls and instead reproduces results from the released tables.
Where source data cannot be redistributed under the provider’s terms, the release records the original source, access date or version, redistribution status, and release tables supported in the source-data manifest.
Raw third-party files and non-anonymized working notebooks are not redistributed; the Microsoft AI Diffusion country/economy adoption table is included from Microsoft’s official MIT-licensed GitHub data release after ISO alpha-3 matching.

| Asset | Use in paper | Version or date | Credit and license/terms source |
| --- | --- | --- | --- |
| ILOSTAT employment and wage statistics | National occupational employment and wage composition | Most recent annual country statistics; accessed 2026-04-14 | [32](#bib.bib33); <https://ilostat.ilo.org/data/> |
| Gmyrek et al. ISCO exposure estimates | Primary occupation-level exposure scores | 2025 ILO Working Paper 140 release | [24](#bib.bib15) |
| World Bank WDI and KNOMAD | GNI, remittance totals, and bilateral remittance shares | WDI 2024 where available; KNOMAD bilateral matrix latest year 2021 | [65](#bib.bib50), [66](#bib.bib51); <https://databank.worldbank.org/> |
| Anthropic Economic Index | Country-level Claude usage validation | Country usage release used in [Figure 4](#S4.F4 "Figure 4 ‣ 4 Predicting National AI Adoption ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies") | [39](#bib.bib65) |
| OpenAI Signals | Population-normalized ChatGPT usage rank validation | Calendar-year 2025 country ranks | [49](#bib.bib47) |
| Microsoft AI Diffusion | Country-level generative AI adoption validation | Q1 2026 GitHub data update | [43](#bib.bib61), [42](#bib.bib66); MIT license at <https://github.com/microsoft/ai-diffusion-report> |
| O\*NET 30.2 and alternative exposure estimates | Occupational-property and robustness analyses | O\*NET 30.2; source releases cited in appendix | [47](#bib.bib60), [16](#bib.bib1), [28](#bib.bib64) |

## Appendix B Exposure Analysis

### B.1 Alternative Occupational Exposure Estimates

Throughout our work, we use the occupational exposure estimates of [24](#bib.bib15) because they are naturally designed for the ISCO-08 occupational categories.
However, other exposure estimates are more popular in the broader economics of AI literature, which often derive from the U.S. Department of Labor such as the O\*NET work taxonomy and the SOC occupational list.
Via a crosswalk that aligns the DOL resources and the SOC list with the ILO resources and the ISCO list, we can compare the occupational exposure estimates we use to other popular choices.

We compare our primary Gmyrek et al. exposure scores to two prominent alternatives: the LLM-task exposure measure from [16](#bib.bib1) and the occupational exposure measure from [28](#bib.bib64).
Because these alternatives are defined over O\*NET/SOC occupations rather than ISCO-08 occupations, we use the SOC-to-ISCO crosswalk described above and aggregate scores to ISCO-08 2-digit occupations before recomputing national exposure scores.1111
11
The robustness pipeline maps O\*NET-SOC 8-digit occupations to SOC-2018 6-digit occupations, then to SOC-2010 6-digit occupations using the BLS 2018 reclassification crosswalk, then to ISCO-08 4-digit occupations using the BLS 2012 SOC-ISCO crosswalk, and finally to ISCO-08 2-digit occupations. At each merge, we take unweighted means across crosswalk rows. The BLS SOC-ISCO crosswalk is many-to-many and includes partial-overlap flags, which we do not weight separately. As a sensitivity check, assigning each SOC-to-ISCO mapping a part-share weight of 1/k1/k for a SOC code that maps to kk ISCO codes changes the Gmyrek-vs-Eloundou Pearson correlation from 0.9540.954 to 0.9570.957 and the Spearman correlation from 0.9500.950 to 0.9550.955, leaving the robustness conclusion unchanged.

The estimates are highly correlated at the occupational and national levels (see [Figure 6](#A2.F6 "Figure 6 ‣ B.1 Alternative Occupational Exposure Estimates ‣ Appendix B Exposure Analysis ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies")).
At the occupation level, the resulting measures are highly correlated with the [25](#bib.bib27) scores: Pearson correlations are r=0.954r=0.954 for [16](#bib.bib1) and r=0.948r=0.948 for [28](#bib.bib64).
At the national level, rankings are even more stable, with Spearman correlations of ρ=0.993\rho=0.993 and ρ=0.990\rho=0.990, respectively.
The main disagreements are concentrated in a small number of occupations, such as ICT professionals and assemblers, but these differences do not materially change the cross-country ranking of national exposure.

### B.2 National Exposure Distribution and Country Scores

The main text visualizes national AI exposure geographically in [Figure 1](#S1.F1 "Figure 1 ‣ 1 Introduction ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies").
For completeness, [Figure 7](#A2.F7 "Figure 7 ‣ B.2 National Exposure Distribution and Country Scores ‣ Appendix B Exposure Analysis ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies") shows the corresponding distributional view, including the least- and most-exposed countries among countries with at least one million workers.
[Table 4](#A2.T4 "Table 4 ‣ B.2 National Exposure Distribution and Country Scores ‣ Appendix B Exposure Analysis ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies") reports the full 141-country exposure panel used in the map.

| Country | n{n} | Country | n{n} | Country | n{n} |
| --- | --- | --- | --- | --- | --- |
| Afghanistan | 0.189 | Germany | 0.333 | Norway | 0.320 |
| Albania | 0.230 | Ghana | 0.220 | Pakistan | 0.225 |
| Angola | 0.206 | Greece | 0.315 | Palau | 0.295 |
| Argentina | 0.294 | Guatemala | 0.234 | Palestine (State of) | 0.253 |
| Australia | 0.322 | Guinea | 0.227 | Panama | 0.232 |
| Austria | 0.321 | Guinea-Bissau | 0.179 | Papua New Guinea | 0.236 |
| Bahamas | 0.282 | Guyana | 0.247 | Peru | 0.243 |
| Bangladesh | 0.218 | Honduras | 0.231 | Philippines | 0.252 |
| Barbados | 0.286 | Hungary | 0.309 | Poland | 0.317 |
| Belarus | 0.282 | India | 0.217 | Portugal | 0.314 |
| Belgium | 0.323 | Indonesia | 0.242 | Romania | 0.272 |
| Belize | 0.242 | Iran (Islamic Republic of) | 0.254 | Russian Federation | 0.298 |
| Benin | 0.227 | Iraq | 0.243 | Rwanda | 0.186 |
| Bhutan | 0.242 | Ireland | 0.331 | Samoa | 0.239 |
| Bolivia (Plurinational State of) | 0.241 | Israel | 0.333 | Sao Tome and Principe | 0.230 |
| Bosnia and Herzegovina | 0.263 | Italy | 0.313 | Serbia | 0.285 |
| Botswana | 0.228 | Jamaica | 0.266 | Sierra Leone | 0.205 |
| Brazil | 0.278 | Japan | 0.316 | Singapore | 0.368 |
| Brunei Darussalam | 0.307 | Jordan | 0.255 | Slovenia | 0.304 |
| Bulgaria | 0.292 | Kenya | 0.199 | Solomon Islands | 0.199 |
| Burkina Faso | 0.198 | Kiribati | 0.227 | Somalia | 0.259 |
| Burundi | 0.144 | Kosovo | 0.288 | Spain | 0.301 |
| Cabo Verde | 0.220 | Kyrgyzstan | 0.240 | Sri Lanka | 0.237 |
| Cambodia | 0.221 | Lao People’s Democratic Republic | 0.205 | Sudan | 0.213 |
| Chile | 0.279 | Latvia | 0.304 | Suriname | 0.270 |
| Colombia | 0.263 | Lebanon | 0.264 | Sweden | 0.334 |
| Congo, Democratic Republic of the | 0.197 | Lesotho | 0.175 | Switzerland | 0.335 |
| Cook Islands | 0.290 | Lithuania | 0.309 | Tajikistan | 0.222 |
| Costa Rica | 0.274 | Luxembourg | 0.371 | Tanzania, United Republic of | 0.173 |
| Croatia | 0.311 | Madagascar | 0.166 | Thailand | 0.250 |
| Cuba | 0.265 | Malawi | 0.223 | Timor-Leste | 0.208 |
| Cyprus | 0.322 | Maldives | 0.280 | Togo | 0.235 |
| Czechia | 0.302 | Mali | 0.200 | Tokelau | 0.273 |
| Côte d’Ivoire | 0.240 | Marshall Islands | 0.268 | Tonga | 0.259 |
| Denmark | 0.324 | Mauritius | 0.289 | Tunisia | 0.236 |
| Dominican Republic | 0.264 | Mexico | 0.264 | Tuvalu | 0.305 |
| Ecuador | 0.222 | Micronesia (Federated States of) | 0.219 | Türkiye | 0.265 |
| Egypt | 0.254 | Mongolia | 0.263 | Uganda | 0.182 |
| El Salvador | 0.251 | Montenegro | 0.318 | United Arab Emirates | 0.281 |
| Estonia | 0.311 | Montserrat | 0.290 | United Kingdom of Great Britain and Northern Ireland | 0.329 |
| Eswatini | 0.244 | Mozambique | 0.162 | United States of America | 0.323 |
| Ethiopia | 0.177 | Myanmar | 0.229 | Uruguay | 0.281 |
| Fiji | 0.259 | Nepal | 0.233 | Vanuatu | 0.218 |
| Finland | 0.309 | Netherlands | 0.339 | Viet Nam | 0.225 |
| France | 0.319 | Niger | 0.241 | Wallis and Futuna | 0.291 |
| Gambia | 0.234 | Niue | 0.314 | Zambia | 0.187 |
| Georgia | 0.237 | North Macedonia | 0.286 | Zimbabwe | 0.192 |

### B.3 Gender Differences in National AI Exposure

[Figure 8](#A2.F8 "Figure 8 ‣ B.3 Gender Differences in National AI Exposure ‣ Appendix B Exposure Analysis ‣ The Jagged Global Economy:Frontier AI Unevenly Exposes National Economies")visualizes the country-level gender exposure gap discussed in the main text.
The x-axis reports the female-minus-male exposure gap as a percentage of total national exposure, so positive values indicate that female exposure exceeds male exposure.
The pattern is broad rather than driven by a handful of countries: women are more exposed than men in most measured countries, while the largest negative gaps appear in countries where women’s employment remains more concentrated in agriculture and other less-exposed occupations.
Among the 141 countries in the main exposure panel, 138 have reliable sex-disaggregated occupational comparisons.
Egypt, Micronesia, and Wallis and Futuna remain in the national exposure panel, but are excluded from this gender-gap analysis because their sex-disaggregated occupational cells do not meet the reliability criteria used for the appendix figure.

### B.4 Predicting National AI Exposure

Beyond the main white-collar specification, we test whether national exposure can be predicted from broader national and occupational covariates.
Among basic national covariates, white-collar share is the strongest single predictor; log GNI and internet penetration are also positively associated with exposure, but explain less cross-country variation on their own. We construct the cognitive-minus-physical (CMP) score as a task-composition diagnostic from O\*NET 30.2.
At the ISCO-08 2-digit occupation level, we map O\*NET SOC occupations to ISCO-08 and compare O\*NET occupational properties with the Gmyrek et al. exposure scores.

The cognitive side is the average of the five O\*NET properties most positively associated with exposure: Working with Computers, Written Comprehension, Reading Comprehension, Administrative, and Computers and Electronics.
The physical side is the average of the five properties most negatively associated with exposure: Trunk Strength, Stamina, Performing General Physical Activities, Static Strength, and Gross Body Coordination.
For each occupation, CMP is the cognitive average minus the physical average; for each country, national CMP is the employment-share-weighted average CMP across its measured ISCO-08 occupations.
Higher CMP therefore means that a country’s employment is concentrated in occupations with more computer/document/information-processing content and less physical/manual content. This O\*NET-derived CMP score provides a more task-grounded measure of labor composition and predicts exposure more strongly than the coarse white-collar split, indicating that the underlying cognitive and physical organization of work is the main driver rather than the white-collar label itself.

|  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  | (1) | (2) | (3) | (4) | (5) | (6) | (7) | (8) |
| Specification | WC | GNI | Internet | CMP | WC+GNI | WC+Internet | WC+CMP | Full |
| White-collar share | 0.242\*\*\* |  |  |  | 0.196\*\*\* | 0.212\*\*\* | -0.046\*\*\* | -0.038\*\* |
|  | (0.007) |  |  |  | (0.011) | (0.008) | (0.017) | (0.015) |
| log GNI |  | 0.036\*\*\* |  |  | 0.009\*\*\* |  |  | 0.004\* |
|  |  | (0.002) |  |  | (0.002) |  |  | (0.002) |
| Internet penetration |  |  | 0.157\*\*\* |  |  | 0.031\*\*\* |  | -0.007 |
|  |  |  | (0.010) |  |  | (0.009) |  | (0.007) |
| Cognitive-minus-physical score |  |  |  | 0.105\*\*\* |  |  | 0.124\*\*\* | 0.117\*\*\* |
|  |  |  |  | (0.001) |  |  | (0.007) | (0.007) |
| Observations | 141 | 135 | 130 | 134 | 135 | 130 | 134 | 124 |
| R2R^{2} | 0.907 | 0.772 | 0.669 | 0.973 | 0.928 | 0.925 | 0.975 | 0.979 |

*Note:* Entries report OLS coefficients with HC1 robust standard errors in parentheses. The dependent variable is national AI exposure. Internet penetration is measured as a 0–1 share. Each column uses the complete-case sample for the variables in that specification. \*\*\* p<0.01p<0.01, \*\* p<0.05p<0.05, \* p<0.10p<0.10.

### B.5 Predicting National AI Adoption

We also estimate the full set of models that include or exclude white-collar share, log GNI, and national AI exposure for each of the three observed adoption outcomes.
National AI exposure strongly predicts adoption on its own across all three datasets.
However, once white-collar share and log GNI are included, adding national AI exposure contributes essentially no additional explanatory power and the full-model exposure coefficient is not statistically distinguishable from zero.
This suggests that exposure is useful as a structural summary, while the observed cross-country adoption relationship is largely aligned with broader national labor composition and income.

|  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  | (1) | (2) | (3) | (4) | (5) | (6) | (7) | (8) |
| Panel A: Anthropic Claude (dependent variable: log10(Claude usage / 100k WAP)) | | | | | | | | |
| Specification | Intercept only | White-collar only | log GNI only | Exposure only | White-collar + log GNI | White-collar + exposure | log GNI + exposure | Full model |
| White-collar share |  | 2.761\*\*\* |  |  | 1.123\*\*\* | 1.878\*\*\* |  | 1.112\*\*\* |
|  |  | (0.123) |  |  | (0.270) | (0.545) |  | (0.423) |
| log GNI |  |  | 0.471\*\*\* |  | 0.305\*\*\* |  | 0.336\*\*\* | 0.304\*\*\* |
|  |  |  | (0.020) |  | (0.051) |  | (0.061) | (0.059) |
| National AI exposure |  |  |  | 10.643\*\*\* |  | 3.602\* | 3.561\*\*\* | 0.056 |
|  |  |  |  | (0.453) |  | (2.142) | (1.296) | (1.986) |
| Observations | 114 | 114 | 114 | 114 | 114 | 114 | 114 | 114 |
| R2R^{2} | 0.000 | 0.792 | 0.837 | 0.769 | 0.863 | 0.799 | 0.854 | 0.863 |
| Panel B: OpenAI Signals (dependent variable: OpenAI rank percentile) | | | | | | | | |
| Specification | Intercept only | White-collar only | log GNI only | Exposure only | White-collar + log GNI | White-collar + exposure | log GNI + exposure | Full model |
| White-collar share |  | 1.343\*\*\* |  |  | 0.571\*\*\* | 0.834\*\*\* |  | 0.686\*\*\* |
|  |  | (0.056) |  |  | (0.105) | (0.212) |  | (0.144) |
| log GNI |  |  | 0.215\*\*\* |  | 0.137\*\*\* |  | 0.152\*\*\* | 0.144\*\*\* |
|  |  |  | (0.009) |  | (0.017) |  | (0.025) | (0.021) |
| National AI exposure |  |  |  | 5.215\*\*\* |  | 2.084\*\*\* | 1.761\*\*\* | -0.634 |
|  |  |  |  | (0.219) |  | (0.777) | (0.590) | (0.724) |
| Observations | 88 | 88 | 88 | 88 | 88 | 88 | 88 | 88 |
| R2R^{2} | 0.000 | 0.828 | 0.874 | 0.812 | 0.908 | 0.839 | 0.891 | 0.909 |
| Panel C: Microsoft AI Diffusion (dependent variable: MS GenAI adoption Q1 2026 (% WAP)) | | | | | | | | |
| Specification | Intercept only | White-collar only | log GNI only | Exposure only | White-collar + log GNI | White-collar + exposure | log GNI + exposure | Full model |
| White-collar share |  | 53.981\*\*\* |  |  | 37.123\*\*\* | 45.650\*\*\* |  | 39.374\*\*\* |
|  |  | (4.045) |  |  | (8.541) | (11.606) |  | (11.082) |
| log GNI |  |  | 8.041\*\*\* |  | 2.990\*\* |  | 3.908\*\* | 3.094\* |
|  |  |  | (0.752) |  | (1.381) |  | (1.627) | (1.639) |
| National AI exposure |  |  |  | 203.888\*\*\* |  | 34.030 | 116.761\*\*\* | -11.584 |
|  |  |  |  | (16.654) |  | (38.948) | (38.042) | (50.533) |
| Observations | 106 | 106 | 106 | 106 | 106 | 106 | 106 | 106 |
| R2R^{2} | 0.000 | 0.651 | 0.599 | 0.611 | 0.670 | 0.653 | 0.641 | 0.671 |

*Note:* Entries report OLS coefficients with HC1 robust standard errors in parentheses. The table contains 24 models: three adoption outcomes times eight predictor specifications. Each panel uses the outcome’s complete-case country sample across white-collar share, log GNI, and national AI exposure. \*\*\* p<0.01p<0.01, \*\* p<0.05p<0.05, \* p<0.10p<0.10.

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
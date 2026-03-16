# CCAS Minimum Viable Experiment: Triad Instrument Validation

**Declan Michaels**

*March 15, 2026*

---

## Research Question

Do triad-based self-signification instruments produce statistically distinguishable population-level distributions across groups with known moral framework differences?

This is the foundational empirical question for the entire CCAS architecture. If the instrument detects moral framework variation, everything else is engineering. If it does not, everything else is moot.

---

## Design Summary

Two populations, two moral scenarios, 50 usable respondents per population per scenario. Online recruitment via Prolific. Data collection through a custom web app built with Claude Code. Total budget under $2,000. Timeline: four weeks.

---

## Populations

**Population A (WEIRD baseline).** US-born, college-educated, secular or low-religiosity, white or mixed ethnicity. Prolific's standard demographic filters handle this directly. This population is expected to over-weight care and fairness foundations, constitute the moral agent as an autonomous individual, and restrict the moral domain to harm-based reasoning.

**Population B (framework-divergent).** First-generation South Asian immigrants in the US (Indian, Bangladeshi, Pakistani). Prolific filters for country of birth and ethnicity. This population carries documented differences on moral agent constitution (collectivist orientation), authority legitimacy (hierarchical deference), and moral domain boundary (purity and sanctity as moral categories). Substantial existing MFQ data from India provides a reference baseline for expected divergence.

**Why these two populations.** Cost and recruitment feasibility. Prolific can filter for both populations today. The California pilot populations named in the paper (Hmong, Mexican immigrant, Korean, WEIRD baseline) require community-based recruitment partnerships that take months to establish. This experiment tests whether the instrument works, not whether the full pilot design works. The populations are chosen to maximize expected divergence on the two dimensions being tested, giving the instrument the best chance of detecting a signal if one exists.

**Why this pairing is methodologically strong.** South Asian diaspora communities in the US are demographically integrated on every variable that normally confounds cross-cultural moral measurement: high education levels, high income, high English proficiency, high digital literacy. On a demographic survey, Populations A and B look similar. But South Asian communities maintain distinct moral frameworks through active cultural infrastructure: temples, language schools, dietary practices rooted in purity norms, arranged marriage traditions, multigenerational household expectations, and elder deference structures. This combination strips the demographic confound from the design. If the triads detect distributional differences between two populations that are demographically similar but morally distinct, the instrument is measuring moral framework variation, not income, education, or language differences. A population pairing where the framework-divergent group was also demographically different from the baseline would produce an ambiguous result: did the instrument detect moral frameworks or socioeconomic variables? This pairing eliminates that ambiguity and preemptively addresses the strongest methodological objection a reviewer would raise.

---

## Scenarios

Two scenarios targeting the dimensions with highest expected divergence between these populations.

**Scenario 1: Moral domain boundary.** This is the dimension where WEIRD and South Asian frameworks diverge most sharply. WEIRD populations systematically restrict the moral domain to harm and fairness. South Asian populations extend moral authority to purity, ritual obligation, and bodily practice.

Prompt: *"Tell me about a time when someone was criticized for something they did in private that didn't hurt anyone."*

Triad vertices:
- (A) The criticism was justified
- (B) It was none of their business
- (C) It depends on the community's values

Expected result: Population A clusters toward vertex B (none of their business, individualist moral domain). Population B distributes more broadly, with significant mass toward vertices A and C (the private behavior is morally relevant, the community's values have standing).

**Scenario 2: Moral agent constitution.** The second highest expected divergence. WEIRD populations constitute the moral agent as the autonomous individual. South Asian populations constitute the moral agent relationally, embedded in family and community obligation structures.

Prompt: *"Tell me about a time when someone in your community had to choose between what was best for them and what was best for their family or community."*

Triad vertices:
- (A) They did what was right
- (B) They did what was expected
- (C) They did what kept the peace

Expected result: Population A distributes across the triad with moral evaluation centered on the individual's choice (was it right for them?). Population B distributes with more weight toward the relational vertices (expected, peace-keeping), reflecting that the individual's moral agency is constituted through relationships rather than autonomy.

Each respondent completes both scenarios. Session duration: 15-20 minutes.

---

## Sample Size

**Target: 50 usable respondents per population (100 total).**

**Recruit 60 per population (120 total)** to ensure 50 usable after exclusions for incomplete responses, nonsense narratives, attention check failures, or Prolific quality flags.

**Power analysis:** For detecting a large effect size (Cohen's d = 0.8) in distributional differences on a 2-simplex with 80% power at alpha = 0.05, approximately 30 respondents per group is sufficient. 50 per group provides headroom for exclusions and supports secondary analyses. The primary analysis uses permutation tests on earth mover's distance (EMD) between population-level triad distributions, which are nonparametric and require no distributional assumptions.

---

## The App

A responsive web app with four screens. Built in React, hosted on Vercel (free tier), backed by Supabase (free tier, 50k row limit). Buildable in one day with Claude Code.

**Screen 1: Consent and demographics.**
- Study description and consent checkbox
- Prolific ID (for payment reconciliation)
- Age, gender
- Country of birth
- Years in US (Population B only, implied by birth country)
- Education level
- Religiosity (5-point scale: not at all religious to very religious)
- Primary language at home

**Screen 2: Scenario 1.**
- Prompt displayed at top of screen
- Text input for narrative (minimum 150 characters, approximately 3 sentences)
- After narrative submission, interactive triangle appears
- Brief instruction: "Place a point in the triangle to show how you interpret the story you just told. Placing your point near a corner means that interpretation fits best. Placing it between corners means your interpretation is a mix. Placing it near the center means all three interpretations apply roughly equally."
- Respondent taps or clicks to place point
- Coordinates (x, y) captured relative to equilateral triangle with vertices at known positions
- Confirm button

**Screen 3: Scenario 2.**
- Same flow as Screen 2, second prompt and triad

**Screen 4: Debrief.**
- Thank you message
- Prolific completion code displayed
- Optional: "Is there anything about these questions that felt unclear or uncomfortable?" (free text, for instrument improvement)

**Data captured per respondent:**
- Demographic fields (8-10 fields)
- Scenario 1: narrative text, triad coordinates (x, y), timestamp
- Scenario 2: narrative text, triad coordinates (x, y), timestamp
- Debrief feedback (optional)
- Prolific ID, session duration

---

## Prolific Configuration

**Study 1 (Population A):**
- Prescreening: country of birth = United States, ethnicity = white, education = undergraduate degree or higher, fluent in English
- Custom screener: religiosity question (filter for score 1-3 on 5-point scale)
- Compensation: $8 per respondent
- Estimated session: 20 minutes
- Prolific fee: ~33% on top of compensation
- Slots: 60

**Study 2 (Population B):**
- Prescreening: country of birth = India, Bangladesh, or Pakistan; currently residing in United States; fluent in English
- Compensation: $8 per respondent
- Estimated session: 20 minutes
- Prolific fee: ~33% on top of compensation
- Slots: 60

Both studies run simultaneously. Participants cannot take both studies.

---

## Analysis Plan

### Primary Analysis

Compute earth mover's distance (EMD) between Population A and Population B triad distributions for each scenario separately. The triad simplex is a 2-dimensional space (three vertices, two degrees of freedom). EMD measures the minimum work required to transform one distribution into the other.

**Significance testing:** Permutation test with 10,000 iterations. For each iteration, randomly reassign population labels to all respondents and recompute EMD. The p-value is the proportion of permuted EMDs that equal or exceed the observed EMD. Reject the null hypothesis (no distributional difference) if p < 0.05.

**Expected outcome:** If the Moral Machine data and MFQ literature are correct about these populations, EMD should be significantly larger than chance for both scenarios, with a larger effect for Scenario 1 (moral domain boundary) than Scenario 2 (moral agent constitution).

### Secondary Analyses

**Distribution visualization.** Plot both populations as density heatmaps on the triad simplex for each scenario. Visual inspection reveals whether the populations cluster in different regions, along different edges, or with different center-clustering frequencies.

**Center-clustering diagnostic.** Compute the proportion of each population placing within a defined radius of the triad center. Heavy center-clustering in one population but not the other suggests the triad vertices do not span the moral space for that population. Heavy center-clustering in both populations suggests the triad design is inadequate for this scenario. This is the instrument diagnostic described in the paper.

**Vertex-proximity analysis.** For each population, compute the proportion of placements within a defined radius of each vertex. This produces a coarse three-category distribution (vertex A dominant, vertex B dominant, vertex C dominant) that can be compared directly via chi-square or Fisher's exact test as a robustness check on the EMD result.

**Dimensional independence.** Each respondent completes both scenarios. Compute the correlation between Scenario 1 triad position and Scenario 2 triad position within each population. Low correlation supports the paper's claim that the four dimensions are structurally independent. High correlation suggests they co-vary within populations, which is informative for the architecture but complicates per-dimension analysis.

### Exploratory Narrative Analysis

Read the narratives from respondents whose triad placements fall in regions of high population divergence. Do the narratives reveal different reasoning patterns? This is a qualitative preview of the Stage 2 reasoning analysis the paper proposes. It is exploratory, not confirmatory, and should be reported as such.

---

## Budget

| Item | Low | High | Notes |
|:-----|----:|-----:|:------|
| App development | $0 | $0 | Built with Claude Code. React + Supabase + Vercel. |
| Hosting (Vercel + Supabase) | $0 | $20 | Free tiers sufficient. Custom domain optional. |
| Prolific: Population A (60 respondents) | $480 | $530 | $8/respondent + 33% Prolific fee |
| Prolific: Population B (60 respondents) | $480 | $530 | $8/respondent + 33% Prolific fee |
| Iteration buffer (second round) | $0 | $700 | Second recruitment of 40-60 respondents if first round reveals instrument problems |
| Analysis tools | $0 | $0 | Python (scipy, matplotlib, pot library for EMD). All open source. |
| **Total** | **$960** | **$1,780** |

The iteration buffer is the most important budget line. The first run almost always reveals something: a prompt that confuses respondents, a triad vertex label that channels responses in unexpected ways, a population filter that doesn't produce the expected demographic profile. If the first round works cleanly and produces clear results, the buffer is unspent and total cost is under $1,000.

---

## Timeline

| Week | Activity |
|:-----|:---------|
| 1 | Build app with Claude Code. Deploy on Vercel. Internal testing with 5-10 unpaid respondents (colleagues, friends). Fix UX issues. Set up Prolific account and configure studies. |
| 2 | Launch both Prolific studies. Monitor completion rates, check for obvious data quality issues (all-center placements, copy-paste narratives, sub-30-second sessions). Pause and adjust if problems appear. |
| 3 | Close first-round recruitment. Run primary analysis (EMD + permutation tests). Visualize distributions. Read narratives from divergent regions. Assess whether instrument adjustments are needed. |
| 4 | If adjustments needed: revise prompts or triad labels, recruit second round. If first round is clean: finalize analysis, write up results, prepare summary for Snowden/Dragan/Tennant. |

---

## Success Criteria

**Strong positive result:** Both scenarios produce statistically significant (p < 0.05) EMD differences between populations, with visible distributional separation on the triad simplex. Narrative analysis reveals qualitatively different reasoning patterns in divergent regions. This is the result that makes the paper's architecture credible and changes every subsequent conversation from theoretical to empirical.

**Weak positive result:** One scenario produces significant EMD, the other does not. This suggests the instrument works for some dimensions but not others, or that the triad design for the non-significant scenario needs revision. Still valuable: demonstrates proof of concept on one dimension and identifies where the instrument needs improvement.

**Null result:** Neither scenario produces significant EMD. The populations' triad distributions are indistinguishable. This means either (a) the instrument lacks resolution to detect framework variation that other instruments (MFQ, WVS) detect, (b) online-recruited South Asian immigrants in the US have already converged toward WEIRD moral frameworks, or (c) the prompts and triad designs do not activate the intended dimensions. Each interpretation has different implications. (a) is the most damaging to the paper's architecture. (b) supports the paper's argument about app-only deployment risk. (c) is fixable with instrument revision.

**Diagnostic result:** Heavy center-clustering in Population B on one or both scenarios. This signals that the triad vertices do not adequately span the moral space for that population. The paper predicts this as a possible outcome and interprets it as instrument design signal rather than population indifference. Redesign the triad and retest.

---

## What This Experiment Does Not Test

- The variance-modified reward mechanism (requires RLHF infrastructure and substantially more budget)
- The rationalization layer's three-category classification (requires more than two populations and reasoning analysis)
- Cross-linguistic narrative comparison (both populations respond in English)
- The community facilitator model (uses online recruitment, not facilitators)
- Whether changed training signal produces changed model behavior (requires ML collaboration)

What it tests is the foundation: does the instrument detect what the paper says it should detect?

---

## Relationship to the Paper

This experiment corresponds to the minimum viable study described in Section 10.1 of "Beyond WEIRD Defaults": "deploy moral scenario triads across two populations with known framework differences and test whether SenseMaker triad distributions track those known differences after controlling for demographic confounds."

If the results are positive, they provide the first empirical evidence that the paper's upstream signal collection mechanism works. This evidence transforms the paper from a theoretical architecture into a partially validated one, and transforms conversations with Snowden, Dragan, Leike, and Tennant from "interesting proposal" to "here are the data, what do we do next?"

---

## Next Steps After Results

**If positive:** Share results with Snowden (validates SenseMaker for moral measurement, new commercial territory), Dragan (empirical foundation for a research collaboration or PhD project), Tennant (complementary data for their intrinsic reward approach). Expand to the full California pilot with four populations, four scenarios, and the balanced incomplete block design described in the paper. Seek grant funding or commercial partnership for the expanded pilot.

**If null:** Diagnose which interpretation applies (instrument resolution, population convergence, or scenario design). If instrument resolution, consider whether a different instrument is needed and whether the paper's architecture survives without SenseMaker. If population convergence, this is evidence for the paper's app-deployment-risk argument and motivation for facilitator-based recruitment of less-connected populations. If scenario design, revise and retest within the remaining iteration budget.

# CCAS Minimum Viable Experiment: Constrained Allocation Instrument Validation

**Declan Michaels**

*March 15, 2026 (revised March 19, 2026)*

---

## Research Question

Do constrained allocation instruments using shared stimuli produce statistically distinguishable population-level distributions across groups with known moral framework differences?

This is the foundational empirical question for the entire CCAS architecture. If the instrument detects moral framework variation, everything else is engineering. If it does not, everything else is moot.

---

## Design Summary

Three populations, two moral scenarios, 50 usable respondents per main population per scenario plus a 25-respondent religiosity triangulation cell. Each scenario presents a shared stimulus followed by two sets of constrained allocation sliders (judgment and reasoning). Scenario order is counterbalanced across respondents. Online recruitment via Prolific. Data collection through a custom web app built with Claude Code. Total budget under $2,500. Timeline: four weeks.

---

## Populations

**Population A (WEIRD baseline).** US-born, college-educated, white or mixed ethnicity. Prolific's standard demographic filters handle this directly. Religiosity is captured in demographics but not filtered: respondents across the religiosity spectrum are included, allowing religiosity to vary naturally for modeling purposes. This population is expected to over-weight care and fairness foundations, constitute the moral agent as an autonomous individual, and restrict the moral domain to harm-based reasoning.

**Population B (framework-divergent).** First-generation South Asian immigrants in the US (Indian, Bangladeshi, Pakistani). Prolific filters for country of birth and ethnicity. This population carries documented differences on moral agent constitution (collectivist orientation), authority legitimacy (hierarchical deference), and moral domain boundary (purity and sanctity as moral categories). Substantial existing MFQ data from India provides a reference baseline for expected divergence.

**Why these two populations.** Cost and recruitment feasibility. Prolific can filter for both populations today. The California pilot populations named in the paper (Hmong, Mexican immigrant, Korean, WEIRD baseline) require community-based recruitment partnerships that take months to establish. This experiment tests whether the instrument works, not whether the full pilot design works. The populations are chosen to maximize expected divergence on the two dimensions being tested, giving the instrument the best chance of detecting a signal if one exists.

**Acknowledged limitation: economic framework variation.** Population A (college-educated, secular Americans) is not just culturally WEIRD but economically WEIRD. The paper's Section 3 demonstrates that the four structural dimensions operate along class and economic-history lines within a single culture: a person who grew up navigating poverty treats resource allocation decisions as moral questions (moral domain boundary) and extends the family's claim on individual spending decisions further (scope of moral obligation) than a person who grew up with enough. Prolific's standard pool over-represents college-educated, economically stable respondents in both populations. This means the pilot tests cross-cultural framework variation but not intra-cultural class-based framework variation. A positive result validates the instrument for the cross-cultural case; it does not establish whether the instrument detects the subtler within-culture divergence that economic history produces. A follow-up study recruiting across class lines within a single demographic (e.g., college-educated vs. non-college-educated white Americans matched on age and region) would test that case directly and would be a striking demonstration that the dimensions detect framework variation independent of ethnicity, nationality, or language.

**Why this pairing is methodologically strong.** South Asian diaspora communities in the US are demographically integrated on every variable that normally confounds cross-cultural moral measurement: high education levels, high income, high English proficiency, high digital literacy. On a demographic survey, Populations A and B look similar. But South Asian communities maintain distinct moral frameworks through active cultural infrastructure: temples, language schools, dietary practices rooted in purity norms, arranged marriage traditions, multigenerational household expectations, and elder deference structures. This combination strips the demographic confound from the design. If the instrument detects distributional differences between two populations that are demographically similar but morally distinct, it is measuring moral framework variation, not income, education, or language differences. A population pairing where the framework-divergent group was also demographically different from the baseline would produce an ambiguous result: did the instrument detect moral frameworks or socioeconomic variables? This pairing eliminates that ambiguity and preemptively addresses the strongest methodological objection a reviewer would raise.

**Population C (religiosity triangulation).** US-born, college-educated, white, moderately to highly religious (religiosity score 4-5 on 5-point scale). Target: 25 usable respondents, recruit 30. This small cell resolves an ambiguity that would otherwise weaken a positive result. Population B is expected to be more religious than Population A on average. Without Population C, a positive EMD result could reflect a secular-vs-religious divide rather than a WEIRD-vs-collectivist framework divide. Population C disentangles the two. If religious white Americans distribute similarly to Population B on the moral domain boundary scenario (Scenario 1), religiosity is doing the work and the framework interpretation is weakened. If religious white Americans distribute similarly to the rest of Population A despite higher religiosity, the framework variation operates through cultural infrastructure (temples, dietary practices, family obligation structures) rather than religiosity per se. This triangulation adds approximately $300 to the budget and dramatically strengthens the interpretation of the primary result. Population C is analyzed only on Scenario 1, where the purity/sanctity dimension makes the religiosity confound most acute.

---

## Scenarios

Two scenarios targeting the dimensions with highest expected divergence between these populations. Each scenario presents a shared stimulus followed by two sets of constrained allocation sliders: judgment (how the respondent interprets the situation) and reasoning (why).

**Scenario 1: Moral domain boundary.** This is the dimension where WEIRD and South Asian frameworks diverge most sharply. WEIRD populations systematically restrict the moral domain to harm and fairness. South Asian populations extend moral authority to purity, ritual obligation, and bodily practice.

Stimulus: *A man is publicly criticized by his neighbors for how he spends his weekends in a way some neighbors find distasteful, though no one is directly affected.*

Judgment sliders (respondent distributes 100 points):
- The criticism was justified
- It was none of their business
- It depends on the community's values

Reasoning sliders (respondent distributes 100 points):
- Because a community has the right to uphold its standards
- Because private behavior is outside the moral domain
- Because community norms reflect collective wisdom
- Other (user-labeled)

Expected result: Population A concentrates weight on "none of their business" (individualist moral domain). Population B distributes more broadly, with significant weight toward "justified" and "depends on the community's values" (the private behavior is morally relevant, the community's values have standing). Reasoning distributions reveal whether convergent judgments rest on shared or divergent reasoning.

**Scenario 2: Moral agent constitution.** The second highest expected divergence. WEIRD populations constitute the moral agent as the autonomous individual. South Asian populations constitute the moral agent relationally, embedded in family and community obligation structures.

Stimulus: *A young woman turns down a job in another city because her mother is seriously ill.*

Judgment sliders (respondent distributes 100 points):
- She was morally right because of her family obligation
- She was morally right because it was her personal choice
- This is not a moral situation, just a personal decision

Reasoning sliders (respondent distributes 100 points):
- Because family obligation comes before personal goals
- Because she would have carried the guilt
- Because the community would have judged her
- Other (user-labeled)

Expected result: Population A distributes judgment weight toward "personal choice" and "not a moral situation" (moral evaluation centered on the individual's autonomy, or framing the decision as non-moral entirely). Population B distributes with more weight toward "family obligation" (the relational framing where family duty is the morally salient feature). The three options stay within the moral frame or explicitly name the non-moral frame, avoiding constructs like "expected" or "kept the peace" that carry different connotations across populations (normative conformity in WEIRD contexts versus moral duty in collectivist contexts). The reasoning sliders test whether populations that agree on judgment reach that agreement through the same reasoning.

**Design note on Scenario 2 labels:** An earlier version used "did what was right / did what was expected / did what kept the peace." Multi-model review identified that "expected" carries negative connotations (conformity pressure) in WEIRD frameworks and positive connotations (moral duty) in collectivist frameworks. The revised labels keep all options explicitly moralized or explicitly non-moral, so distributional differences reflect framework variation rather than label interpretation.

Each respondent completes both scenarios in counterbalanced order: half see Scenario 1 first, half see Scenario 2 first. Order is randomly assigned at session start and logged. Order effects are tested as a secondary analysis (compare EMD computed from Scenario-1-first respondents vs. Scenario-2-first respondents). After each scenario, a single manipulation check item asks: "How morally relevant is this situation to you?" (5-point Likert scale). This provides an independent signal that the scenario activated moral reasoning and allows correlation with distributional spread. Session duration: 15-20 minutes.

---

## Sample Size

**Target: 50 usable respondents per population (100 total).**

**Recruit 60 per population (120 total)** to ensure 50 usable after exclusions for incomplete responses, attention check failures, or Prolific quality flags.

**Sample size rationale:** There is no established power analysis framework for EMD on simplex distributions; the standard Cohen's d framework does not apply because the test statistic is a distributional distance, not a difference of means. The 50-per-group target is based on three practical considerations: (1) density estimation on a simplex requires sufficient samples to resolve distributional shape, and simulation studies suggest 30-50 points produce stable kernel density estimates (Duong, 2007); (2) the Bartels et al. studies (2018, 2019) achieved interpretable population-level patterns with subgroups of similar size using a related self-signification instrument; (3) the permutation test makes no distributional assumptions, so the main risk is insufficient sample density to resolve shape differences rather than insufficient statistical power in the classical sense. 50 per group provides headroom for exclusions and supports secondary analyses. Recruiting 60 ensures 50 usable.

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
- Shared stimulus displayed at top of screen
- Brief instruction: "Read the story above, then distribute 100 points across the interpretations below to show how you see this situation. Giving more points to an option means it fits your view better."
- Judgment sliders: three labeled options with numeric inputs. Respondents allocate freely (no auto-adjustment of other sliders when one changes). A running total is displayed. On confirmation, if the total does not equal 100, allocations are normalized proportionally and the respondent sees a confirmation screen: "Your allocations have been adjusted proportionally to sum to 100. Does this look right?" with the adjusted values displayed. This avoids both manual-summing frustration and the confound of auto-adjusting algorithms that become part of the instrument.
- After judgment allocation is confirmed, reasoning sliders appear
- Brief instruction: "Now distribute 100 points across the reasons below to show why you see it that way."
- Reasoning sliders: three labeled options plus a user-labeled "other" option, constrained to sum to 100
- If respondent allocates any weight to "other," a text field appears for them to label their reason
- Confirm button

**Screen 3: Scenario 2.**
- Same flow as Screen 2, second stimulus and slider sets

**Attention checks.** Three quality checks are embedded in the study: (1) A single attention-check item in the demographics section ("For this question, please select 'Agree'") to catch inattentive respondents. (2) Post-hoc time filter: respondents who complete a scenario faster than the fastest genuine completion observed during internal testing are flagged for review. The threshold is determined empirically during Week 1 testing (5-10 unpaid respondents with screen recording), not set a priori. The app logs individual interaction events (first slider touch, last slider touch, confirm button timestamp) so that "read fast, allocated thoughtfully" can be distinguished from "clicked through without reading." Flagged respondents are excluded only if their allocations also show minimal engagement (e.g., all weight on a single option for both slider sets). (3) Prolific's built-in quality metrics (approval rate > 95%, previous submissions flagged for quality) provide additional screening.

**Screen 4: Debrief.**
- Thank you message
- Prolific completion code displayed
- Semantic probe (2 items): "In your own words, what does 'community standards' mean in the first story?" and "In your own words, what does 'family obligation' mean in the second story?" (free text, 1-2 sentences each). These detect whether key terms carry different meanings across populations. High divergence in probe responses flags semantic interpretation drift as a confound.
- Optional: "Is there anything about these questions that felt unclear or uncomfortable?" (free text, for instrument improvement)

**Data captured per respondent:**
- Demographic fields (8-10 fields)
- Scenario 1: judgment slider allocations (array summing to 100), reasoning slider allocations (array summing to 100), "other" label text (if used), timestamp
- Scenario 2: judgment slider allocations, reasoning slider allocations, "other" label text (if used), timestamp
- Debrief feedback (optional)
- Prolific ID, session duration

---

## Prolific Configuration

**Study 1 (Population A):**
- Prescreening: country of birth = United States, ethnicity = white, education = undergraduate degree or higher, fluent in English
- No religiosity filter. Religiosity is captured in demographics (5-point scale) and modeled explicitly in analysis rather than filtered out. An earlier version excluded moderately and highly religious respondents to maximize WEIRD contrast. Multi-model review identified that this created an ambiguity: a positive result could reflect a secular-vs-religious divide rather than a framework divide, and the partial permutation test cannot distinguish between "religiosity is a confound" and "religiosity is a component of the framework you just removed." Letting religiosity vary naturally in Population A, combined with Population C (below), resolves this cleanly.
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

**Study 3 (Population C -- religiosity triangulation):**
- Prescreening: country of birth = United States, ethnicity = white, education = undergraduate degree or higher, fluent in English
- Custom screener: religiosity score 4-5 on 5-point scale (moderately to highly religious)
- Compensation: $8 per respondent
- Estimated session: 20 minutes
- Prolific fee: ~33% on top of compensation
- Slots: 30

All three studies run simultaneously. Participants cannot take more than one study.

**Pre-launch decision rule for Population B pool.** Run the Prolific audience estimator for all three prescreens before building the app. If Population B eligible pool is under 50, switch the entire Population B to UK-resident South Asians rather than mixing US and UK residents. A mixed-residence population adds a confound without adding power. Document the decision and rationale.

**Recruitment risk for Population B.** Prolific's participant pool skews UK-heavy for South Asian users. The intersection of "born in India/Bangladesh/Pakistan" AND "currently residing in United States" AND "fluent in English" may produce a smaller available pool than 60 requires. Check Prolific's pool estimator before launch. If the US-resident pool is insufficient, the fallback is to extend recruitment to UK-resident South Asians, with the tradeoff being a different host-country institutional context (NHS vs. US healthcare, different immigration dynamics). This is methodologically acceptable because the framework differences being tested (collectivist moral agent constitution, purity-based moral domain extension) are maintained by cultural infrastructure (temples, dietary practices, family structures) that operate similarly in both UK and US diaspora contexts. Document which host country each respondent resides in and test whether host country moderates the EMD result.

---

## Analysis Plan

### Primary Analysis

Compute earth mover's distance (EMD) between Population A and Population B slider distributions for each scenario separately, for both judgment and reasoning sliders. Each respondent's slider allocation is a point on a simplex (three or four values summing to 1, after normalizing from the 100-point allocation). EMD measures the minimum work required to transform one population's distribution into the other, using a uniform ground metric (all simplex vertices equidistant). The uniform metric is the appropriate default when no principled basis exists for assigning semantic distances between moral interpretations (Rubner et al., 2000).

Four EMD scores are computed: Scenario 1 judgment, Scenario 1 reasoning, Scenario 2 judgment, Scenario 2 reasoning. Implementation: 1-Wasserstein distance on the simplex using the Python POT (Python Optimal Transport) library, `ot.emd2` function with uniform ground distance matrix. Code and exact function calls will be pre-registered on OSF before recruitment begins.

**Ground metric sensitivity analysis.** The uniform metric treats all simplex vertices as equidistant. This is the appropriate default when no principled basis exists for assigning semantic distances between moral interpretations, but the moral categories may not be truly equidistant (e.g., "justified" vs. "depends on community values" may be closer than either is to "none of their business"). As a robustness check, recompute EMD under a simple ordinal metric where adjacent categories (on a defensible ordering) have distance 1 and non-adjacent have distance 2. If results are stable across both metrics, the finding is robust to metric choice. If not, the ground metric is doing meaningful work and needs principled justification.

**Significance testing:** Permutation test with 10,000 iterations per EMD score. For each iteration, randomly reassign population labels to all respondents and recompute EMD. The p-value is the proportion of permuted EMDs that equal or exceed the observed EMD. Reject the null hypothesis (no distributional difference) if p < 0.05.

**Expected outcome:** If the Moral Machine data and MFQ literature are correct about these populations, judgment EMD should be significantly larger than chance for both scenarios, with a larger effect for Scenario 1 (moral domain boundary) than Scenario 2 (moral agent constitution). Reasoning EMD provides the additional signal the paper's architecture requires: do populations that converge on judgment also converge on reasoning (candidate universal), or do they reach similar judgments through different reasoning paths (contingent agreement)?

### Secondary Analyses

**Distribution visualization.** Plot both populations as density heatmaps on the simplex for each scenario and slider set. Visual inspection reveals whether the populations cluster in different regions, along different edges, or with different spread patterns.

**"Other" usage diagnostic.** Compute the proportion of each population allocating any weight to "other" on the reasoning sliders, and the proportion allocating more than 20 points to "other." High "other" usage in one population but not the other signals that the reasoning options do not span the moral reasoning space for that population. This is the instrument's self-diagnostic: high "other" rates indicate where the slider labels need revision, not where the population is indifferent. Qualitative analysis of the "other" labels reveals what reasoning the instrument designers missed.

**Extreme-allocation diagnostic.** Compute the proportion of each population placing 90+ points on a single judgment option. Heavy extreme-allocation in both populations suggests the judgment options produce forced-choice-like behavior despite the constrained allocation format. This would undermine the distributional resolution the instrument is designed to provide and would indicate that slider labels need revision to invite more nuanced allocation.

**Dimensional independence.** Each respondent completes both scenarios. Compute the correlation between Scenario 1 judgment allocations and Scenario 2 judgment allocations within each population. Low correlation supports the paper's claim that the structural dimensions are independent. High correlation suggests they co-vary within populations, which is informative for the architecture but complicates per-dimension analysis.

**Order effects.** Compare EMD computed from respondents who saw Scenario 1 first vs. those who saw Scenario 2 first. If the EMD difference between orderings is substantial, scenario priming is present and the within-subject design needs revision. If negligible, counterbalancing was sufficient.

**Religiosity triangulation (Population C).** Compute EMD between Population C (religious white Americans) and Population A on Scenario 1 judgment sliders. Compare to EMD between Population B and Population A on the same sliders. If Population C clusters with Population B (high EMD from Population A), religiosity is a primary driver of the moral domain boundary signal. If Population C clusters with Population A (low EMD from Population A despite high religiosity), the framework variation operates through cultural infrastructure rather than religiosity. This analysis is the primary purpose of Population C and the key to interpreting the main result.

**"Other" option position note.** The "other" option appears last in the reasoning slider set across all respondents. This could suppress "other" usage if respondents who find a partial fit early allocate there and never reach the final option. The suppression likely affects both populations equally (no bias on the population comparison) but could understate the true rate of reasoning-space gaps. Noted as a known limitation. Randomizing "other" position was considered but rejected for this pilot to avoid UX inconsistency; the fixed position is documented for interpretation.

**Classification function preview.** For each scenario, apply the paper's two-stage classification logic: if judgment EMD falls below a threshold, check reasoning EMD. This produces a preliminary classification (candidate universal, contingent agreement, or cultural contingency) for each dimension with these two populations. The threshold is determined from the natural clustering in the four EMD scores rather than set a priori. This is exploratory, not confirmatory -- two populations cannot validate a classification function designed for multiple populations -- but it previews whether the classification machinery produces interpretable results.

---

## Ethics

This study collects moral judgments from human participants using shared stimuli. Ethical requirements:

**Informed consent.** Participants receive a study description on Screen 1 explaining that they will be asked to read short stories about moral situations and indicate how they interpret them using slider tools. They are informed that their responses are anonymous (linked only to Prolific ID for payment), that data will be used for research on moral framework measurement, and that they may withdraw at any time without penalty. Consent is recorded via checkbox before any data is collected.

**IRB or equivalent review.** If conducted through an institutional affiliation, IRB approval or exemption determination is required before launch. If conducted independently, Prolific's own ethics review process provides baseline coverage (Prolific requires all studies to meet their ethical guidelines, including informed consent, right to withdraw, and fair compensation). In either case, the study protocol should be reviewed by at least one person with human subjects research training before recruitment begins. The scenarios present everyday moral situations (community criticism, family obligation), not personal trauma, and the shared stimulus format means respondents interpret a third-person story rather than disclosing personal experiences, minimizing risk of distress.

**Data protection.** Slider allocations and "other" labels are stored in Supabase with row-level security. Prolific IDs are stored separately from response data and used only for payment reconciliation. No identifying information (names, locations, specific institutions) is solicited. Published results will use aggregate distributions and anonymized "other" labels only.

---

## Budget

| Item | Low | High | Notes |
|:-----|----:|-----:|:------|
| App development | $0 | $0 | Built with Claude Code. React + Supabase + Vercel. |
| Hosting (Vercel + Supabase) | $0 | $20 | Free tiers sufficient. Custom domain optional. |
| Prolific: Population A (60 respondents) | $480 | $530 | $8/respondent + 33% Prolific fee |
| Prolific: Population B (60 respondents) | $480 | $530 | $8/respondent + 33% Prolific fee |
| Prolific: Population C (30 respondents) | $240 | $265 | $8/respondent + 33% Prolific fee |
| Iteration buffer (second round) | $0 | $700 | Second recruitment of 40-60 respondents if first round reveals instrument problems |
| Analysis tools | $0 | $0 | Python (scipy, matplotlib, pot library for EMD). All open source. |
| OSF pre-registration | $0 | $0 | Free. Register analysis plan before recruitment. |
| **Total** | **$1,200** | **$2,045** |

The iteration buffer is the most important budget line. The first run almost always reveals something: a stimulus that confuses respondents, a slider label that channels responses in unexpected ways, a population filter that doesn't produce the expected demographic profile. If the first round works cleanly and produces clear results, the buffer is unspent and total cost is under $1,000.

---

## Timeline

| Week | Activity |
|:-----|:---------|
| 1 | Build app with Claude Code. Deploy on Vercel. Internal testing with 5-10 unpaid respondents (colleagues, friends). Fix UX issues. Set up Prolific account and configure studies. |
| 2 | Launch both Prolific studies. Monitor completion rates, check for obvious data quality issues (all-single-option allocations, sub-30-second sessions). Pause and adjust if problems appear. |
| 3 | Close first-round recruitment. Run primary analysis (EMD + permutation tests for all four slider sets). Visualize distributions. Check "other" usage rates. Assess whether instrument adjustments are needed. |
| 4 | If adjustments needed: revise slider labels or stimuli, recruit second round. If first round is clean: finalize analysis, write up results, prepare summary for collaborators. |

---

## Success Criteria

**Strong positive result:** Both scenarios produce statistically significant (p < 0.05) judgment EMD differences between populations, with visible distributional separation on the simplex. Reasoning EMD reveals whether convergent judgments rest on shared or divergent reasoning. "Other" usage is low in both populations (reasoning options span the space). This is the result that makes the paper's architecture credible and changes every subsequent conversation from theoretical to empirical.

**Weak positive result:** One scenario produces significant judgment EMD, the other does not. This suggests the instrument works for some dimensions but not others, or that the stimulus or slider labels for the non-significant scenario need revision. Still valuable: demonstrates proof of concept on one dimension and identifies where the instrument needs improvement.

**Null result:** Neither scenario produces significant judgment EMD. The populations' slider distributions are indistinguishable. This means either (a) the instrument lacks resolution to detect framework variation that other instruments (MFQ, WVS) detect, (b) online-recruited South Asian immigrants in the US have already converged toward WEIRD moral frameworks, (c) the stimuli and slider designs do not activate the intended dimensions, or (d) the instrument detects distributional differences but not along the assumed dimensions -- the variation exists but the scenarios target the wrong structural axes. Each interpretation has different implications. (a) is the most damaging to the paper's architecture. (b) supports the paper's argument about app-only deployment risk. (c) is fixable with instrument revision. (d) is actually a valuable outcome: it means the instrument has resolution but the dimensional framework needs revision, which is exactly what a pilot is for.

**High "other" diagnostic result:** One or both populations allocate substantial weight to "other" on the reasoning sliders. This signals that the pre-defined reasoning options do not span the moral reasoning space for that population. The paper predicts this as a possible outcome and interprets it as instrument design signal rather than population indifference. Qualitative analysis of the "other" labels reveals what reasoning the designers missed. Redesign the reasoning sliders and retest.

---

## What This Experiment Does Not Test

- The variance-modified reward mechanism (requires RLHF infrastructure and substantially more budget)
- The classification function's three-category output at scale (requires more than two populations)
- Cross-linguistic comparison (both populations respond in English)
- The community facilitator model (uses online recruitment, not facilitators)
- Whether changed training signal produces changed model behavior (requires ML collaboration)

What it tests is the foundation: does the instrument detect what the paper says it should detect?

**An important distinction:** This experiment tests whether the instrument detects *known* framework differences (sensitivity). The paper's architecture needs the instrument to detect framework differences that *aren't already known* (discovery power). A positive result here demonstrates instrument resolution but not discovery power. The logical next validation step, after this pilot succeeds, is deploying the instrument on a dimension where strong priors about expected distributions do not exist and assessing whether the results are interpretable.

**Pre-registration.** The full analysis plan (EMD implementation, permutation test parameters, success thresholds, secondary analysis specifications) will be pre-registered on OSF (Open Science Framework) before recruitment begins. This commits the analytical decisions in advance and prevents post-hoc adjustment of thresholds to fit the data.

---

## Relationship to the Paper

This experiment corresponds to the minimum viable study described in Section 9 of "Beyond WEIRD Defaults": deploying the constrained allocation instrument across two populations with known framework differences and testing whether slider distributions track those known differences after controlling for demographic confounds.

If the results are positive, they provide the first empirical evidence that the paper's upstream signal collection mechanism works. This evidence transforms the paper from a theoretical architecture into a partially validated one, and transforms conversations with potential collaborators from "interesting proposal" to "here are the data, what do we do next?"

---

## Next Steps After Results

**If positive:** Share results with potential academic collaborators. Expand to the full California pilot with four populations, four scenarios, and the balanced incomplete block design described in the paper. Seek grant funding or collaboration partnership for the expanded pilot.

**If null:** Diagnose which interpretation applies (instrument resolution, population convergence, or scenario design). If instrument resolution, consider whether the constrained allocation format needs modification or whether additional collection mechanisms are needed. If population convergence, this is evidence for the paper's app-deployment-risk argument and motivation for facilitator-based recruitment of less-connected populations. If scenario design, revise stimuli and slider labels and retest within the remaining iteration budget.

---

## Design Review Methodology

This experiment design was stress-tested by four AI models (ChatGPT, Gemini, Grok, Claude) via direct text review in March 2026. Each model reviewed the full document independently. The reviews were compared for convergence (issues multiple models identified independently) and unique findings (issues only one model caught). Convergent findings were treated as high-priority revisions; unique findings were evaluated individually on merit.

Key convergent findings (all four models): religiosity handling needed revision; Population B selection was the strongest methodological feature; EMD + permutation approach was confirmed as correct; overall verdict was "run it with refinements." Key unique findings incorporated: Scenario 1 stimulus cued the WEIRD answer (Claude), religiosity triangulation cell resolves the confound (Claude), pre-register on OSF (Grok), manipulation check item (Grok), Scenario 2 label ambiguity (ChatGPT), slider mechanics specification (Claude).

The multi-model review process itself produced a finding relevant to the project's thesis: each model found issues the others missed, and no single model found everything. The combined assessment was stronger than any individual review. This is the same convergence-from-independent-sources logic the paper argues for in moral frameworks.

---

## Key References

*Each reference links to its [annotated bibliography](./pilot-experiment-annotated-bibliography.md) entry.*

[Henrich, J., Heine, S. J., & Norenzayan, A. (2010)](./pilot-experiment-annotated-bibliography.md#henrich-2010). The weirdest people in the world? *Behavioral and Brain Sciences*, 33(2-3), 61-83. [doi.org/10.1017/S0140525X0999152X](https://doi.org/10.1017/S0140525X0999152X)

[Haidt, J. (2012)](./pilot-experiment-annotated-bibliography.md#haidt-2012). *The Righteous Mind: Why Good People Are Divided by Politics and Religion.* Vintage Books.

[Graham, J., Haidt, J., Koleva, S., Motyl, M., Iyer, R., Wojcik, S. P., & Ditto, P. H. (2013)](./pilot-experiment-annotated-bibliography.md#graham-2013). Moral foundations theory: The pragmatic validity of moral pluralism. *Advances in Experimental Social Psychology*, 47, 55-130. [doi.org/10.1016/B978-0-12-407236-7.00002-4](https://doi.org/10.1016/B978-0-12-407236-7.00002-4)

[Shweder, R. A., Much, N. C., Mahapatra, M., & Park, L. (1997)](./pilot-experiment-annotated-bibliography.md#shweder-1997). The "big three" of morality (autonomy, community, divinity). In A. Brandt & P. Rozin (Eds.), *Morality and Health* (pp. 119-169). Routledge.

[Awad, E., Dsouza, S., Kim, R., Schulz, J., Henrich, J., Shariff, A., Bonnefon, J.-F., & Rahwan, I. (2018)](./pilot-experiment-annotated-bibliography.md#awad-2018). The Moral Machine experiment. *Nature*, 563(7729), 59-64. [doi.org/10.1038/s41586-018-0637-6](https://doi.org/10.1038/s41586-018-0637-6)

[Van der Merwe, S. E., Biggs, R., Preiser, R., Cunningham, C., Snowden, D. J., O'Brien, K., et al. (2019)](./pilot-experiment-annotated-bibliography.md#vandermerwe-2019). Making sense of complexity: Using SenseMaker as a research tool. *Systems*, 7(2), 25. [doi.org/10.3390/systems7020025](https://doi.org/10.3390/systems7020025)

[Bartels, S. A., Michael, S., Roupetz, S., Garbern, S., Kilzar, L., Bergquist, H., et al. (2018)](./pilot-experiment-annotated-bibliography.md#bartels-2018). Making sense of child, early and forced marriage among Syrian refugee girls. *BMJ Global Health*, 3(1), e000509. [doi.org/10.1136/bmjgh-2017-000509](https://doi.org/10.1136/bmjgh-2017-000509)

[Bartels, S. A., Michael, S., Vahedi, L., Collier, A., Kelly, J., Davison, C., et al. (2019)](./pilot-experiment-annotated-bibliography.md#bartels-2019). SenseMaker as a monitoring and evaluation tool. *Evaluation and Program Planning*, 77, 101715. [doi.org/10.1016/j.evalprogplan.2019.101715](https://doi.org/10.1016/j.evalprogplan.2019.101715)

[Rubner, Y., Tomasi, C., & Guibas, L. J. (2000)](./pilot-experiment-annotated-bibliography.md#rubner-2000). The earth mover's distance as a metric for image retrieval. *International Journal of Computer Vision*, 40(2), 99-121. [doi.org/10.1023/A:1026543900054](https://doi.org/10.1023/A:1026543900054)

[Duong, T. (2007)](./pilot-experiment-annotated-bibliography.md#duong-2007). ks: Kernel density estimation and kernel discriminant analysis for multivariate data in R. *Journal of Statistical Software*, 21(7), 1-16. [doi.org/10.18637/jss.v021.i07](https://doi.org/10.18637/jss.v021.i07)

[Atari, M., et al. (2023)](./pilot-experiment-annotated-bibliography.md#atari-2023). Morality beyond the WEIRD: How the nomological network of morality varies across cultures. *Journal of Personality and Social Psychology*. [doi.org/10.1037/pspp0000470](https://doi.org/10.1037/pspp0000470)

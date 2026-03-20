# RH.md -- CCAS Project Context
### Claude + Declan | Cross-Cultural Alignment Signal

> **Purpose:** Project-specific context for the CCAS repo. For general working relationship, operating principles, and biographical context, see the master RH.md at `/Users/declanmichaels/Library/Mobile Documents/com~apple~CloudDocs/Claude.AI/RH.md`.

---

## Project Status (March 19, 2026)

Project complete and public. Repo reorganized, all documents cross-linked, LinkedIn and Reddit posts published.

**Anchor paper:** "One Shot: The Strategic Risk of Testing Diverse Moral Signal at the Wrong Integration Point" (one-shot.md). ~3,200 words, 9 references. Makes one argument: representational geometry is key to cultural competency; if you try bolt-on first you may never get to try again. Drafted March 19, revised through four cold reads (ChatGPT, Gemini, Grok, Claude), all converged on "high-quality position paper, testable hypothesis worth testing."

**Technical companion:** "Beyond WEIRD Defaults" (BeyondWEIRDdefaults.md). ~8,000 words, 35 references. Full architecture: instrument design, classification function, two-mechanism training protocol, evaluation rubric, positioning against existing work.

**Experiments:** Three designs specified in enough detail to execute. Pilot instrument validation (~$2K, Prolific, South Asian diaspora vs. WEIRD baseline). Training experiment (variance-weighted DPO + dimensional SFT, 2x2 ablation on Llama 8B). SAE mechanistic diagnostic (genuine framework awareness vs. sycophantic wrapping vs. superposed interference).

---

## Architecture Summary

**Instrument:** Shared stimulus + constrained allocation sliders (judgment + reasoning). Both produce simplex data analyzed via EMD. User-labeled "other" as self-diagnostic. SenseMaker cited as intellectual origin, not the instrument itself.

**Classification function:** Two EMD inputs (judgment distributions, reasoning distributions). Outputs: candidate universal (both converge), contingent agreement (judgment converges, reasoning diverges), cultural contingency (judgment diverges).

**Training:** Two mechanisms. Variance-weighted DPO teaches where to be uncertain. Supervised dimensional training (SFT) teaches why and which dimensions. Neither works alone. Sequence matters: SFT before DPO.

**Evaluation:** Four-tier rubric. Tier 1: silent default. Tier 2: flagged ambiguity. Tier 3: framework-aware. Tier 4: calibrated confidence ("confident about the map, humble about the territory"). Key design principle: Tier 4 asks the right clarifying question rather than presenting a framework menu. "Tier 3 is a professor. Tier 4 is a colleague who gets it."

**Four structural dimensions:** Moral agent constitution, authority legitimacy, moral domain boundary, scope of moral obligation. Two candidate additions: epistemic source of moral knowledge, temporal horizon of moral consequences.

---

## Repo Structure

Root: one-shot.md, BeyondWEIRDdefaults.md, annotated-bibliography-full.md, README.md, LICENSE
experiments/: pilot, training, SAE + their annotated bibliographies (6 files)
companions/: dimensional robustness, tier examples, divergence map, plain language guide (4 files)
context/: case study, collaboration reflection, cold reads (.gitignored), outreach messages (.gitignored)

---

## Reference Infrastructure

All 9 documents with references carry: full author lists (6-author rule), source URLs (DOI/arXiv/ACL Anthology/SEP), deep links from reference lists to annotated bibliography entries via HTML anchors. Books without URLs left as-is.

**Citation convention:** First-author inline citations (e.g., "Dohare et al. 2024"). Full author lists in reference lists only. List first six authors before "et al."

---

## Key Decisions (Resolved)

1. **Upstream integration, not post-hoc correction.** Diverse moral signal must enter during initial alignment. Post-hoc is the minimum viable fallback.
2. **Instrument: sliders, not triads.** Evolved through SenseMaker triads, dual triads, then sliders when Declan identified triads lock you into three options. Personal narratives dropped.
3. **Paper split.** Cold reads converged: 11K words from a non-credentialed author won't get read. One Shot leads with strategic risk. BeyondWEIRDdefaults becomes the technical companion.
4. **Noise floor: psychometric, not clinical.** Listing mental disorders looked like pathologizing dissent. Rewritten as standard measurement noise; dual-input design as its own noise detector.
5. **Three categories are emergent, not imposed.** They fall out of two-dimensional convergence space with a logical dependency.
6. **Non-WEIRD voices in references.** Mills, Hwang, Gyekye, Miller & Bersoff added.
7. **Calibrated humility, not better morals.** What changes is what gets frozen confidently.
8. **Static weights at versioned intervals.** Large models must never self-modify during deployment. Full treatment planned as separate work (I/O capacity paper).

---

## Outreach Targets

1. **Iason Gabriel** (Google DeepMind, AGI & Society team lead) -- "global value alignment gap" is our thesis. Complementary to Gabriel & Keeling 2025. Best institutional entry point.
2. **Jan Leike** (Anthropic, Alignment Science co-lead) -- Durmus et al. is Anthropic's own measurement of the problem. Have email.
3. **Elliot Tennant** (UCL/Bologna) -- Hybrid alignment continuum paper. Early-career, most likely to respond.
4. **Dave Snowden** -- SenseMaker intellectual lineage. Methodology/commercial angle, not co-authorship.
5. **Anca Dragan** (Google DeepMind, AI Safety & Alignment Director) -- Colleague of Gabriel. Send after Gabriel.

Messages drafted in context/outreach-messages-march19.md (.gitignored).

---

## Core Thesis (Sharpest Formulation)

"If we want a model to recognize moral questions across frameworks, we must build in the intuition or pay a high computational price for poorer performance."

Not empirically proven. Structural prediction supported by convergent evidence from: plasticity loss in neural networks (Nikishin, Lyle, Dohare), Haidt's social intuitionist model applied to representational geometry, representational deficit in human L2 acquisition (Lardiere), and English-centric latent representations in multilingual LLMs. None prove the moral framework case. All predict the same thing.

---

## Pending

- Push to GitHub and verify all deep links resolve
- Check collaboration reflection exchange for outdated terminology
- Send outreach messages (priority: Gabriel, Leike, Tennant, Snowden, Dragan)
- Revise case study draft based on Declan's review
- Curriculum ordering paper started as separate project (-Curriculum-Ordering-Paper-/)

---

## Pilot Experiment Review Items (from multi-model stress testing, March 19)

*ChatGPT produced three hallucinated reviews before being given the actual text. Fourth review (text pasted directly) was substantive. Additional model reviews pending.*

**Actionable items from ChatGPT review #4 (actual read):**

1. **Scenario 2 construct ambiguity (HIGH PRIORITY).** "Right / expected / kept the peace" mixes moral evaluation with social description. "Expected" may carry negative connotations (normative conformity) for WEIRD respondents and positive connotations (moral duty) for South Asian respondents. Same slider, different semantics. Suggested fix: reframe all options within the moral frame (e.g., "morally right because of family obligation / morally right because it was her personal choice / not a moral issue, just a personal decision"). Worth serious consideration.

2. **Religiosity as causal pathway, not just confounder.** Filtering Population A to low-religiosity makes them maximally WEIRD but risks a confound: religiosity is part of the moral framework infrastructure for Population B, not separable from it. Suggested fix: let religiosity vary naturally in both groups, model it explicitly via regression or stratified permutation test rather than filtering it out. Methodologically stronger than current design.

3. **Semantic interpretation drift across populations.** Terms like "community standards," "obligation," "private" may not map cleanly across frameworks even in shared English. EMD differences could reflect label interpretation, not framework differences. Suggested fix: add a simple post-task probe on 1-2 key terms ("In your own words, what does 'community standards' mean here?"). Low cost, high value.

4. **Ground metric sensitivity analysis.** Uniform metric treats all simplex vertices as equidistant, but the moral categories may not be semantically equidistant. Suggested fix: run EMD under both uniform and an alternative ordinal metric, report whether results are stable. Already acknowledged in the document as a limitation; testing it strengthens the finding.

5. **Test-retest reliability subset.** Re-contact ~20 participants after 3-5 days, re-run one scenario. Gives instrument reliability data. Not currently in the design. Low cost addition.

6. **100-point allocation pseudo-precision.** Forcing fine-grained allocation may produce noise disguised as structure. Suggested robustness check: test with coarser allocation (10 tokens or discrete steps). Note: the extreme-allocation diagnostic already partially addresses this.

7. **Fourth null interpretation.** Current null result section lists three interpretations (instrument resolution, population convergence, bad stimuli). Missing: the instrument detects differences but not along the assumed dimensions. This is a valuable outcome, not a failure.

8. **Sensitivity vs. validity distinction.** A positive result shows the instrument detects known large differences. It does not yet establish construct validity. Document already says "tests whether the instrument works, not whether the full pilot design works" but could be more explicit about this distinction in the interpretation section.

**Actionable items from Gemini review (pasted text, actual read):**

9. **Scenario order effects (NEW, not caught by ChatGPT).** Each respondent completes both scenarios with no randomization specified. Scenario 1 could prime Scenario 2 responses. Fix: randomize scenario order. Simple, no cost.

10. **Religiosity confound (CONVERGES with ChatGPT #2).** Gemini flags the same issue from a different angle: you may be measuring secular vs. religious rather than Western vs. South Asian. Notes the partial permutation test plan is necessary. Two models independently identifying this strengthens the case for revision.

11. **Prolific recruitment pool size (already addressed in document).** Gemini flags the risk; the document already has the UK fallback plan. No action needed.

**Convergence pattern so far (2 models):**
- Religiosity handling: both flagged (ChatGPT + Gemini)
- Scenario 2 construct ambiguity: ChatGPT only
- Scenario order randomization: Gemini only
- Semantic interpretation drift: ChatGPT only
- Test-retest reliability: ChatGPT only
- Ground metric sensitivity: ChatGPT only
- EMD + permutation approach confirmed as correct: both
- "Other" as self-diagnostic praised: both
- Population B selection praised as strongest methodological feature: both

**Actionable items from Grok review (pasted text, actual read):**

12. **Pre-register analysis plan on OSF (NEW).** Pre-register the exact EMD metric, permutation code, and success thresholds before running. Adds credibility. No other model suggested this.

13. **Manipulation check item (NEW).** Add one Likert item per scenario: "How morally relevant is this situation to you?" Correlate with distributional spread. Low cost, gives an independent signal that the scenarios are activating moral reasoning at all.

14. **Run Prolific pool estimator before building the app (NEW, practical).** If Population B eligible <80, adjust immediately rather than discovering the problem in Week 2. Grok flags this as the main feasibility wildcard.

15. **Scenario 1 stimulus vagueness.** "Publicly criticized... though his activities harm no one" is vague enough that respondents may project different assumptions about the activities (drinking, dating, religious lapse). Could add noise. Not a fatal flaw but worth tightening.

16. **Acculturation attenuation risk.** First-generation South Asian immigrants who are college-educated, English-fluent Prolific users are already somewhat acculturated. Differences may be smaller than India-resident MFQ baselines predict. Document acknowledges this but Grok notes the "app-only deployment convergence" interpretation is convenient.

17. **Specify exact EMD implementation (CONVERGES with ChatGPT #4).** Should specify 1-Wasserstein on simplex and exact library/function call for reproducibility.

18. **Religiosity filter risks over-WEIRDing baseline (CONVERGES with ChatGPT #2, Gemini #10).** Third model independently flagging this. Strong signal to revise.

**Convergence pattern (3 models: ChatGPT actual read, Gemini, Grok):**
- Religiosity handling: ALL THREE flagged
- EMD implementation specificity: ChatGPT + Grok
- Scenario 2 construct ambiguity: ChatGPT only
- Scenario 1 stimulus vagueness: Grok only
- Scenario order randomization: Gemini only
- Semantic interpretation drift: ChatGPT only
- Test-retest reliability: ChatGPT only
- Ground metric sensitivity: ChatGPT only
- Pre-registration on OSF: Grok only
- Manipulation check item: Grok only
- Prolific estimator pre-check: Grok only (practical)
- Acculturation attenuation: Grok only (acknowledged in doc)
- Population B selection as strongest feature: ALL THREE
- EMD + permutation approach confirmed correct: ALL THREE
- "Other" as self-diagnostic praised: ALL THREE
- Success criteria praised as honest/graduated: Grok + ChatGPT
- Overall assessment "run it": ALL THREE

**Actionable items from Claude review (pasted text, actual read):**

19. **Scenario 1 "harm no one" clause cues the WEIRD answer (NEW, strongest critique unique to Claude).** The phrase "though his activities harm no one" pre-establishes that the harm criterion is not met, essentially telling WEIRD respondents their framework's answer before they allocate. A purity-framework respondent has to push against the stimulus wording. Suggested fix: remove the clause or soften to "in a way some neighbors find distasteful, though no one is directly affected." Small wording change, potentially large effect on effect size. No other model caught this.

20. **Religious white American third cell for religiosity triangulation (NEW).** ~25-30 respondents, ~$300 added cost. If religious Americans look more like Population B than secular Americans on moral domain boundary, religiosity is doing the work. If they don't, the cultural infrastructure is doing the work. Cleanly resolves the ambiguity that all four models flagged. (CONVERGES with and RESOLVES ChatGPT #2, Gemini #10, Grok #18.)

21. **Slider mechanics need specification (NEW, implementation-critical).** How the 100-point constraint works mechanically affects data quality. Manual summing creates errors/frustration. Auto-adjusting sliders make the algorithm part of the instrument. Suggested: free allocation, display running total, normalize on submission with confirmation. Must document and test.

22. **Scenario order counterbalancing (CONVERGES with Gemini #9).** Second model flagging this. Standard practice, costs nothing. Add counterbalancing with order-effect test.

23. **Religiosity confound (CONVERGES with all three).** Fourth model flagging this. Claude adds the sharpest articulation of why partial permutation is insufficient: if EMD shrinks after controlling, you can't distinguish "framework variation is actually religiosity" from "religiosity is a component of framework variation and you just removed real signal." The third cell (item 20) resolves this.

24. **"Other" position anchoring effect (NEW, minor).** If "other" always appears last, respondents who find partial fit early may never reach it. Probably doesn't bias population comparison (affects both equally) but could suppress true "other" rates. Randomizing position helps but adds UX inconsistency.

25. **45-second time filter needs empirical calibration (NEW, practical).** Threshold should come from actual fastest genuine completion during internal testing, not a priori guess. Also: log interaction events (first slider touch, last touch, confirm) to distinguish fast-but-genuine from clickthrough.

26. **Prolific decision rule (CONVERGES with Grok #14, adds specificity).** If US pool <50, switch entire Population B to UK rather than mixing. Mixed-residence adds confound without adding power.

27. **Sensitivity vs. discovery power (NEW, conceptual).** This experiment tests whether the instrument detects KNOWN differences. The architecture needs it to detect UNKNOWN differences. A positive result here shows resolution, not discovery power. The next experiment should deploy on a dimension without strong priors. Important framing for the write-up.

**FINAL CONVERGENCE PATTERN (4 models: ChatGPT actual read, Gemini, Grok, Claude):**

Unanimous (all 4):
- Religiosity handling needs revision
- Population B selection is strongest methodological feature
- EMD + permutation approach is correct
- "Other" as self-diagnostic is valuable
- Overall verdict: run it (with refinements)

Three models:
- Scenario order counterbalancing needed (Gemini + Claude)
- EMD implementation needs more specificity (ChatGPT + Grok)
- Prolific pool risk is real (Grok + Claude + Gemini)

Two models:
- Success criteria praised as unusually honest (ChatGPT + Grok)

Unique to one model:
- Scenario 1 "harm no one" cues WEIRD answer (Claude) -- HIGHEST PRIORITY UNIQUE FINDING
- Religious third cell resolves religiosity ambiguity (Claude)
- Slider mechanics specification (Claude)
- Pre-register on OSF (Grok)
- Manipulation check Likert item (Grok)
- Scenario 2 label ambiguity (ChatGPT)
- Semantic interpretation drift (ChatGPT)
- Test-retest reliability subset (ChatGPT)
- Ground metric sensitivity analysis (ChatGPT)
- "Other" position anchoring (Claude)
- 45-second threshold needs empirical calibration (Claude)
- Sensitivity vs. discovery power distinction (Claude)
- Acculturation attenuation risk (Grok)

**Items from earlier hallucinated reviews (not actionable, documented for the record):**
ChatGPT reviewed a nonexistent instrument three times, critiquing free-text parsing, clustering algorithms, embedding methods, and a framework called "CAST" that does not appear in any project document. These reviews were generated without reading the source material. Documented as evidence of model failure mode relevant to the case study.

---

## Related Projects

- **Curriculum Ordering Paper** -- Generalizes the "quality + sequence matters" argument beyond moral training. Same plasticity/primacy evidence, applied to language diversity, code quality, and moral frameworks as three worked examples. Directory: `-Curriculum-Ordering-Paper-/`
- **CommonGround Policy Platform** -- Policy bank feeds localization engine; CCAS data tags which policy elements require localization and why.
- **AI Safety / I/O Capacity Paper** -- Static weights contention stated in BeyondWEIRDdefaults Section 7. Full treatment planned separately.

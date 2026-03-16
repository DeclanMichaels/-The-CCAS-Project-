# Annotated Bibliography

## Beyond WEIRD Defaults: Diverse Moral Experience as AI Alignment Signal

*This addendum provides context for each reference: what the source argues, what this paper draws from it, and where it appears in the text. References are numbered by order of first appearance in the paper.*

---

**[1] Henrich, J. (2020). *The WEIRDest People in the World: How the West Became Psychologically Peculiar and Particularly Prosperous.* Farrar, Straus and Giroux.**

Henrich expands his foundational 2010 article (which coined the WEIRD acronym and demonstrated that Western behavioral science samples are global outliers) into a causal account of how WEIRD psychology developed. His central argument is that the Catholic Church's "Marriage and Family Program," which prohibited cousin marriage, dismantled polygyny, and broke up extended kin networks, inadvertently produced a historically contingent psychology: individualist, analytically oriented, high in impersonal trust, and disposed toward rule-based rather than relationship-based moral reasoning. This psychology is not a universal human baseline but the product of specific institutional changes that dismantled kin-based social structures over centuries. Henrich documents how this reshaping produced populations that index heavily toward impersonal prosociality (treating strangers almost as fairly as kin), abstract moral reasoning, and institutional trust, traits that now dominate the AI alignment signal.

*Used in:* Section 1 (The Problem) as the foundational citation for the claim that the current alignment signal is not merely demographically narrow but historically contingent. The paper draws on Henrich's causal argument to establish that WEIRD moral psychology reflects a specific institutional history rather than a universal human baseline, making the case that encoding it as default in AI systems is not just parochial but structurally misleading.

---

**[2] Haidt, J. (2012). *The Righteous Mind: Why Good People Are Divided by Politics and Religion.* Vintage Books.**

Haidt synthesizes two decades of cross-cultural moral psychology research into Moral Foundations Theory, identifying six foundations that underlie moral judgment across cultures: care/harm, fairness/cheating, loyalty/betrayal, authority/subversion, sanctity/degradation, and liberty/oppression. His central finding is that WEIRD populations, and political liberals within those populations especially, systematically over-weight care and fairness while treating the other foundations as less morally relevant or even morally suspect. Non-WEIRD populations and political conservatives tend to draw on all six foundations more evenly. Haidt argues this is not a deficit but a genuine difference in moral architecture.

*Used in:* Section 1 (The Problem) to specify what "WEIRD-skewed moral intuitions" actually means: not just a vague cultural bias but a documented, measurable asymmetry in which moral foundations are weighted. Section 3 (What Moral Framework Diversity Actually Means) as the empirical base from which the paper's four structural dimensions are derived. The six foundations describe what triggers moral intuition (content-level signal); the paper argues that when aggregated across populations, these triggers produce framework-level convergence and divergence patterns along four structural dimensions (moral agent constitution, authority legitimacy, moral domain boundary, and scope of moral obligation) that the rationalization layer detects. MFT's sanctity/degradation foundation is particularly important: it grounds the "moral domain boundary" dimension, where WEIRD and non-WEIRD frameworks diverge not on answers but on whether a domain is morally relevant at all. The paper also uses Haidt's work to argue that fairness is a derived moral judgment rather than a structural feature. Also referenced in Sections 4 and 5.

---

**[3] Durmus, E., et al. (2024). Towards measuring the representation of subjective global opinions in language models. In *Proceedings of the Conference on Language Modeling (COLM 2024)*.**

This Anthropic paper (18 authors) develops a quantitative framework for measuring whose opinions LLM-generated responses most closely resemble. Using the GlobalOpinionQA dataset, drawn from cross-national surveys on global issues, they define a metric comparing LLM responses to human survey responses conditioned on country. Their central finding is that Claude's responses are systematically more similar to opinions from the United States and certain European and South American countries, and less similar to opinions from other regions. Critically, this bias persists even when controlling for language, suggesting it is embedded in the alignment process rather than merely in training data coverage.

*Used in:* Section 1 (The Problem) to move the WEIRD-bias argument from theoretical (Henrich [1] established it in behavioral science generally) to empirical and specific (Durmus confirmed it in LLMs specifically, and measured it). The fact that this paper comes from Anthropic, the developer of Claude, strengthens the claim that the problem is recognized within the industry but not yet addressed at the level of the upstream signal.

---

**[4] Casper, S., et al. (2023). Open problems and fundamental limitations of reinforcement learning from human feedback. *Transactions on Machine Learning Research*. arXiv:2307.15217.**

This comprehensive survey (32 authors) systematizes the flaws of RLHF across three categories: challenges with human feedback (inconsistency, bias, limited coverage), challenges with the reward model (misgeneralization, reward hacking), and challenges with the policy (distributional shift, sycophancy). The paper reviews over 250 papers and distinguishes between tractable problems (fixable with engineering effort within the current paradigm) and fundamental limitations (structural to the RLHF approach regardless of implementation quality). The authors argue that RLHF was intended as a stepping stone toward more robust alignment techniques but has instead been deployed as a production solution, and that its limitations are systematically underappreciated.

*Used in:* Section 1 (The Problem) to establish that the limitations of compliance-based alignment are extensively documented. The paper's argument is not that compliance should be replaced but that its upstream signal should be improved. Casper et al. document the structural problems with RLHF; this paper proposes an intervention targeting the quality and honesty of the input to the pipeline, adding empirically grounded humility in domains where moral frameworks diverge across cultures.

---

**[5] Awad, E., et al. (2018). The Moral Machine experiment. *Nature*, 563(7729), 59-64.**

The largest cross-cultural moral data collection to date: 40 million decisions from 2.3 million participants across 233 countries and territories. Using an online platform presenting autonomous vehicle dilemmas, the study identified global moral preferences (spare humans over animals, spare more lives, spare the young) while documenting substantial cross-cultural variation. Hierarchical clustering revealed three major cultural clusters (Western, Eastern, and Southern) with systematically different preference profiles correlated with cultural dimensions (Hofstede's individualism), economic development, and institutional quality. The paper demonstrates that cross-cultural moral variation is real, measurable, geographically patterned, and correlated with deep cultural and institutional traits.

*Used in:* Section 2 (Divergence as Signal) as empirical evidence that cross-cultural moral divergence is measurable and structured, not random noise. Section 3 (What Moral Framework Diversity Actually Means) to ground the scope of moral obligation dimension, where the data confirmed systematic cross-cultural variation in whose welfare weighs in moral calculations. Section 8 (Relationship to Existing Work) to acknowledge the Moral Machine as important precedent while drawing a critical distinction: it captures forced-choice preferences in hypothetical dilemma scenarios, conclusions stripped of reasoning. The SenseMaker approach preserves narrative context and continuous moral weighting, producing the richer signal the rationalization layer requires.

---

**[6] Rawls, J. (1993). *Political Liberalism.* Columbia University Press.**

Rawls addresses a central problem in liberal political theory: how a stable, just society is possible among citizens who hold deeply different and irreconcilable comprehensive doctrines (religious, philosophical, moral). His answer is the overlapping consensus: citizens reasoning from different comprehensive doctrines converge on the same political principles, each for their own reasons. The overlapping consensus is not a compromise or a modus vivendi (which would collapse if power shifted) but a genuine convergence on principles, arrived at from within each doctrine's own reasoning. The stability comes precisely from the fact that different paths lead to the same destination. Rawls distinguishes this from mere agreement: in an overlapping consensus, each party endorses the shared principles as following from their own deepest commitments, not as a concession to others.

*Used in:* Section 2 (Divergence as Signal) to establish philosophical precedent for the contingent agreement category. Rawls's overlapping consensus describes the same structural pattern: convergence on conclusions through divergent reasoning paths. The paper's contribution is the operationalization: translating the philosophical observation into differential reward confidence for RLHF.

---

**[7] Sunstein, C. R. (1996). *Legal Reasoning and Political Conflict.* Oxford University Press.**

Sunstein develops the concept of incompletely theorized agreements: situations where people agree on an outcome or a mid-level principle while disagreeing on the deeper reasons. His central argument is that this incompleteness is a feature, not a deficiency. In legal and political contexts, insisting on agreement at the level of deep theory produces paralysis or false consensus, while agreement on outcomes allows diverse societies to function and adapt. Sunstein shows that judges routinely reach agreement on case outcomes while offering fundamentally different rationales, and that this practice produces more stable and adaptable law than would insistence on theoretical unity. The concept applies beyond law: any domain where people must cooperate across deep disagreement benefits from recognizing that outcome-level agreement with reasoning-level divergence is a distinct and valuable category.

*Used in:* Section 2 (Divergence as Signal) alongside Rawls [6] to establish philosophical precedent for the contingent agreement category. Sunstein sharpens the point that Rawls introduces: agreement on outcomes is often more stable and productive precisely because the parties have not been forced into agreement on underlying reasons. This maps directly to the paper's claim that contingent agreements are real but fragile, breaking when perturbation shifts the question to adjacent territory where the divergent reasoning paths produce divergent conclusions. The rationalization layer's three-category classification operationalizes what Rawls and Sunstein observed philosophically.

---

**[8] Darwall, S. (2006). *The Second-Person Standpoint: Morality, Respect, and Accountability.* Harvard University Press.**

Darwall's central argument is that moral obligation is fundamentally second-personal. It arises from the standing of one agent to make claims on another, rather than from abstract principles applied impersonally. Moral authority is not a property of rules but of relationships between agents who recognize each other as having the standing to demand, refuse, and hold accountable. This framework implies that moral systems differ not just in what they prescribe but in who they recognize as having the standing to make moral claims at all.

*Used in:* Section 3 (What Moral Framework Diversity Actually Means) to ground the "scope of moral obligation" dimension. Different moral traditions draw the boundary of second-person standing differently, and these differences are among the most consequential for AI alignment. Darwall is also cited as one of the two theoretical foundations (alongside Haidt [2]) from which the paper's four structural dimensions are derived.

---

**[9] Shweder, R. A., Much, N. C., Mahapatra, M., & Park, L. (1997). The "big three" of morality (autonomy, community, divinity) and the "big three" explanations of suffering. In A. Brandt & P. Rozin (Eds.), *Morality and Health* (pp. 119-169). Routledge.**

Shweder's foundational cross-cultural moral psychology framework, developed from fieldwork in Orissa, India. He argues that moral discourse across cultures organizes around three irreducible ethics: autonomy (rights, justice, harm, individual freedom), community (duty, hierarchy, interdependence, role-based obligation), and divinity (purity, sanctity, pollution, the sacred order). Unlike Haidt's six foundations, the CAD triad operates at a higher level of abstraction, describing three distinct moral logics rather than discrete triggers. Shweder's work predates and heavily influenced MFT; Haidt's care and fairness foundations map to autonomy, loyalty and authority to community, and sanctity to divinity. The framework has been validated cross-culturally and remains the primary alternative to MFT in cultural moral psychology.

*Used in:* Section 3 (What Moral Framework Diversity Actually Means) as one of three alternative frameworks cited to establish that MFT's contested status does not undermine the four structural dimensions. Addendum A demonstrates the full mapping: moral agent constitution corresponds to the autonomy-community axis, authority legitimacy falls within the community ethic, moral domain boundary maps to divinity, and scope of moral obligation cuts across all three ethics.

---

**[10] Gray, K., & Schein, C. (2012). Two minds vs. two philosophies: Mind perception defines morality and dissolves the debate between deontology and utilitarianism. *Review of Philosophy and Psychology*, 3(3), 405-423.**

Gray and Schein propose the Theory of Dyadic Morality (TDM), arguing that all moral judgment reduces to a perceived dyad: an intentional agent causing harm (or benefit) to a vulnerable patient. Rather than multiple independent foundations (MFT) or three ethics (Shweder), TDM posits a single cognitive template that generates apparent moral diversity through variation in who is perceived as agent or patient, what counts as harm, and how readily the dyadic template is completed (dyadic completion: the tendency to perceive a victim even where none is obviously present). TDM is the most reductionist alternative to MFT and represents a direct challenge to the claim that morality has plural foundations. Gray and Schein's later work (2018) expanded TDM into a full alternative to MFT.

*Used in:* Section 3 (What Moral Framework Diversity Actually Means) as a cited alternative framework. Addendum A demonstrates that even this maximally reductionist framework reproduces the four structural dimensions through variation in agent perception (moral agent constitution), authority-as-agent-or-protector (authority legitimacy), dyadic completion (moral domain boundary), and patient perception (scope of moral obligation). TDM's concept of dyadic completion is particularly useful for explaining the moral domain boundary dimension: cultures differ in whether they complete the harm dyad for purity violations.

---

**[11] Curry, O. S., Mullins, D. A., & Whitehouse, H. (2019). Is it good to cooperate? Testing the theory of morality-as-cooperation in 60 societies. *Current Anthropology*, 60(1), 47-69.**

Curry, Mullins, and Whitehouse derive seven moral domains from seven distinct types of cooperation problem: family values (kin altruism), group loyalty (mutualism), reciprocity (exchange), bravery (conflict resolution), respect (deference hierarchies), fairness (division), and property rights (possession). They test this framework against ethnographic data from 60 societies and find that all seven types of cooperative behavior are considered morally good in the majority of societies studied, with no society rating any of them as morally bad. MAC is the most granular alternative to MFT and is distinctive in deriving moral content from evolutionary cooperation theory rather than from psychological foundations or cultural logics.

*Used in:* Section 3 (What Moral Framework Diversity Actually Means) as a cited alternative framework. Addendum A demonstrates that MAC's seven domains cluster under the four structural dimensions: family values and group loyalty versus property rights and fairness map to moral agent constitution, respect maps to authority legitimacy, variation in which cooperation problems are moralized maps to moral domain boundary, and the reach of reciprocity and group loyalty maps to scope of moral obligation.

---

**[12] Dryzek, J. S., et al. (2019). The crisis of democracy and the science of deliberation. *Science*, 363(6432), 1144-1146.**

Twenty leading scholars of democratic theory argue that the proliferation of citizen expression, rather than solving democracy's problems, has created a signal-to-noise crisis. The sheer volume of opinion overloads both policymakers and citizens, accompanied by declining civility and argumentative complexity. The authors make the case that deliberative processes, in which citizens engage with evidence and opposing views under structured conditions, produce qualitatively different and better output than preference aggregation or unstructured expression. Deliberation changes participants' views, increases mutual understanding, and generates outputs that preference polling cannot.

*Used in:* Section 4 (The Instrument) to frame the problem SenseMaker addresses: traditional surveys capture conclusions, deliberation captures reasoning but does not scale, and unstructured expression creates noise. Section 8 (Relationship to Existing Work) to sharpen the distinction from Collective Constitutional AI. Dryzek et al.'s argument that deliberation produces qualitatively different output from preference aggregation establishes the principle; the paper then honestly positions SenseMaker as occupying middle ground (more than aggregation, less than full deliberation) by specifying three ways it goes beyond preference data without achieving the exchange of reasons between participants that deliberation requires.

---

**[13] Van der Merwe, S. E., et al. (2019). Making sense of complexity: Using SenseMaker as a research tool. *Systems*, 7(2), 25.**

This is the primary academic description of SenseMaker as a research methodology. The paper walks through the four-step process: instrument design (prompts and signifiers), distributed data collection via micro-narratives, sensemaking through pattern analysis of triad/dyad distributions, and adaptive response. Key contributions include the explanation of how triads capture continuous moral weighting rather than discrete choices, how self-signification removes researcher interpretation bias, and how the combination of quantitative triad data with qualitative narrative data produces mixed-methods output that neither alone could generate. The paper also documents limitations including challenges with low-literacy populations and the need for careful prompt design.

*Used in:* Section 4 (The Instrument) as the primary citation for how SenseMaker works. The dual-signal design (narrative plus triad placement), self-signification, and the capacity to detect convergence/divergence patterns across populations are all drawn from this source. Section 10.4 (Structural Risks) cites this as the academic documentation establishing that the methodology is independently replicable beyond Cognitive Edge's proprietary platform.

---

**[14] Snowden, D. J., & Boone, M. E. (2007). A leader's framework for decision making. *Harvard Business Review*, 85(11), 68-76.**

This article introduced the Cynefin framework to a broad audience, distinguishing five domains of decision-making context: simple (clear cause and effect), complicated (cause and effect discoverable through expertise), complex (cause and effect only coherent in retrospect), chaotic (no discernible cause and effect), and disorder (not knowing which domain applies). The framework's core principle is that appropriate action depends on correctly identifying which domain a problem occupies. Methods that work in complicated domains fail or cause harm in complex ones. Snowden later developed SenseMaker as a tool for navigating complexity by capturing distributed human sensemaking rather than attempting expert analysis.

*Used in:* Section 4 (The Instrument) to establish SenseMaker's theoretical foundation. The alignment signal problem is a complex-domain problem. Moral frameworks interact in ways that cannot be predicted from components, and the appropriate response is distributed sensemaking rather than expert adjudication. Citing Cynefin grounds SenseMaker in a coherent theoretical framework rather than presenting it as a standalone data collection tool.

---

**[15] Yan, Y., Lou, X., Li, J., Zhang, Y., Xie, J., Yu, C., Wang, Y., Yan, D., & Shen, Y. (2024). Reward-robust RLHF in LLMs. *arXiv:2409.15360*.**

Yan et al. introduce a reward-robust RLHF framework that addresses the inherent instability and imperfections of reward models. Their central contribution is Bayesian Reward Model Ensembles (BRME), which model the uncertainty set of reward functions rather than relying on a single reward signal. The framework balances nominal performance with robustness by incorporating both mean and minimum reward signals from the ensemble. Empirical results show consistent improvement across benchmarks with improved long-term stability. The paper demonstrates formally that reward models are inherently imperfect even with unbiased annotators, and that noisy reward signals produce degraded training outcomes including reward hacking and sycophancy.

*Used in:* Section 4 (What variance can and cannot teach) alongside Casper [4] to ground the claim that noisy reward signals produce specific, documented failure modes. Yan et al.'s BRME work is particularly relevant because their approach to modeling reward uncertainty through ensembles addresses the same structural problem our variance-weighted mechanism addresses: the reward signal carries uncertainty that must be managed rather than ignored. Their empirical demonstration that reward noise produces reward hacking, sycophancy, and conservative hedging directly supports our argument that variance modification alone (without dimensional supervised training) would produce these same content-poor behaviors rather than the content-rich Tier 3-4 behaviors the paper targets.

---

**[16] Bartels, S. A., et al. (2018). Making sense of child, early and forced marriage among Syrian refugee girls: A mixed methods study in Lebanon. *BMJ Global Health*, 3(1), e000509.**

This study deployed SenseMaker among Syrian refugees in Lebanon to understand factors contributing to child marriage, collecting 1,422 self-interpreted narratives from 1,346 participants across Beirut, Beqaa, and Tripoli over seven weeks. Twelve trained interviewers administered the tool on iPads. Participants shared stories about the lives of Syrian girls and self-interpreted their narratives using triads and dyads. The study demonstrated SenseMaker's capacity for efficient, large-scale mixed-methods data collection in a humanitarian setting with a displaced, multilingual population. Findings revealed the intersection of economic hardship, social pressure, and protection concerns in driving early marriage, patterns that emerged from the narratives rather than being assumed by the researchers.

*Used in:* Section 6 (Community Facilitator Model) as evidence that SenseMaker works in the field conditions this proposal requires: digitally disconnected, low-literacy, conflict-affected, multilingual populations. The study's use of trained local interviewers is directly relevant to the community facilitator model proposed here.

---

**[17] Bartels, S. A., et al. (2019). SenseMaker as a monitoring and evaluation tool to provide new insights on gender-based violence programs and services in Lebanon. *Evaluation and Program Planning*, 77, 101715.**

This follow-on study deployed SenseMaker for monitoring and evaluation of GBV programs across five locations in Lebanon, collecting 198 self-interpreted stories from women and girls accessing services from six providers (ABAAD, IRC, IMC, Caritas, UNRWA, and others). The study demonstrated that SenseMaker's mixed-methods output provided nuanced insights that conventional M&E tools missed, including how perceived benefits differed by program type, how motivations for access differed by location, and how experiences differed by participant nationality. The study also documented challenges: low literacy and limited technology skills among participants required additional facilitator support, and the tool was more time-intensive than anticipated in this population.

*Used in:* Section 6 (Community Facilitator Model) alongside [16] as evidence of successful field deployment. This study's documentation of literacy and technology challenges supports the argument for human facilitators rather than digital-only deployment. The named NGO partners (ABAAD, IRC, UNFPA, UNRWA) represent the institutional infrastructure this proposal would build upon: facilitators recruited from organizations already operating within target communities.

---

**[18] Bai, Y., et al. (2022). Constitutional AI: Harmlessness from AI feedback. *arXiv:2212.08073*.**

This paper (51 authors, Anthropic) introduces Constitutional AI, a method for training AI assistants to be harmless without direct human labels for harmful outputs. Instead, a set of written principles (the "constitution") guides the model through self-critique and revision. The supervised learning phase generates and refines responses against these principles; the reinforcement learning phase uses AI-generated preference labels rather than human labels. The key contribution is replacing human feedback on harmlessness with AI feedback guided by explicit principles, making the values embedded in the system more transparent and auditable.

*Used in:* Section 8 (Relationship to Existing Work) as the baseline that this paper proposes to supplement. Constitutional AI is characterized as structured compliance: more principled and transparent than ad hoc refusal training, but still operating on a narrow moral signal. This paper supplements rather than replaces Constitutional AI by improving the upstream signal.

---

**[19] Huang, S., Siddarth, D., Lovitt, L., Liao, T. I., Durmus, E., Tamkin, A., & Ganguli, D. (2024). Collective Constitutional AI: Aligning a language model with public input. In *Proceedings of the 2024 ACM Conference on Fairness, Accountability, and Transparency (FAccT '24)*. arXiv:2406.07814.**

This paper extends Constitutional AI by sourcing constitutional principles from a representative sample of roughly 1,000 U.S. adults via the Polis deliberation platform, rather than having Anthropic employees write them. The publicly-sourced constitution produced a model with lower bias across nine social dimensions compared to the Anthropic-written baseline while maintaining equivalent performance. The paper demonstrates that public input can meaningfully shape model behavior through the constitutional framework.

*Used in:* Section 8 (Relationship to Existing Work) as the closest existing work in spirit. The distinction this paper draws is that aggregated preference data from a U.S. sample, while more democratic than developer-written principles, is still a single-population preference aggregation. It does not capture moral reasoning grounded in lived experience, does not preserve divergence as information, and does not reach the populations whose moral frameworks differ most from the WEIRD default. The CCAI approach improves *who* provides input but not *what kind* of input the mechanism captures.

---

**[20] Sorensen, T., Moore, J., Fisher, J., Gordon, M. L., Mireshghallah, N., Rytting, C. M., Ye, A., Jiang, L., Lu, X., Dziri, N., Althoff, T., & Choi, Y. (2024). Position: A roadmap to pluralistic alignment. In *Proceedings of the 41st International Conference on Machine Learning (ICML)*, PMLR 235:46280-46302.**

The most comprehensive taxonomy of pluralistic alignment to date. Sorensen et al. distinguish three types of pluralistic models: Overton pluralistic (presenting a spectrum of reasonable responses), steerably pluralistic (reflecting specific perspectives on demand), and distributionally pluralistic (calibrated to reflect the actual distribution of views in a given population). They pair these with three benchmark types: multi-objective, trade-off steerable, and jury-pluralistic. Their critical empirical finding is that standard alignment procedures (RLHF, Constitutional AI) may actively reduce distributional pluralism in models, narrowing the model's moral range rather than preserving it. The paper provides a roadmap for the field but does not address the upstream question of how to collect diverse moral signal, particularly from populations absent from digital platforms.

*Used in:* Section 8 (Relationship to Existing Work) as the primary point of contact with the current pluralistic alignment literature. This paper's proposal maps most closely to Sorensen et al.'s distributionally pluralistic category but differs in a critical respect: Sorensen et al. frame the goal as calibrating model outputs to match population view distributions, while this paper frames it as using the structure of convergence and divergence to calibrate model confidence. Their finding that standard alignment reduces pluralism directly supports this paper's argument that the current pipeline discards the most valuable signal. Two gaps in their framework that this paper addresses: they do not propose a mechanism for collecting diverse moral signal from digitally disconnected populations (SenseMaker + community facilitators), and their taxonomy does not distinguish convergence-in-conclusion from convergence-in-reasoning (the contingent agreement category that the rationalization layer's dual-signal design detects).

---

**[21] Tennant, E., Hailes, S., & Musolesi, M. (2024). Hybrid approaches for moral value alignment in AI agents: a manifesto. *arXiv:2312.01818*.**

Tennant, Hailes, and Musolesi (UCL/University of Bologna) systematize existing approaches to embedding morality in AI systems along a continuum from fully top-down (hard-coded rules, constraints, constitutions) to fully bottom-up (learned entirely from human feedback with no explicit moral principles). Their central argument is that popular techniques cluster at the extremes of this continuum: Constitutional AI and rule-based constraints at the top-down end, RLHF and inverse RL at the bottom-up end. They document the relative strengths and weaknesses of each extreme (top-down is controllable and interpretable but rigid and unable to handle novel situations; bottom-up is adaptive and generalizable but opaque and vulnerable to reward hacking and data poisoning) and argue that hybrid approaches combining explicit moral structure with learned behavior are the most promising path forward. In subsequent work (Tennant et al., 2025, ICLR Main Track), the same team implements one specific hybrid: intrinsic reward functions derived from moral philosophy frameworks (utilitarianism, deontology, virtue ethics, social contract theory) used to fine-tune LLM agents in a Prisoner's Dilemma setting, demonstrating that explicit moral rewards can align agent behavior more transparently and cost-effectively than RLHF.

*Used in:* Section 8 (Relationship to Existing Work) to position our proposal on the hybrid continuum Tennant et al. define. Our architecture is a different hybrid from theirs: they derive moral structure from philosophical theory (top-down source, implemented as intrinsic reward functions), while we derive it from empirical cross-cultural data processed through a rationalization layer (bottom-up source, structured by dimensional analysis, implemented as variance-modified reward confidence). Both add explicit moral architecture to the training pipeline; the distinction is the source. The approaches are complementary: Tennant et al.'s intrinsic rewards could be informed by the three-category output of our rationalization layer, grounding philosophical frameworks in empirical cross-cultural data about where those frameworks converge and diverge.

---

**[22] Conitzer, V., Freedman, R., Heitzig, J., Holliday, W. H., Jacobs, B. M., Lambert, N., Mosse, M., Pacuit, E., Russell, S., Schoelkopf, H., Tewolde, E., & Zwicker, W. S. (2024). Position: Social choice should guide AI alignment in dealing with diverse human feedback. In *Proceedings of the 41st International Conference on Machine Learning (ICML)*, PMLR 235.**

This position paper (12 authors including Stuart Russell) argues that social choice theory, the formal study of aggregating individual preferences into collective decisions, should be applied to AI alignment when human feedback is diverse and conflicting. The authors contend that RLHF and related methods implicitly make aggregation choices (whose preferences count, how conflicts are resolved) without drawing on the extensive theoretical toolkit social choice provides for handling exactly these problems. They survey relevant social choice concepts (Arrow's impossibility theorem, strategyproofness, proportional representation) and argue these should inform how alignment systems reconcile competing human values. The paper is a call for interdisciplinary collaboration between social choice theorists and alignment researchers.

*Used in:* Section 8 (Relationship to Existing Work) to engage with the formal aggregation approach to value pluralism. The distinction this paper draws is that social choice approaches assume the preferences are already collected and focus on fair aggregation rules, while our proposal focuses on what gets collected and how. The quality of the upstream signal determines what any aggregation mechanism has to work with. Conitzer et al. address the aggregation problem; we address the collection problem. The two approaches are complementary rather than competing.

---

**[23] Gabriel, I., & Keeling, G. (2025). A matter of principle? AI alignment as the fair treatment of claims. *Philosophical Studies*, 182(7), 1951-1973.**

Gabriel and Keeling (Google DeepMind) advance Gabriel's earlier work on the alignment problem by arguing that alignment requires fair *processes* that generate principles sensitive to variation in context, rather than the identification of fixed universal principles. They frame AI alignment as analogous to a problem in political philosophy: how to produce principles that fairly adjudicate competing moral claims when those claims arise from genuinely different value systems. The paper moves beyond Gabriel's 2020 framework (which emphasized reflective endorsement of fair principles) toward a procedural account where the fairness of the process, not just the content of the principles, determines alignment quality.

*Used in:* Section 8 (Relationship to Existing Work) to engage with the strongest philosophical framework for alignment. This paper agrees with Gabriel and Keeling's framing (fair processes sensitive to context) but contends that such processes require empirical grounding in diverse lived experience, which is what the SenseMaker instrument and rationalization layer provide. Their emphasis on context-sensitivity aligns with our argument that alignment must account for the structural dimensions along which moral frameworks diverge.

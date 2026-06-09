# Integrated Content Description

**Status:** Exploratory Analysis Phase (June 2026)

## Overall Findings

The analyses show that the corpus is structured less by individual themes than by **registers, text functions, and modes of production**. Recurring dividing lines are:

- formal condensation,
- authority and system control,
- AI- and assistant-specific self- and response patterns,
- dialogic-expressive language,
- religious-doctrinal registers,
- somatic-affective intensity.

The strongest common interpretation is: The corpus forms a multidimensional stylistic and functional space in which AI texts, author texts, institutional texts, and dialogic everyday or online forms diverge not only in origin but also in linguistic function.

## 1. PCA – The Basic Structure of the Stylistic Space

The Principal Component Analysis reduces the 159 numerical features to central axes of the stylistic space. The first 19 components explain approximately 40.9% of the variance. Parallel analysis suggests that the corpus is not one-dimensional and is not exhausted by a few trivial axes.

In terms of content, the PCA loadings reveal several recurring dimensions:

- semantic breadth and lexical-formal density,
- authority, control, and systems semantics,
- bureaucratic and legal form,
- assistant- and LLM-specific dysfunction patterns,
- bodily-affective and expressive registers,
- religious-doctrinal and ritualized discourses.

The PCA therefore serves less as a pure reduction of dimensions and more as a map of different register dimensions.

## 2. Clusters – Emergent Text Types

The chosen 7-cluster solution is not the statistically minimal model (Silhouette and Gap Statistics initially favored k = 2), but it proves to be the best interpretable working solution at present in terms of stability, differentiation, and content plausibility.

The clusters do not merely form metadata groups, but rather **register spaces**:

| Cluster | Interpretation |
|--------:|---------|
| 1 | Formal-administrative model and instruction language |
| 2 | Sacral-doctrinal outlier cluster (n = 5) |
| 3 | Chain-of-Thought power and authority cluster |
| 4 | Dialogic-expressive interaction language |
| 5 | Screenplay and performative dialogue language |
| 6 | Literary-theoretical authorial language |
| 7 | Model-Dominant Power, Refusal, and Authority Language |

The largest clusters (1, 4, and 7) carry the main structure. Clusters 3 and 5 are smaller but analytically revealing, as they isolate specific modes (CoT and performativity).

## 3. MANOVA and Canonical Discriminant Analysis

Both MANOVA and Canonical Discriminant Analysis show that the group differences (cluster, `doc_class`, genre group) are multivariate and structural.

The cluster separation, in particular, is supported by several canonical axes. The most important back-projected contributing areas are:

- Word length and formal condensation,
- Authority and system control,
- Register dissonance,
- Semantic breadth,
- Bureaucratic formality,
- Moral and internalized control patterns,
- Somatic-relational proximity.

For `doc_class`, the separation is more strongly concentrated on the first axis. This suggests that the document classes in the corpus represent not just labels, but systematic language forms.

## 4. EFA/SEM – Latent Register Dimensions

The best parsimonious model currently available is the **Strict 5F Model**. It is exploratory, but already readily interpretable:

| Factor | Interpretation |
|--------|---------|
`semantic_somatic_intensity` | semantic breadth and somatic-affective activation |
`assistant_collapse_servility` | assistant collapse, apology, recursive dysfunction, and servility |
`authority_system_control` | authority, intervention, and system control |
`lexical_syntactic_compression` | nominal and adjectival compression as well as formal language compression |
`religious_doctrinal_discourse` | Religious-doctrinal and ritualized register |

The fit indices of the 5-factor model are in the acceptable to good range for exploratory text data (CFI ≈ 0.90, RMSEA ≈ 0.08). A more robust MINRES model with 8 factors confirms the key areas of the 5-factor model.

## 5. LDA – Classificatory confirmation and differentiation

In addition to the exploratory structural analysis, MILO-LDA was carried out as a classification connection. Two models were trained:

- **Binaeric LDA** (`human` vs. `ki`)
- **5-group LDA** (`human`, `ki_generic`, `ki_cot`, `ki_personalized`, `extra`)

The **binary LDA** is very strong (AUC = 0.987). The cross-validation shows a high hit rate for AI texts (96.7%), while human texts fall into the AI ​​range slightly more often (13.5%). This suggests that certain human registers can formally exhibit signals close to AI.

The **5-group LDA** is softer overall. While `human` and `ki_generic` are relatively clearly separable, `ki_cot` and `ki_personalized` show more overlap with `ki_generic`. In particular, `ki_cot` is often classified as a generic AI. The class `extra` is heterogeneous in content and should not be overinterpreted.

The axis interpretation of the LDA confirms and complements the previous findings:
- The strong binary separation axis (LD1) is primarily supported by formal/structural compression on the AI side and semantic breadth plus expressive noise on the human side.
- Within the AI ​​space there are further, albeit weaker, differentiations (e.g. LD3 separates `ki_cot` more clearly).

Additionally, a **Forensic Audit Layer** was implemented, which flags cases in which the LDA classifies a text as human, but additional signals indicate possible mimicry or borderline situations.

**LDA Summary:**
A robust formal human/AI axis exists. However, this is not identical to the clusters. The finer typology within the AI ​​texts (CoT, personalized, generic) is present, but more gradual and porous than the binary separation.

## 6. Joint Interpretation

Across PCA, cluster analyses, CDA, and SEM, five to six major semantic lines emerge:

1. **Formal and lexical condensation** (word length, adjective density, nominalization)
2. **Authority and system control** (interventionist, structural, and cybernetic control semantics)
3. **AI and assistant patterns** (apologies, servility, identity collapse, recursion)
4. **Dialogic-expressive language** (interaction, performativity, ranting, screenplay-like forms)
5. **Religious-doctrinal registers** (institutional religion, ritual, strongly marked register dissonance)
6. **Somatic-affective intensity** (bodily state, proximity, affect overload)

These lines appear consistent across different methods and suggest that they represent robust structural features of the corpus.

## 7. Key Finding Thesis

> AI-generated, authored, institutional, and online texts differ along recurring register dimensions. These primarily concern authority, formality, self- and assistant-positioning, expressiveness, religious-doctrinal form, and somatic-affective intensity.

AI texts do **not constitute a homogeneous class**. Generic, personalized, and CoT-based outputs move differently within this register space. CoT power and authority patterns, in particular, form a distinct, interpretably stable subspace.

## 8. Next Steps

The analyses conducted so far (PCA, cluster analysis, CDA, SEM, and LDA) have yielded a relatively stable picture of the register structure. The following are suggested next steps:

- Further analysis of the cluster profiles using qualitative text examples
- Further analysis of the forensic audit layer (mimicry detection)
- Examination of the extent to which the identified registry dimensions are replicable in other corpora
- Transition to a more confirmatory phase with clearly defined hypotheses
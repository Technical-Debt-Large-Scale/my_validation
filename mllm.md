## Manual and LLM-Assisted Agreement

For Apache Cassandra, we compared manual inspection against LLM-assisted labeling. Manual inspection classified **76 of 226 issues (33.63%)** as **architecturally impactful** and **150 issues (66.37%)** as **non-architecturally impactful**. The LLM-assisted inspection classified **96 issues (42.48%)** as **architecturally impactful** and **130 issues (57.52%)** as **non-architecturally impactful**.

Table 1 presents the confusion matrix used to compute the agreement metrics. Manual inspection is treated as the **reference oracle** for the Cassandra dataset. Considering **architectural impact** as the positive class, the LLM-assisted inspection produced:

- **71 True Positives (TP)**
- **25 False Positives (FP)**
- **5 False Negatives (FN)**
- **125 True Negatives (TN)**

The agreement analysis yielded a **Cohen's Kappa coefficient (κ) of 0.721**, which is commonly interpreted as **substantial agreement** according to Cohen and the interpretation scale proposed by Landis and Koch.

The resulting performance metrics are:

| Metric | Value |
|---------|------:|
| Cohen's Kappa | **0.721** |
| Accuracy | **0.867** |
| Precision | **0.740** |
| Recall | **0.934** |
| F1-score | **0.825** |

These results indicate that the proposed LLM-assisted protocol can effectively support **first-pass inspection** of issue reports while still requiring expert validation, particularly for false positives and borderline cases.

### Table 1. Cassandra Agreement Matrix Between Manual and LLM-Assisted Labels

| Manual Label | Architectural | Non-Architectural | Total |
|--------------|--------------:|------------------:|------:|
| **Architectural** | **71** | **5** | **76** |
| **Non-Architectural** | **25** | **125** | **150** |
| **Total** | **96** | **130** | **226** |

Both **manual** and **ChatGPT-assisted** inspections were performed, and **Cohen's Kappa** was computed to quantify the agreement between the two classification processes. All scripts, datasets, prompts, and experimental results are publicly available in the replication package:

**Replication Kit:**  
https://anonymous.4open.science/r/my_validation-3CEC

### Interpretation of Cohen's Kappa

The level of agreement was interpreted according to the widely adopted Landis and Koch scale:

| Cohen's Kappa | Interpretation |
|--------------:|----------------|
| < 0.00 | Poor |
| 0.00–0.20 | Slight |
| 0.21–0.40 | Fair |
| 0.41–0.60 | Moderate |
| 0.61–0.80 | **Substantial** |
| 0.81–1.00 | Almost Perfect |

Since the obtained value (**κ = 0.721**) falls within the **substantial agreement** range, the results suggest that the proposed semi-automatic inspection protocol is sufficiently reliable to support **large-scale issue inspection** when combined with appropriate validation and quality-control procedures.

It is important to emphasize that substantial agreement **does not imply perfect classification**. Instead, it demonstrates that LLM-assisted labeling can provide accurate and scalable **first-pass classifications**, significantly reducing the manual effort required for empirical software engineering studies.

### Qualitative Analysis of Disagreements

A qualitative inspection of the disagreement cases reveals that most classification differences occur in **boundary cases** involving mixed architectural and implementation concerns.

Typical examples include:

- Issues that reference architectural components but are ultimately resolved through localized code changes.
- Issues that initially describe implementation-level symptoms but whose resolution requires deeper architectural modifications.
- Reports containing both maintenance-related and architectural information, making the architectural impact difficult to determine solely from textual evidence.

These observations reinforce the value of a **human-in-the-loop** inspection process. In this workflow, the LLM provides an initial classification and a concise justification, while software engineering researchers or maintainers review cases with **low confidence**, **ambiguous architectural impact**, or **high maintenance relevance** before reaching a final decision.

---
layout: post
title: "Animal Experiments"
date: 2019-08-19
desription: Practical advice about animal experiments
tags: academic animals aug2019
---

# Some thoughts about animal experiments
These are pretty much verbatim from Dr. Christine Peterson's transcription of Dr. Ken Hess's talk.

* IACUC is the ethics committee within MDACC.
* Animal protocols are known as ACUFs (animal care and use forms) - these may cover multiple experiments (even hundreds, but median of 3).
* 97% of animals are mice.
* MDACC requires justification of sample size for animal experiments.
* "Nude" mice have a mutation that enables cancer growth.
* Xenographs
  * Source of implanted cells may be cell lines, tumor samples from patients (i.e. PDX models), or genetically engineered mice.
  * Implantation may be subcutaneous (injected into flank) or orthotopic (matching organ).
* Endpoints
  * Typically tumor size (measured using calipers or imaging), often involves repeated measures.
  * Animal survival (must be via sacrifice for ethnical reasons).
* Analysis plan
  * Must match primary endpoint, scientific interest.
  * Methods should be simple but appropriate.
  * Need to assess what comparison are of interest (just control? between all pairs of treatment groups? interested in synergy, which requires a larger sample size, or just identifying best treatment combination?)
  * For repeated measures of tumor size, challenge is truncation at time of sacrifice.  Could do t-test at specific time point, or better alternative is linear mixed effect modeling. Power calculation is less straightforward but could use gPower or simulation. May want to consider log trasnformation of tumor size.
  * For survival endpoint, exponential assumption not appropriate, also advised against Cox model. Normal distribution may be ok. Right censoring depends on how long mice survive. Consider "survreg" which models shift in mean assuming Gaussian link. Log-rank test is robust to censoring, well-powered for normal data.
* Analysis advice:
  * If normal, no censoring, then ANOVA.
  * If normal and censoring, use survReg with Gaussian link.
  * If not normal and no censoring, use wilcoxon rank sum test or rank-based ANOVA.
  * If not normal and censoring, use log rank test.
* Design
  * Often difficult due to lack of preliminary data.
  * Need to ensure true randomization (rather than just haphazard allocation) and consider blocking (e.g. by weight) and blinding.
  * Sample size of 10 mice per group generally reasonable, maybe 15-20 for survival endpoint.
  * Focus on 2 group comparisons.
  * Need to see big differences to ensure translation to humans, so may want to think twice about larger sample sizes (don't want to be powered to detect small effects).
  * Replication most useful if done externally rather than simply repeating within the same lab.
* See Bates and Clark "The Design and Statistical Analysis of Animal Experiments."




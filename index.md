---
layout: default
title: Ryan Sun
---

# Welcome

I am a postdoctoral fellow in the Department of Biostatistics at the Harvard T.H. Chan School of Public Health.
I also received my PhD from this department in May 2017 under the mentorship of [Professor Xihong Lin](https://content.sph.harvard.edu/xlin/).
Below you can find some of the software that accompanies my work.

You can view my CV [here]({{ https://ryanrsun.github.io/cv }}/files/rsun-20190221.pdf).

# Software
* [GEint](https://github.com/ryanrsun/GEint): An R package for performing inference on gene-environment (GxE) interaction
effects when the environment term is misspecified.
    * Main function is to run the Bootstrap Inference with Corrected Sandwich (BICS) procedure, which provides more
robust inference than, for example, a standard Wald test.
    * Supports testing of multiple interaction terms in the same model. 
    * If utilizing a linear regression model, can also provide analytic expressions for the bias of the interaction
regression coefficient.

![mexico_qqplot](/files/mexico_mdi.png){:class="img-responsive"}
   *QQplots of p-values generated using BICS look much more uniform than those generated using model-based or standwich-type standard errors.*

* [GBJ](https://github.com/ryanrsun/GBJ): An R package for performing set-based inference in genetic association studies with
the Generalized Berk-Jones (GBJ). 
    * GBJ modifies the standard Berk-Jones statistic to provide more power when factors in a set are correlated (e.g. genotypes in the same gene).
    * For users familiar with SKAT, GBJ and SKAT can be used interchangeably. GBJ can also be used with summary statistics.
    * This package also implements the Higher Criticism, Berk-Jones, Generalized Higher Criticism, and Minimum P-value statistics and provides an analytic 
p-value for each of these tests when factors in a set are correlated.   

![rej_regions](/files/rej_regions.png){:class="img-responsive"}
   *The rejection region for GBJ is well-suited to detect moderately sparse signals.*

* [reconstructKM](https://github.com/ryanrsun/reconstructKM): An R package for reconstructing individual-level data from Kaplan-Meier
curves published in medical journals.
    * Requires digitizing software to recapture the "points" on each figure (e.g. DigitizeIt). This step will become more difficult
as the KM curve becomes smoother (more jumps).
    * Once the points have been captured, feed the coordinates and number-at-risk information into the package to reconstruct
individual patient survival times and censored/event indicators.

![rej_regions](/files/two_KM.png){:class="img-responsive"}
   *The original Kaplan-Meier curve (top, NEJM 2018) and one generated using reconstructed data (bottom).*

* [GOF Exact Pvalue](https://github.com/ryanrsun/GOF_exact_pvalue): A C++ binary to calculate the exact p-value for supremum-based
goodness-of-fit tests such as the Berk-Jones and Generalized-Berk Jones when factors in a set are correlated. 
    * Only suitable for small sets, do not try to use with more than ten factors in a set.




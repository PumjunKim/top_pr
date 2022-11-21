# Topological Metrics

## Abstract
> We propose a robust and reliable evaluation metric for generative models by
introducing topological and statistical treatments for a rigorous support manifold
estimation. Existing metrics, such as Inception Score (IS), Fréchet Inception
Distance (FID), and the variants of Precision and Recall (P&R), heavily
rely on support manifolds that are estimated from sample features. However, the
reliability of their estimation has not been seriously discussed (and overlooked)
even though the quality of the evaluation entirely depends on it. In this paper, we
propose Topological Precision and Recall (TopP&R, pronounced “topper”), which
provides a systematic approach to estimating support manifolds, retaining only
topologically and statistically important features with a certain level of confidence.
This not only makes TopP&R strong for noisy features, but also provides statistical
consistency. Our theoretical and experimental results show that TopP&R is robust
to outliers and non-independent and identically distributed (Non-IID) perturbations,
while accurately capturing the true trend of change in samples. To the best of our
knowledge, this is the first evaluation metric focused on the robust estimation of
the support manifold and provides its statistical consistency under noise.

## How to use
```python
from module import top_pr.top_pr as TopPR
import numpy as np

# Real data
REAL = np.random.normal(loc=0.0, scale=1.0, size=[10000, 64])
# Fake data
FAKE = np.random.normal(loc=0.4, scale=1.0, size=[10000, 64])

# Evaluation
TopPR(REAL, FAKE, alpha = 0.1, kernel = "cosine", random_proj = True, f1_score = True)
print(Top_PR.get('fidelity'), Top_PR.get('diversity'), Top_PR.get('Top_F1'))
```

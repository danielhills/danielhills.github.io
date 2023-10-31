---
layout: default
---

# Survival Analysis Part I: Basic concepts and first analyses

__Date read:__ `2021-06-01`

__Paper:__ https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2394262/pdf/89-6601118a.pdf

First of 4 part paper series looking at the core concept of Survival Analysis. Main use case is for analysing survival in cancer patients and the impact of treatment on this.

- Survival events rarely Normally distributed. Tend to have many early events, few late ones -> requires special methods for analysis

### Censorship

A key concept to survival analysis is censorship, there are two main ones to mention:
1. Right censorship - event hasn't happened before end of study (e.g. person still alive at end of cancer study)
2. Left censorship - individual started before observation began (e.g. person had cancer before analysis started)
 
![censorship](images/censorship.png)

In addition there is also inverval censored. This is a bit harder to draw, but essentially it is where individuals go in and out of observation.

### Probabilities

Two probabilities underpin survival analysis:

- `S(t)` - probability of survival from time of origin to time t
- `h(t) / lambda(t)` - probability of event at time t

Kaplan-Meier quation can can used to estimate `S(t)` based on previous values.

### Comparing Survival

If we want to compare survival curves for different groups we can use a standard chi-squared statistic comparing the observed events with the expected events if there was no difference between groups (null hypothesis). From this p-values can be calculated fof significance tests.

When comparing two groups we can look at the hazard ratio `HR = (O1/E1) / (O2/E2)`. A HR of 1 is where the is no difference in survival.

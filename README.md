# Comparative efficacy and acceptability of pharmacological, psychological, and noninvasive brain stimulation interventions for poststroke depression: a component network meta-analysis of randomised controlled trials

This repository contains the analysis data and supplementary results for a component network meta-analysis (cNMA) of interventions for poststroke depression. The three primary outcomes were clinician-rated and self-rating depressive symptom severity at the end of intervention, and acceptability (all-cause discontinuation).

## Analysis data

We used standardised mean differences (SMDs) for continuous outcomes and risk ratios (RRs) for binary outcomes. We fitted random-effects standard NMA models within connected subnetworks and additive cNMA models across the overall network.

## Key R functions

- `pairwise()` prepares study contrasts from arm-level data.
- `netmeta()` fits standard NMA models.
- `discomb()` fits additive cNMA models.
- `netsplit()` compares direct and indirect evidence where both are available.
- `netcomparison()` estimates effects for specified component combinations.

### Minimal examples

The vectors below contain study contrasts prepared with `pairwise()`. For standard NMA, use the contrasts from one connected subnetwork. For additive cNMA, use the contrasts from the overall network.

```r
sm <- "SMD"  # Use "RR" for binary outcomes.

netmeta::netmeta(TE, seTE, treat1, treat2, studlab, sm = sm)
netmeta::discomb(TE, seTE, treat1, treat2, studlab, sm = sm, sep.comps = "+")
```

See the [netmeta reference manual](https://cran.r-project.org/package=netmeta) for function arguments.

## Supplementary results

The `results/` folder contains outcome-specific analyses, assessments of model assumptions, sensitivity analyses, and visualisations. Interactive displays cover component effects, treatment effects, and exploratory estimates for component combinations.

# Experiment Design Audit — Power, Selection & Weighting

## Objective
I examined how low statistical power and selection bias can lead to misleading conclusions in experiments and observational studies.

## Methodology
- Audited an A/B test that assigned 2% of traffic to treatment, resulting in 1,000 treatment users.
- Calculated statistical power and the sample size needed to detect a 0.8 percentage-point lift.
- Wrote my own `power_check` function and compared its results with `statsmodels`.
- Examined selection bias in a wellness-program comparison by comparing the naive estimate with the true treatment effect.
- Applied inverse probability weighting (IPW) to adjust for differences between the treatment and comparison groups.

## Key Findings
- **Underpowered A/B test:** The original experiment had only 19.8% power to detect a 0.8 percentage-point lift. Achieving 80% power required 12,514 users per group.
- **Power improvement:** With the same 50,000 users split evenly between groups, statistical power would have increased to 97.7%.
- **Selection bias:** The naive wellness-program estimate was -$1,396, compared with the true effect of -$500.
- **Inverse probability weighting:** After applying IPW, the estimated effect improved to -$522, much closer to the true effect.

## Conclusion
I learned that a large sample does not automatically produce reliable results. Experiments need enough statistical power, and observational comparisons need to account for selection bias. I also saw how inverse probability weighting can improve treatment-effect estimates.

# Estimation & Bootstrapping -- Quantifying Uncertainty Without a Formula

## Objective
I measured how uncertain an estimate is with standard errors, confidence intervals and the bootstrap, including for statistics that have no formula.

## Methodology
- I loaded the UCI Adult Census Income data of 32,561 respondents with pandas.
- I treated the full file as a population, drew repeated samples of age and compared the standard deviation of the data with the standard error of the mean across four sample sizes.
- I built a parametric confidence interval for mean age from the CLT and plotted how fast the sampling distribution of the mean became bell-shaped for age and for capital gains.
- I ran the bootstrap by hand on the median age, the median capital gain and the mean capital gain, then ran it again with scipy.stats.bootstrap.
- I compared percentile and BCa intervals on the mean of the heavily skewed capital gains.
- I bootstrapped the difference in mean weekly hours between men and women.
- I asked an AI to write a bootstrap-interval function, revised my prompt once and checked the function against my own intervals.

## Key Findings
- The standard deviation of age stayed the same while the standard error of the mean fell with the square root of the sample size.
- The CLT converged quickly for age and slowly for capital gains.
- The bootstrap SE of the median of 32,561 whole-number ages was exactly 0.0000 because with that many ties every resample returned the same median, so the bootstrap reported a real property of the data instead of failing.
- On the skewed capital gains the BCa interval moved slightly away from the percentile interval to correct for skew.
- The interval for the difference in mean weekly hours between men and women didn't contain zero.
- The AI's bootstrap function matched my own interval once my revised prompt gave it a seed.

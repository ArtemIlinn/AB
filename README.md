# 🅰️/🅱️ Tests

An A/B test is a tool that allows us to make reliable conclusions about the impact of a change on a product, through the use of statistical methods and parallel collection of data for compared groups.


## 🛤 Sequence of steps when conducting an A/B test:
1. Select metrics and formulate hypotheses.
2. Select the randomization method and determine the sampling parameters.
3. Determine the required sample size.
4. We launch the experiment and collect data.
5. We check the validity of the experiment.

The division into groups within the A/B test should occur in parallel and randomly. This eliminates the influence of effects other than the change being tested on the metric.
When designing an experiment, it is important to consider the potential presence of network effects. If groups influence each other, then instead of simple randomization by user, more complex methods must be used.
Before conducting the test, we need to calculate the required sample size. Only after it is collected can the results be analyzed.
It is important not only to directly analyze the test results, but also to additionally check the validity of the experiment. Such checks are the A/A test and the SRM test.



## 🧭 Quantitative Metrics
All metrics are divided into quantitative, conversion and relationship metrics.
Revenue can be calculated on average per user, paying user or order.

The relationship between ARPU and ARPPU is described by the formula: 

$ARPU = ARPPU ⋅ PayingShare$, 

where Paying share is the share of users who made a purchase.

To calculate the sample size, it is necessary to estimate the variance in the test and control groups. Since the sample size is calculated before the sample itself is recruited, these variances are estimated by averaging the variance over several past periods.
To analyze changes in quantitative metrics, we can use a T-test or a bucket test.


## 📥 Conversions and relational metrics
Conversion is the percentage of users who completed the target
action. It is can be calculated using the formula: 

$CR_{X to Y} = \frac{K}{N} ⋅ 100$%, 

where $K$ is the number of users who performed the target action, $Y$ (reached step $Y$), $N$ is the number of users who performed action $X$ (reached step $X$).

The variance of conversion metrics is calculated using the formula:

$Var_{Bernoulli} = \bar{p} ⋅ (1 - \bar{p})$, 

where $\bar{p}$ - calculated conversion.

To calculate the required sample size for conversion metrics, at the experiment planning stage it is necessary to estimate the variances of the test and control groups. To do this, the variances of the conversion metric over past periods are averaged.
Ratio metrics differ from quantitative and conversion metrics in that for them the randomization unit chosen within the experiment is not coincides with the unit of analysis. For such metrics, the T-test and Z-test for proportions cannot be used in their pure form.

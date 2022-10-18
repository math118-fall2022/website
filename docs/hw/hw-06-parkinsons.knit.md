---
title: "HW 06 - Parkinsons"
subtitle: "due Tuesday, Nov. 1 at 11:59pm"
output: 
  tufte::tufte_html:
    highlight: pygments
    css: "math118-hw.css"
    toc: true
    toc_depth: 2
link-citations: yes
---



# Introduction and Data

The goal of today's lab is to practice statistical inference using
simulation procedures. The data for today's lab may be found by cloning your repository available at the class GitHub repository. Use the lecture notes, readings, and application exercises to help you complete the lab. You can also use [this chart on simulation-based inference](img/06-parkinsons/sim-inference-chart.png) to help you determine the appropriate sampling scheme when conducting simulation-based inference.

The dataset is adapted from Little et al. (2007), and contains voice 
measurements from individuals both with and without Parkinson's Disease (PD), a progressive neurological disorder that affects the motor system. The aim of Little et al.'s study was to examine whether they could diagnose PD by examining the spectral (sound-wave) properties of patients' voices.

147 measurements were taken from patients with PD, and 48 measurements were
taken from healthy controls. For the purposes of this lab, you may assume that measurements are representative of the underlying populations (PD vs. healthy).

The variables in the dataset are as follows:

- `clip`: ID of the recording number
- `jitter`: a measure of variation in fundamental frequency
- `shimmer`: a measure of variation in amplitude
- `hnr`: a ratio of total components vs. noise in the voice recording
- `status`: PD vs. Healthy
- `avg.f.q`: 1, 2, or 3, corresponding to average vocal fundamental frequency 
(1 = low, 2 = mid, 3 = high)

You may load in the data with the following code, where `____` should be
replaced by a meaningful name of your choosing:


```r
library(tidyverse)
library(infer)
____ <- read_csv("data/parkinsons.csv")
```

# Exercises

<br> 

<div class = "commit">
<b>NOTES</b>
<ul>
  <li>To write $\mu$, type in `$\mu$` in the narrative. To write $\alpha$, type in `$\alpha$` in your narrative. To write $\neq$, type in `$\neq$` in your narrative.</li>
  <li>At that start of each exercise that requires simulation, set a random seed equal to the Exercise number in the R chunk.</li>
</ul>
</div>


### Part 1 

Is there enough evidence to suggest that the mean HNR in the voice recordings of the healthy patients is significantly different from 25 at the $\alpha$ = 0.05 significance level? 

1. Write out the null and alternative hypotheses for this question in both
words and symbols. 

<label for="tufte-mn-" class="margin-toggle">&#8853;</label><input type="checkbox" id="tufte-mn-" class="margin-toggle"><span class="marginnote"></span>

2. Display a visualization of your simulated null distribution, and describe the values that would cause you to reject your null hypothesis (called the *rejection region*). Does our observed sample mean lie in this rejection region?

<label for="tufte-mn-" class="margin-toggle">&#8853;</label><input type="checkbox" id="tufte-mn-" class="margin-toggle"><span class="marginnote"></span>

3. What is your p-value, decision, and conclusion in context of the
research question?

<label for="tufte-mn-" class="margin-toggle">&#8853;</label><input type="checkbox" id="tufte-mn-" class="margin-toggle"><span class="marginnote"></span>

4. Given your conclusion in Exercise 3, which type of error could you possibly have made? What would making such an error mean in the context of the research question?

<label for="tufte-mn-" class="margin-toggle">&#8853;</label><input type="checkbox" id="tufte-mn-" class="margin-toggle"><span class="marginnote"></span>


<!-- ### Part 2 -->

<!-- Researchers suspect that patients with PD are less able to control their vocal muscles, and thus may have a different HNR (tonal component to noise ratio)  compared to healthy volunteers. Thus, they are interested in whether the mean HNR in voice recordings among patients with PD is statistically significantly different from 24.7 at the 0.05 significance level.  -->


<!-- 5. Write out the null and alternative hypotheses for this question in both -->
<!-- words and symbols.  -->

<!-- ```{marginfigure} -->
<!-- ``` -->

<!-- 6. Display a visualization of your simulated null distribution, and describe the values that fall into the rejection region. Does our observed sample mean lie in this rejection region? -->

<!-- ```{marginfigure} -->
<!-- ``` -->

<!-- 7. What is your p-value, decision, and conclusion in context of the -->
<!-- research question? -->

<!-- ```{marginfigure} -->
<!-- ``` -->

<!-- 8. Given your conclusion in Exercise 6, which type of error could you possibly have made? What would making such an error mean in the context of the research question? -->

<!-- ```{marginfigure} -->
<!-- ``` -->

### Part 2

Suppose we are now interested in testing whether a correlation exists between voice jitter and voice shimmer among healthy volunteers. Test whether the correlation between these two values is non-zero at the $\alpha$  = **0.01** level. 

<label for="tufte-mn-" class="margin-toggle">&#8853;</label><input type="checkbox" id="tufte-mn-" class="margin-toggle"><span class="marginnote"><span style="display: block;">As an aside, correlation is given in symbols by <span
class="math inline">\(\rho\)</span>.</span></span>

5. Write out the null and alternative hypotheses in words. 

<label for="tufte-mn-" class="margin-toggle">&#8853;</label><input type="checkbox" id="tufte-mn-" class="margin-toggle"><span class="marginnote"><span style="display: block;"><strong>Hint</strong>: Refer to HW 05 for what to
<code>specify()</code>. Use
<code>hypothesize(null = "independence")</code>. The type of simulated
data we will <code>generate()</code> depends on two
quantities/variables; consult the chart.</span></span>

6. Display a visualization of your simulated null distribution, and describe the values that would cause you to reject your null hypothesis. Does the observed sample correlation lie in this rejection region?

<label for="tufte-mn-" class="margin-toggle">&#8853;</label><input type="checkbox" id="tufte-mn-" class="margin-toggle"><span class="marginnote"></span>

7. What is your p-value, decision, and conclusion in context of the
research question?

<label for="tufte-mn-" class="margin-toggle">&#8853;</label><input type="checkbox" id="tufte-mn-" class="margin-toggle"><span class="marginnote"></span>

8. What is the probability you've made a Type 1 error? If you cannot tell for sure, explain why. Similarly, what is the probability you've made a Type 2 error? If you cannot tell for sure, explain why.

<label for="tufte-mn-" class="margin-toggle">&#8853;</label><input type="checkbox" id="tufte-mn-" class="margin-toggle"><span class="marginnote"></span>

# Submission

Knit to PDF to create a PDF document. Knit and commit all remaining changes, and push your work to GitHub. Make sure all files are updated on your GitHub repo.

Please then upload your PDF document to Canvas.

# Lab 05 — Sampling Distributions, Standard Error, and Bootstrap

EAES 480: Modern Statistics in Earth & Environmental Science
University of Illinois Chicago
Instructor: Dr. Gavin McNicol

# Dataset & Study Context

This lab continues using the simplified AmeriFlux-style dataset from the US-AMS site at Argonne National Laboratory (near Chicago, IL) covering 2023 at 30-minute resolution.

What is AmeriFlux?

AmeriFlux is a network of ecosystem observation sites (primarily eddy covariance towers) that measure exchanges of:  
	* carbon dioxide (CO₂),
	* water vapor,
	* energy,

between ecosystems and the atmosphere, along with supporting meteorological variables.

AmeriFlux overview: https://ameriflux.lbl.gov/about/about-ameriflux/
AmeriFlux variable documentation: https://ameriflux.lbl.gov/data/aboutdata/data-variables/

# Why This Dataset is Ideal for Sampling Distributions

The US-AMS time series contains:  

	* strong seasonality,
	* a clear day–night cycle,
	* structured variability across months,
	* and substantial short-term fluctuations.

This makes it ideal for exploring:  

	* how point estimates vary from study to study,
	* how sample size affects accuracy,
	* how sampling distributions emerge,
	* and how bootstrap methods approximate uncertainty.

# Overview

This lab moves from sampling design to sampling distributions and uncertainty.

Rather than focusing on one sample, we now imagine:

What if we repeated the same study many times?

This assignment emphasizes:  

	* distinguishing population parameters from point estimates,
	* measuring accuracy using relative error,
	* generating approximate sampling distributions using simulation,
	* understanding how standard error scales with sample size,
	* and using the bootstrap to estimate uncertainty from one sample.

You will work in a structured R Markdown (.Rmd) document that combines:  

	* guided fill-in sections,
	* partially scaffolded pipelines,
	* and sections where you write code from scratch.

This lab prepares you directly for hypothesis testing and confidence intervals in Unit 3.

# Learning Goals

By the end of this lab, you should be able to:  

	* Clearly distinguish a population parameter from a sample estimate
	* Compute and interpret relative error
	* Simulate repeated studies using replicate()
	* Visualize and interpret a sampling distribution
	* Explain the difference between increasing:
		* sample size (n)
		* number of replicated studies (reps)
	* Compute and interpret standard error (SE = σ / √n)
	* Implement a basic bootstrap procedure
	* Produce a fully reproducible R Markdown analysis

# What You’ll Do

In the provided R Markdown template, you will:  

	* Select 2–3 variables from the US-AMS dataset
	* Compute population mean and SD (parameters)
	* Draw samples and compute point estimates
	* Calculate relative error
	* Simulate repeated studies to generate sampling distributions
	* Examine how sampling variability changes with sample size
	* Compare simulated SE to theoretical SE
	* Perform a bootstrap analysis from a single sample
	* Write short conceptual responses explaining what the results mean

This lab emphasizes statistical reasoning as much as coding.

# Repository Contents

Contents

	*	lab-05-sampling-bootstrap-dist.Rmd
→ The lab template you will complete and submit

	*	README.md
→ This file

	*	data/us-ams-simple.csv
→ Simplified AmeriFlux-style dataset (US-AMS, 2023)

Instructions  

	1.	Fork or clone this repository to your own GitHub account
	2.	Open lab-05-sampling-bootstrap-dist.Rmd in RStudio
	3.	Work through the document from top to bottom
	4.	Complete all code chunks (some fill-in, some from scratch)
	5.	Answer interpretation prompts in complete sentences
	6.	Knit regularly to catch errors early

⚠️ Code that runs in the Console but not in the .Rmd does not count.

# Reproducibility Requirements

Your submission must:  

	* Knit without errors
	* Run top-to-bottom in a clean R session
	* Include all required libraries in the setup chunk
	* Avoid hard-coded local file paths
	* Use na.rm = TRUE where appropriate
	* Use set.seed() where instructed
	* Clearly define any chosen variable names (e.g., target_var)

These are not stylistic preferences—they are scientific standards.

# Submission

You should:  

	* Commit and push your completed .Rmd file to your GitHub repository
	* You do not need to submit the knitted HTML unless instructed

Your work will be evaluated on:  

	* correctness of simulation logic,
	* clarity of interpretation,
	* understanding of sampling distributions,
	* and reproducibility.

# Collaboration Policy

Please consider:  

	* You may discuss statistical concepts and simulation logic
	* You may not copy code verbatim from classmates
	* Code you submit must be written and understood by you

# Why This Matters

In Earth & Environmental Science:  

	* we rarely observe full populations,
	* field campaigns are expensive and limited,
	* and conclusions depend on sampling variability.

Understanding sampling distributions is what allows us to:  

	* quantify uncertainty,
	* build confidence intervals,
	* and test hypotheses responsibly.

This lab is the bridge between descriptive statistics and formal inference.


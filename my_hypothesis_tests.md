# My Hypothesis tests

To verify the hypotheses we can use the following approach:
## 1. Identify the null and alternative hypotheses.

The null hypothesis is the statement that the three characteristics listed are not associated with issues with architectural impact. 

The alternative hypothesis is the statement that the three characteristics are associated with issues with architectural impact.

## 2. The statistical test (Chi-squared test, Mann-Whitney U test). 

The choice of statistical test will depend on the specific characteristic you are testing. 
For example: to test the hypothesis that issues with architectural impact issues with architectural impact require more time for resolution you can use a Mann-Whitney U test.
The chi-squared test must be used to normalized data.

## 3. Collect data. 

We will need to collect data on the **number of files** affected, the **number of lines of code changed**, and the **time to resolution** for both issues with architectural impact and issues without architectural impact.

## 4. Calculate the test statistic and p-value. 

The test statistic is a measure of the evidence against the null hypothesis. 

The *p-value* is the probability of obtaining a test statistic as extreme or more extreme than the one you observed, assuming that the null hypothesis is true.

Consider alpha=0.05

## 5. Make a decision. 

If the *p-value* is less than your chosen significance level, then you reject the null hypothesis and conclude that the evidence supports the alternative hypothesis.

# Results of Hypothesis Tests

## RQ1) Do architectural impact issues affect a substantial number of LOC changes in commits?

### T1: HA - issues with architectural impact affect a substantial number of LOC changes in commits.

To test the hypothesis that issues with architectural impact affect a substantial number of LOC changes in commits:

**Null hypothesis (H0A)**: The number of LOC changed in commits affected by issues with architectural impact is not significantly different from the number of files affected by issues without architectural impact.

**Alternative hypothesis (H1A)**: The number of LOC changed in commits affected by issues with architectural impact is significantly greater than the number of LOC changes affected by issues without architectural impact.

**Alternative hypothesis (H2A)**: The number of LOC changed in commits affected by issues with architectural impact is significantly lower than the number of LOC changes affected by issues without architectural impact.

**Statistical test**: Mann-Whitney U test

| T1:HA   	| Cassandra | ActiveMQ | Kafka	   | Hadoop	   |
| --------- | --------- | -------- | --------- | --------- |
| h0stats   | 7466.5    | 2568.0   | 5138.0    | 2144.5    | 
| h0p-value | 0.00108   | 0.01891  | 0.000196  | 0.00145   | 
| p-value   | 0.00053   | 0.00945  | 9.82e-05  | 0.00072   |
| effec-size| 0.54716   | 0.54376  | 0.58016   | 0.83171   |
| H0A 		  | Rejected  | Rejected | Rejected  | Rejected  | 
| H1A 		  | Accepted  | Accepted | Accepted  | Accepted  |
| H2A 		  | Rejected  | Rejected | Rejected  | Rejected  |

![Boxplot Lines - LOC - changes in Commits in issues with AI](https://github.com/armandossrecife/my_validation3/blob/main/imagens/boxplot_lines_chagnes_in_commits_issues_with_ai.png)

![lines_changes_in_commits_issues](https://github.com/armandossrecife/my_validation3/blob/main/imagens/lines_changes_in_commits_issues.png)


## RQ2) Do architectural impact issues affect a substantial amount of modified files in commits?

### T2: HB - issues with architectural impact affect a substantial number of files

To test the hypothesis that issues with architectural impact affect a substantial number of files:

**Null hypothesis (H0B)**: The number of files affected by issues with architectural impact is not significantly different from the number of files affected by issues without architectural impact.

**Alternative hypothesis (H1B)**: The number of files affected by issues with architectural impact is significantly greater than the number of files affected by issues without architectural impact.

**Alternative hypothesis (H2B)**: The number of files affected by issues with architectural impact is significantly lower than the number of files affected by issues without architectural impact.

**Statistical test**: Mann-Whitney U test

| T2:HB   	| Cassandra | ActiveMQ | Kafka	   | Hadoop	   |
| --------- | --------- | -------- | --------- | --------- | 
| h0stats   | 8299.5    | 2765.0   | 5367.5    | 1845.0    |
| h0p-value | 0.00071   | 0.00507  | 0.00164   | 0.05692   |
| p-value   | 0.00035   | 0.00253  | 0.00082   | 0.05692   |
| effec-size| 0.56297   | 0.60501  | 0.5655    | 0.61094   |
| H0B 	    | Rejected  | Rejected | Rejected  | Accepted  |
| H1B 	    | Accepted  | Accepted | Accepted  | Rejected  |
| H2B 		  | Rejected  | Rejected | Rejected  | Rejected  |

![Boxplot Files chagnes in Commits in issues with AI](https://github.com/armandossrecife/my_validation3/blob/main/imagens/boxplot_files_chages_in_commits_issues_with_ai.png)

![modified_files_in_commits_issues](https://github.com/armandossrecife/my_validation3/blob/main/imagens/modified_files_in_commits_issues.png)


## RQ3) Do architectural impact issues require more time for resolution?

### T3: HC - issues with architectural impact require more time for resolution
To test the hypothesis that issues with architectural impact require more time for resolution:

**Null hypothesis (H0C)**: The time to resolution for issues with architectural impact is not significantly different from the time to resolution for issues with less architectural impact.

**Alternative hypothesis (H1C)**: The time to resolution for issues with architectural impact is significantly greater than the time to resolution for issues with less architectural impact.

**Alternative hypothesis (H2C)**: The time to resolution for issues with architectural impact is significantly lower than the time to resolution for issues with less architectural impact.

**Statistical test**: Mann-Whitney U test

| T3:HC   	| Cassandra | ActiveMQ | Kafka	   | Hadoop	   |
| --------- | --------- | -------- | --------- | --------- |
| h0stats   | 6252.5    | 1655.0   | 3583.5    | 2916.0    |
| h0p-value | 0.000218  | 0.19534  | 0.02584   | 2.459e-09 |
| p-value   | 0.000109  | 0.19534  | 0.01292   | 1.229e-09 |
| effec-size| 0.64695   | 0.26989  | 0.47917   | 1.11671   |
| H0C 		  | Rejected  | Accepted | Rejected  | Rejected  |
| H1C 		  | Accepted  | Rejected | Accepted  | Accepted  |
| H2C 		  | Rejected  | Rejected | Rejected  | Rejected  |

![Boxplot Issues Time Resolution](https://github.com/armandossrecife/my_validation3/blob/main/imagens/boxplot_timeresolution_issues.png)

![time_resolution_in_commits_issues](https://github.com/armandossrecife/my_validation3/blob/main/imagens/time_resolution_in_commits_issues.png)

## RQ4) Do commits with SATD and issues with architectural impact affect a substantial number of LOC changes?

### T4:HD - Commits with SATD and issues with architectural affect a substantial number of LOC changes

**Null Hypothesis (H0D)**: Don't these commits affect as many LOCs as those without SATD?

**Alternative hypothesis (H1D)**: Do these commits affect more LOC than those without SATD?

**Alternative hypothesis (H2D)**: Do these commits affect less LOC than those without SATD?

| T4:HD   		| Cassandra | ActiveMQ | Kafka	   | Hadoop	   |
| --------------| --------- | -------- | --------- | --------- |
| h0stats   	| 4071.0    | 582.0    | 3049.0    | 1104.0    | 
| h0p-value 	| 2.427e-09 | 0.016719 | 0.0001283 | 2.582e-05 |
| p-value   	| 1.213e-09 | 0.008359 | 6.417e-05 | 1.291e-05 |
| effec-size	| 1.1888854 | 0.884572 | 0.8608436 | 1.3019999 |
| H0D 		  	| Rejected  | Rejected | Rejected  | Rejected  |
| H1D 		  	| Accepted  | Accepted | Accepted  | Accepted  |
| H2D 		  	| Rejected  | Rejected | Rejected  | Rejected  |

![Boxplot Lines - LOC - changes in Commits in issues with AI with SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxplot_lines_chagnes_in_commits_issues_with_ai.png)

![lines_changes_in_commits_issues with SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/lines_changes_in_commits_issues_satd.png)

## RQ5) Do commits with SATD and issues with architectural impact affect a substantial modified files changes?

### T5:HE - Commits with SATD and issues with architectural affect a substantial modified files changes

**Null Hypothesis (H0E):** Don't these commits modify as many files as those without SATD?

**Alternative hypothesis (H1E):** Do these commits affect more files than those without SATD?

**Alternative hypothesis (H2E):** Do these commits affect fewer files than those without SATD?

| T5:HE   	 | Cassandra | ActiveMQ | Kafka	    | Hadoop	|
| ---------- | --------- | -------- | --------- | --------- |
| h0stats    | 4032.0    | 596.5    | 2641.5    | 1037.5    |
| h0p-value  | 3.169e-06 | 0.086074 | 0.0025881 | 0.0002208 |
| p-value    | 1.584e-06 | 0.086074 | 0.0012940 | 0.0001104 |
| effec-size | 0.9550442 | 0.552624 | 0.6963532 | 1.1450433 |
| H0E 		 | Rejected  | Accepted | Rejected  | Rejected  |
| H1E 		 | Accepted  | Rejected | Accepted  | Accepted  |
| H2E 		 | Rejected  | Rejected | Rejected  | Rejected  |

![Boxplot Files chagnes in Commits in issues with AI with SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxplot_files_chages_in_commits_issues_with_ai_satd.png)

![modified_files_in_commits_issues with SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/modified_files_in_commits_issues_satd.png)

More details in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_comparison.ipynb

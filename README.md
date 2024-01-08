# Validating the ATDCodeAnalyzer method

To validate the [ATDCodeAnalyzer](https://github.com/Technical-Debt-Large-Scale/atdcodeanalyzer), we executed the following steps:

1. **Development of an Inspection Labeling Process**: We created a process to label inspections, facilitating the identification of issues with potential architectural impacts.

2. **Analysis of Four Open-Source Repositories**: Employing the ATDCodeAnalyzer, we extracted critical classes from each repository. We examined the behavior of LOC changes in commits, modified files, and time resolution within issues bearing Architectural Impact. Additionally, we explored the behavior of LOC changes and modified files in commits with critical classes affected by SATD and issues with Architectural Impact.

3. **Analysis of SATD in Repository Commits**: We thoroughly assessed SATD within the commits of each repository, scrutinizing the behavior of LOC changes, modified files, and issues associated with commits featuring critical classes.

![Validating the ATDCodeAnalyzer](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/Validating_the_ATDCodeAnalyzer.png)

# Analysing Issues with Architectural Impact

Analysis of [commits and issues](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/analysis_commits_issues.jpg) from Git Repositories using Critical Classes from [ATDCodeAnalyzer](https://github.com/Technical-Debt-Large-Scale/atdcodeanalyzer/blob/main/docs/diagrams/AnalysisCassandraRepositoryFlow.png).

We have been analysed four Java Software project Git Repositories: Apache Cassandra, Apache ActiveMQ, Apache Kafka and Apache Hadoop. We evaluated 678 issues from Cassandra (226), ActiveMQ (132), Kafka (179) and Hadoop (141) using an inspection aided by the LLM model to classify them as either Yes or No based on their architectural impact.

We selected a representative dataset of Git repositories, encompassing significant source code repositories such as Apache Cassandra, Apache Kafka, Apache Hadoop and Apache ActiveMQ. These repositories exhibit complex software architectures, boasting many attributes, including more than 10000 commits, over 100 collaborators, over 1000 Java files, over 100000 lines of code, and at least ten-year lifetime. Consequently, these repositories are characterized by substantial commit histories, many contributors, intricate codebases, and widespread adoption within the software industry. Each repository's numerical and metric attributes will be comprehensively detailed. We applied the [ATDCodeAnalyzer](https://github.com/Technical-Debt-Large-Scale/atdcodeanalyzer) method to the repositories to identify critical files impacted by Architectural Technical Debt.

We examine if these issues indicate architectural problems within the software. These problems encompass: software's structure, organizational issues, quality software, issues that impact evolvability and maintainability. For example: changes to core components,performance improvements, scalability snhancements, concurrency and parallelism, resource management, data model changes, distributed system aspects, consistency and availability, extensibility and plugin frameworks, security and compliance, system modularity, data integrity and durability, etc.

We also examined the behavior of LOC changes and modified files in commits related to Self-admitted Technical Debt (SATD) found in comments from the diffs of each commit.

Related to "architectural impact issues" found by **issues in commits with critical classes** in the selected software repositories: 

RQ0) What is the proportion of issues classified as impacting architectural design, as observed in each analyzed software repository?

RQ1) Do architectural impact issues affect a substantial number of LOC changes in commits with critical classes?

RQ2) Do architectural impact issues affect a substantial amount of modified files in commits with critical classes?

RQ3) Do architectural impact issues require more time for resolution?

RQ4) Do commits with critical classes and SATD and issues with architectural impact affect a substantial number of LOC changes?

RQ5) Do commits with critical classes and SATD and issues with architectural impact affect a substantial modified files changes?

## Apache Cassandra analysis

Draft of Cassandra's commit and issue analysis method

![My analysis of commits and issues from Cassanddra](https://raw.githubusercontent.com/armandossrecife/my_validation3/main/imagens/my_method_analysis_commits_issues.jpg)

1. Filtering (A) - Cassandra Project:
This step involves selecting and filtering data related to the Apache Cassandra project from the GitHub repository.

3. Filtering (A) - Commits with Critical Classes:
After filtering the Cassandra project data, you further narrow down the focus by identifying commits that involve critical classes. Critical classes may be those that are related to architectural or high-impact changes.

4. Filtering (B) - Cassandra Project:
In this step, you do a similar filtering process but on the Jira Issue Tracker, specifically looking for issues related to the Cassandra project.

5. Filtering (B) - Issues with Commits with Critical Classes:
This step involves identifying Jira issues that are associated with commits containing critical classes. It's a way to link code changes with corresponding issues.

6. Random Sample Selection from 4 that results in 226 issues:
Here, you randomly select a subset of the filtered issues. The reason  is for further analysis.
Based on a normal continuous random variable from [ScyPY](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.norm.html)
Based on the parameters: confidence_level = 0.95, margin_of_error = 0.05, population_proportion = 0.8 and population_size = len(issues_with_commits_with_critical_classes)
sample_size = calculate_sample_size(confidence_level, margin_of_error, population_proportion, population_size)
norm.ppf(): normal continuous random variable

7. Manual classification of issues to check architectural impact:
You manually review and classify the selected 226 issues to assess their architectural impact. This could involve identifying whether the issue relates to architectural changes, refactoring, or other factors.

8. Semi-automatic classification aided by ChatGPT with Prompt Engineering:
In this step, you use ChatGPT to assist in the classification process. You might provide prompts to ChatGPT to help automate or semi-automate some of the classification tasks. More details in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/inspection_process.md

9. Degree of Agreement Calculation comparing 6 and 7:
This step involves calculating the degree of agreement between the manual classification and the semi-automatic classification performed with the help of ChatGPT. You need to quantify how closely the two methods align.

10. Degree Agreement using Cohen's Kappa:
Cohen's Kappa is a statistical measure used to assess the agreement between two raters (in this case, the manual and ChatGPT-assisted classifications). It takes into account the possibility of agreement occurring by chance.

The calculated Cohen's Kappa score was found to be 0.721, indicating a substantial level of agreement between manual inspection and ChatGPT inspection.

In our evaluation of the model used for inspecting issues, we obtained the following key performance metrics: Precision: 0.962, Recall: 0.833, Accuracy: 0.867 and F1-Score: 0.893.

More details about evaluation of precision of inspection process is available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/evaluate_inspection_model.ipynb

This semi-automatic inspection process (aided by ChatGPT) can help to inspect other issues from other apache projects. 

More details and scripts are available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_cassandra.ipynb

## Apache ActiveMQ analaysis

ActiveMQ analysis

![My analysis of commits and issues from ActiveMQ](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_method_analysis_commits_issues_activemq.jpg)

More details and scripts available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_activemq.ipynb

## Apache Kafka analysis

Kafka analysis

![My analysis of commits and issues from Kafka](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_method_analysis_commits_issues_kafka.jpg)

More details and scripts available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_kafka.ipynb

## Apache Hadoop analysis

Hadoop analysis

![My analysis of commits and issues from Hadoop](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_method_analysis_commits_issues_hadoop.jpg)

More details and scripts available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_hadoop.ipynb

# Results

The comparison of **issues in commits with critical classes** among Cassandra, ActiveMQ, Kafka and Hadoop

## RQ0 - What is the proportion of issues classified as impacting architectural design, as observed in each analyzed software repository?

![% of architectural impact by Repository](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/architectural_impact_by_repo.png)

## RQ1 - Do architectural impact issues affect a substantial number of LOC changes in commits with critical classes?

![Boxplot Lines - LOC - changes in Commits in issues with AI](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxplot_lines_changes_in_commits_issues_with_ai_color.png)

- c1 (Cassandra) - issues with Architectural Impact
- c2 (Cassandra) - issues without Architectural Impact
- a1 (ActiveMQ) - issues with Architectural Impact
- a2 (ActiveMQ) - issues without Architectural Impact
- k1 (Kafka) - issues with Architectural Impact
- k2 (Kafka) - issues without Architectural Impact
- h1 (Hadoop) - issues with Architectural Impact
- h2 (Hadoop) - issues without Architectural Impact

![lines_changes_in_commits_issues](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/lines_changes_in_commits_issues.png)

## RQ2 - Do architectural impact issues affect a substantial amount of modified files in commits with critical classes?

![Boxplot Files chagnes in Commits in issues with AI](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxplot_files_changes_in_commits_issues_with_ai_color.png)

- c1 (Cassandra) - issues with Architectural Impact
- c2 (Cassandra) - issues without Architectural Impact
- a1 (ActiveMQ) - issues with Architectural Impact
- a2 (ActiveMQ) - issues without Architectural Impact
- k1 (Kafka) - issues with Architectural Impact
- k2 (Kafka) - issues without Architectural Impact
- h1 (Hadoop) - issues with Architectural Impact
- h2 (Hadoop) - issues without Architectural Impact
  
![modified_files_in_commits_issues](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/modified_files_in_commits_issues.png)

## RQ3 - Do architectural impact issues require more time for resolution?

![Boxplot Issues Time Resolution](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxplot_timeresolution_issues_color.png)
- c1 (Cassandra) - issues with Architectural Impact
- c2 (Cassandra) - issues without Architectural Impact
- a1 (ActiveMQ) - issues with Architectural Impact
- a2 (ActiveMQ) - issues without Architectural Impact
- k1 (Kafka) - issues with Architectural Impact
- k2 (Kafka) - issues without Architectural Impact
- h1 (Hadoop) - issues with Architectural Impact
- h2 (Hadoop) - issues without Architectural Impact
  
![time_resolution_in_commits_issues](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/time_resolution_in_commits_issues.png)

## RQ4 - Do commits with critical classes and SATD and issues with architectural impact affect a substantial number of LOC changes?

![Boxplot Lines - LOC - changes in Commits in issues with AI and SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxplot_lines_changes_in_commits_issues_with_ai_satd_color.png)

- c1 (Cassandra) - commits with SATD and issues with Architectural Impact
- c2 (Cassandra) - commits without SATD and issues without Architectural Impact
- a1 (ActiveMQ) - commits with SATD and issues with Architectural Impact
- a2 (ActiveMQ) - commits without SATD and issues without Architectural Impact
- k1 (Kafka) - commits with SATD and issues with Architectural Impact
- k2 (Kafka) - commits without SATD and issues without Architectural Impact
- h1 (Hadoop) - commits with SATD and issues with Architectural Impact
- h2 (Hadoop) - commits without SATD and issues without Architectural Impact
  
![lines_changes_in_commits_issues with SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/lines_changes_in_commits_issues_satd.png)

## RQ5 - Do commits with critical classes and SATD and issues with architectural impact affect a substantial modified files changes?

![Boxplot Files chagnes in Commits in issues with AI with SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxplot_files_chages_in_commits_issues_with_ai_satd.png)

- c1 (Cassandra) - commits with SATD and issues with Architectural Impact
- c2 (Cassandra) - commits without SATD and issues without Architectural Impact
- a1 (ActiveMQ) - commits with SATD and issues with Architectural Impact
- a2 (ActiveMQ) - commits without SATD and issues without Architectural Impact
- k1 (Kafka) - commits with SATD and issues with Architectural Impact
- k2 (Kafka) - commits without SATD and issues without Architectural Impact
- h1 (Hadoop) - commits with SATD and issues with Architectural Impact
- h2 (Hadoop) - commits without SATD and issues without Architectural Impact
  
![modified_files_in_commits_issues with SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/modified_files_in_commits_issues_satd.png)

## Hypothesis Tests

[Hypothesis Tests](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_hypothesis_tests.md)

## Conclusions 

Issues with architectural impact (labeled as "Yes") in commits with critical classes exhibit the following **characteristics**:
- They affect a substantial number of files in commits (T1:H1A accepted).
- They involve significant code changes in commits (T2:H1B accepted).
- They require more time for resolution (T3:H1C accepted).

Commits with critical classes and SATD and issues with architectural impact (labeled as "Yes") also have the following **characteristics**:  
- They affect a substantial number of files in commits (T4:H1D accepted).
- They involve significant code changes in commits (T5:H1E accepted).

**Justification**
These conclusions are drawn from a comparative analysis of results from the Cassandra, ActiveMQ, and Kafka repositories, specifically:
- A comparison of the results related to the number of lines and files modified in issue commits with architectural impact (labeled as "Yes") and without architectural impact (labeled as "No").
- A comparison of the results concerning the average time required to resolve issues with architectural impact (also labeled as "Yes") and without architectural impact (labeled as "No").

Furthermore, the inspection of issues that appear in commits containing critical files and have an architectural impact underscores the influence of critical classes on software architecture.

**Contributions**

- We created an LLM model, based on prompt engineering, to help identify issues with architectural impact.
- We provided a dataset (Apache Cassandra, Apache ActiveMQ, Apache Kafka and Apache Hadoop) with detailed information of commits, and issues that have architectural impact
- We provided a dataset (Apache Cassandra, Apache ActiveMQ, Apache Kafka and Apache Hadoop) of text with details about inspections of issues with architectural impact and issues without architectural impact
- We provided a set of scripts that can be performed automatically to analyse the dataset and produce the results of analysis. 

More details in 

https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_comparison.ipynb

# Analyzing SATD in the investigated repositories

We also conducted an analysis of SATD in the investigated repositories to examine the behavior of LOC changes in commits and modified files within commits.

https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/comparing_satd_in_repositories.md

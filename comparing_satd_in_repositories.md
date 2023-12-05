# Analyzing SATD in the investigated repositories (Cassandra, Kafka, ActiveMQ, and Hadoop)

Comparing the presence and impact of Self-admitted Technical Debt (SATD) across repositories like Cassandra, Kafka, ActiveMQ, and Hadoop can provide valuable insights into how SATD manifests and affects software development.

To thoroughly investigate the impact of SATD on software development, we carefully selected the following characteristics for analysis: 
- LOC changes in commits (SATD x No SATD)
- Modified files in commits (SATD x No SATD)
- LOC changes in commits with critical files (SATD x No SATD)
- Modified files in commits with critical files (SATD x No SATD)
- LOC changes in commits without critical files (SATD x No SATD)
- Modified files in commits without critical files (SATD x No SATD)
- **LOC changes in issues in commits with critical files (SATD x No SATD)**
- **Modified files issues in commits with critical files (SATD x No SATD)**

## Analysis of SATD in Different Repositories

1. LOC Changes in Commits

Comparison of Lines of Code (LOC) changes in commits that contain SATD versus those without SATD across each repository.

2. Modified Files in Commits

Examining the number of modified files in commits associated with SATD against commits without SATD in each repository.

3. LOC Changes in Commits with Critical Files

Analyzing LOC changes specifically in critical files within commits where SATD is present versus commits without SATD in each repository.

4. Modified Files in Commits with Critical Files

Comparison of the count of modified files specifically in critical files within commits containing SATD against those without SATD in each repository.

5. LOC Changes in Commits without Critical Files

Evaluating LOC changes in commits without critical files that have SATD versus those without SATD in each repository.

6. Modified Files in Commits without Critical Files

Comparison of the number of modified files in commits without critical files, distinguishing between those with SATD and those without SATD in each repository.

**7. LOC Changes in Issues in Commits with Critical Files**

Assessing the LOC changes in issues identified within commits involving critical files, comparing SATD-related issues with non-SATD issues in each repository.

**8. Modified Files in Issues in Commits with Critical Files**

Analyzing the count of modified files associated with issues in commits involving critical files, distinguishing between SATD-related issues and non-SATD issues in each repository.

By conducting these comparisons across multiple repositories, we can gain insights into the prevalence and impact of SATD, understand its relationship with critical files, and identify patterns in terms of LOC changes and modified files. Such analysis aids in comprehending how SATD affects software repositories of varying complexities and domains, potentially guiding strategies for effective SATD management and software quality improvement.


## Boxplots of Apache Cassandra

Comparing Commits, Isues, Critical Classes and SATD

![Diagram of Apache Cassandra Commits and SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_validation_analysis_commits_satd_cassandra.jpg)

1. Filtering (A) - Commits Extraction:

Extract all commits from the Cassandra Git repository.

2. Filtering (A) - Selecting Critical Classes Commits:

Choose only commits containing critical classes identified by ATDCodeAnalyzer.

3. Filtering (A) - Non-Critical Classes Commits:

Select commits without critical classes.

4. Filtering (B) - All Issues Retrieval:

Retrieve all issues from the Apache Cassandra Jira Issue Tracker.

5. Filtering (B) - Selecting Issues from Commits with Critical Classes:

Choose issues registered in commit messages where the associated commits contain critical classes.

6. Defining SATD Keywords:

Establish a set of Self-Admitted Technical Debt keywords from existing literature.

7. Filtering (A) - SATD Keyword in Modified File Comments:

Select commits containing SATD keywords in comments from modified files' diffs.

8. Filtering (A) - Non-SATD Commits:

Choose only commits without Self-Admitted Technical Debt indicators.

9. Filtering (A) - Critical Classes Commits with SATD:

Select commits with critical classes containing Self-Admitted Technical Debt.

10. Filtering (A) - Critical Classes Commits without SATD:

Select commits with critical classes without Self-Admitted Technical Debt.

11. Filtering (A) - Non-Critical Classes Commits with SATD:

Select commits without critical classes containing Self-Admitted Technical Debt.

12. Filtering (A) - Non-Critical Classes Commits without SATD:

Select commits without critical classes and Self-Admitted Technical Debt.

13. Filtering (B) - Issues in Commits with Critical Classes and SATD:

Choose issues associated with commits containing critical classes and Self-Admitted Technical Debt.

14. Filtering (B) - Issues in Commits with Critical Classes without SATD:

Choose issues linked to commits containing critical classes but without Self-Admitted Technical Debt.

Scenarios of Boxplots of Apache Cassandra 

![Comparing Boxplots of Cassandra](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxsplots_satd_cassandra.png)

More details in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_cassandra.ipynb

## Boxplots of Apache Kafka

Comparing Commits, Isues, Critical Classes and SATD

![Diagram of Apache Kafka Commits and SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_validation_analysis_commits_satd_kafka.jpg)

Scenarios of Boxplots of Apache Kafka 

![Comparing Boxplost of Kafka](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxsplots_satd_kafka.png)

More details in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_kafka.ipynb

## Boxplots of Apache ActiveMQ

Comparing Commits, Isues, Critical Classes and SATD

![Diagram of Apache ActiveMQ Commits and SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_validation_analysis_commits_satd_activemq.jpg)

Scenarios of Boxplots of Apache ActiveMQ 

![Comparing Boxplost of ActiveMQ](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxsplots_satd_activemq.png)

More details in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_activemq.ipynb

## Boxplots of Apache Hadoop

Comparing Commits, Isues, Critical Classes and SATD

![Diagram of Apache Hadoop Commits and SATD](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_validation_analysis_commits_satd_hadoop.jpg)

Scenarios of Boxplots of Apache Hadoop 

![Comparing Boxplost of Hadoop](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/boxsplots_satd_hadoop.png)

More details in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_hadoop.ipynb

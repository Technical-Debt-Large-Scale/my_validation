# Cassandra Critical Java Files and Issue-Related Metrics

## Table Overview

The following table summarizes selected critical Java files from Apache Cassandra and their corresponding commit- and issue-related metrics.

| File | AIC | AICWI | AII | AIB | AIII | AINFI |
|---|---:|---:|---:|---:|---:|---:|
| `StorageService.java` | 1317 | 1034 | 967 | 160 | 79 | 3 |
| `ColumnFamilyStore.java` | 1178 | 893 | 832 | 139 | 96 | 3 |
| `DatabaseDescriptor.java` | 854 | 697 | 659 | 90 | 62 | 4 |
| `StorageProxy.java` | 572 | 445 | 463 | 71 | 55 | 2 |
| `CompactionManager.java` | 668 | 506 | 406 | 72 | 47 | 5 |
| `Config.java` | 500 | 393 | 379 | 58 | 37 | 3 |
| `SSTableReader.java` | 457 | 399 | 352 | 47 | 48 | 1 |
| `MessagingService.java` | 328 | 241 | 288 | 50 | 31 | 1 |
| `NodeProbe.java` | 369 | 303 | 287 | 39 | 26 | 2 |
| `CassandraDaemon.java` | 386 | 316 | 235 | 28 | 34 | 5 |

## Metric Definitions

- **AIC — Appearances in Commits**  
  Number of commits in which the critical file appears.

- **AICWI — Appearances in Commits with Issues**  
  Number of commits containing the critical file that are explicitly linked to JIRA issues.

- **AII — Appearances in Issues**  
  Total number of issue-related appearances associated with the critical file, considering all JIRA issue types.

- **AIB — Appearances in Bug Issues**  
  Number of appearances associated with JIRA issues classified as **Bug**.

- **AIII — Appearances in Improvement Issues**  
  Number of appearances associated with JIRA issues classified as **Improvement**.

- **AINFI — Appearances in New Feature Issues**  
  Number of appearances associated with JIRA issues classified as **New Feature**.

## Additional JIRA Issue Types

The columns **AIB**, **AIII**, and **AINFI** cover three major Apache JIRA issue types:

- Bug;
- Improvement;
- New Feature.

However, Apache JIRA also contains other issue types, including:

- Task;
- Sub-task;
- Test;
- Wish;
- Question;
- other project-specific categories.

Therefore, the value of **AII** may be greater than the sum of **AIB**, **AIII**, and **AINFI**.

The number of appearances associated with other issue types can be calculated as:

```text
Other Issue Appearances = AII - AIB - AIII - AINFI
```

## Interpretation

The table shows that the selected Cassandra critical files are not only frequently modified, but are also repeatedly connected to issue-tracker discussions.

For example:

- `StorageService.java` appears in **1,317 commits**, including **1,034 commits linked to issues**, and has **967 issue-related appearances**.
- `ColumnFamilyStore.java` appears in **1,178 commits**, including **893 commits linked to issues**, and has **832 issue-related appearances**.
- `DatabaseDescriptor.java` also exhibits strong maintenance activity, with **854 commit appearances** and **659 issue-related appearances**.

These results indicate that critical files are strongly involved in Cassandra's maintenance and evolution activities. Because these classes implement central responsibilities related to storage, configuration, messaging, compaction, and node management, their frequent association with issues makes them important candidates for architectural inspection and technical-debt analysis.

## Suggested Table Note for the Paper

> **Note:** AIC denotes appearances of a critical file in commits; AICWI denotes appearances in commits explicitly linked to JIRA issues; AII denotes total appearances in issues across all issue types; AIB, AIII, and AINFI denote appearances in Bug, Improvement, and New Feature issues, respectively. The difference between AII and the sum of AIB, AIII, and AINFI corresponds to other JIRA issue types, such as Task, Sub-task, Test, Wish, and Question.

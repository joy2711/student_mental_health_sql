# Student Mental Health Analysis — SQL

## Overview
This project explores whether studying abroad affects students' mental health, using survey data from a Japanese international university (2018). The study was approved by multiple ethical and regulatory boards.

The analysis focuses on international students and examines how length of stay relates to three mental health indicators:
- PHQ-9 score — measures depression (higher = more depressed)
- SCS score — measures social connectedness (higher = more connected)
- ACAS score — measures acculturative stress (higher = more stressed)

## Key Question
Does length of stay at a foreign university influence depression, social connectedness, and acculturative stress among international students?

## Tools Used
- PostgreSQL
- SQL — filtering, aggregation, grouping

## Query
```sql
SELECT
    stay,
    COUNT(*) AS count_int,
    ROUND(AVG(todep), 2) AS average_phq,
    ROUND(AVG(tosc), 2) AS average_scs,
    ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
```

## Key Findings

| Stay (years) | Count | Avg PHQ-9 | Avg SCS | Avg ACAS |
|---|---|---|---|---|
| 1 | 95 | 7.48 | 38.11 | 72.80 |
| 2 | 39 | 8.28 | 37.08 | 77.67 |
| 3 | 46 | 9.09 | 37.13 | 78.00 |
| 4 | 14 | 8.57 | 33.93 | 87.71 |
| 10 | 1 | 13.00 | 32.00 | 50.00 |

- Most students (95) had only been in the country for 1 year
- Depression scores show a general upward trend in the early years of stay (1→3 years)
- Social connectedness tends to decrease as length of stay increases, suggesting students struggle to maintain belonging over time
- Acculturative stress peaks around year 4-5 before declining in longer stays
- Results are consistent with the original study's finding that social connectedness and acculturative stress are linked to depression in international students

## Dataset
Survey data from students at a Japanese international university, published in 2019. Dataset sourced from DataCamp — not included in this repo.

## Status
Completed as part of the DataCamp Data Analyst track.

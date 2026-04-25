# Student Mental Health Analysis — SQL

## Overview
This project explores whether studying abroad affects students' mental health, using survey data from a Japanese international university (2018). The study was approved by multiple ethical and regulatory boards.

The analysis focuses on international students and examines how length of stay relates to three mental health indicators:
- PHQ-9 score — measures depression
- SCS score — measures social connectedness
- ACAS score — measures acculturative stress

## Key Question
Does length of stay at a foreign university influence depression, social connectedness, and acculturative stress among international students?

## Tools Used
- PostgreSQL (via DataCamp workspace)
- SQL — aggregation, filtering, grouping

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

## What the Query Does
- Filters for international students only (`inter_dom = 'Inter'`)
- Groups them by length of stay
- Calculates average PHQ-9, SCS, and ACAS scores per group
- Orders results from longest to shortest stay

## Dataset
Survey data from students at a Japanese international university, published in 2019.

## Status
Completed as part of the DataCamp Data Analyst track.


# Lab 01 – Splunk Basics (SOC Foundations)

## Objective
Learn core Splunk search commands used by SOC Analysts to explore logs, identify data sources, and understand log volume over time.

## Tools Used
- Splunk Cloud (Search & Reporting)
- Browser-based SPL editor

## Data Source
- index=_internal (Splunk internal logs)

## Skills Practiced
- Basic SPL syntax
- Using stats and timechart
- Understanding sourcetype and event volume
- Time-based analysis

## Status
In progress

## Step 1: Verify Data Is Coming Into Splunk

### Purpose
Confirm that Splunk is receiving logs by querying its internal index.

### SPL Command
```spl
index=_internal
```



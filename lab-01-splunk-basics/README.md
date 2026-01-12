# Lab 01 – Splunk Basics (SOC Foundations)

## Objective
Learn core Splunk search commands used by SOC Analysts.

## Tools Used
- Splunk Cloud (Search & Reporting)
- Browser-based SPL editor

## Data Source
- index=_internal (Splunk internal logs)

## Skills Practiced
- Basic SPL syntax
- Using stats
- Time-based analysis

## Status
In progress

---

## Step 1: Verify Data Is Coming Into Splunk

### Purpose
Confirm that Splunk is receiving logs.

### SPL Command
```spl
index=_internal
### Result
- Internal Splunk logs were successfully queried.
- Event volume over time was visualized using `timechart`.
- Consistent log ingestion was observed across the selected time range.



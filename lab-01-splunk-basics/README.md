# Lab 01 - Splunk Basics (SOC Foundations)

## Objective
Learn core Splunk search commands used by SOC Analysts.

## Tools Used
- Splunk Cloud (Search & Reporting)

## Data Source
- index=_internal (Splunk internal logs)

## Status
In progress

---

## Step 1: Verify Data Is Coming Into Splunk

### Purpose
Confirm that Splunk is receiving logs by querying the internal index.

### SPL Command
```spl
index=_internal
| timechart count
Result
Internal Splunk logs were successfully queried.

Event volume over time was visualized using timechart.

Consistent log ingestion was observed across the selected time range.

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

---

## Step 2: Count Total Events

### Purpose
Determine the total number of events in the internal Splunk index.

### SPL Command
```spl
index=_internal
| stats count
Result
A total of 728,402 events were recorded in the internal index for the selected time range.

This confirms active and continuous log ingestion into Splunk.

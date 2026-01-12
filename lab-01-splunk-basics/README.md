# Lab 01 - Splunk Basics (SOC Foundations)

## Objective
Learn core Splunk search commands used by SOC Analysts.

## Tools Used
- Splunk Cloud (Search & Reporting)

## Data Source
- index=_internal (Splunk internal logs)

## Status
In progress

## Step 1: Verify Data Is Coming Into Splunk

### Purpose
Confirm that Splunk is receiving logs by querying the internal index.

### SPL Command

```spl
index=_internal
| timechart count
```

### Result
Internal Splunk logs were successfully queried.

Event volume over time was visualized using timechart.

Consistent log ingestion was observed across the selected time range

## Step 2: Count Total Events

### Purpose
Determine the total number of events in the internal Splunk index.

### SPL Command

```spl
index=_internal
| stats count
```

### Result
A total of 728,402 events were recorded in the internal index for the selected time range.

This confirms active and continuous log ingestion into Splunk.

## Step 3: Analyze Internal Logs by Sourcetype

### Purpose
Identify and analyze specific internal log sources by grouping events according to their sourcetype.

### SPL Command

```spl
index=_internal sourcetype=splunkd
| stats count by sourcetype
```

### Result
Internal Splunk logs were successfully filtered by the splunkd sourcetype.

A total of 518,706 events were recorded for this sourcetype within the selected time range.

This demonstrates how SOC analysts narrow investigations by focusing on specific internal log sources.

## Step 4: Identify Most Frequent Internal Log Messages

### Purpose
Identify the most common internal log messages to understand frequent system activity within Splunk.

### SPL Command

```spl
index=_internal
| top limit=10 _raw
```

### Result
The most frequent internal log messages were identified from the internal Splunk index.

The message STARTED_SUPERVISOR_BOOTSTRAP was the most common event, indicating repeated internal service initialization activity.

Other recurring messages included SSL warnings, HTTP requests, and telemetry events, reflecting normal background operations within Splunk.

This step demonstrates how SOC analysts identify recurring patterns and high-frequency events during log analysis.

### Screenshot
![Step 4 - Top Raw Events](screenshots/step-04-top-raw.png)

## Step 5: Identify Most Active Sourcetypes

### Purpose

Identify which internal Splunk sourcetypes generate the highest volume of events to understand where most system activity originates.

### SPL Command

```spl
index=_internal
| stats count by sourcetype
| sort - count
```

### Result
The results show that the splunkd sourcetype generates the highest number of internal events, indicating core Splunk daemon activity.

Other high-volume sourcetypes such as mongod, splunkd_access, and splunkd_ui_access represent database operations and user interactions with the Splunk web interface.

This step demonstrates how SOC analysts identify dominant log sources to prioritize monitoring, performance analysis, and troubleshooting.

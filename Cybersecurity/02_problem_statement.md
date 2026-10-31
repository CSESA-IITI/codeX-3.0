# Problem Statement: Suspicious Login Activity Analyzer

**Level:** Beginner to Moderate

## Background

Applications record login attempts in logs. A few failed attempts may simply mean someone forgot a password, but many failures in a short period can suggest an attempt to guess credentials. Manually reviewing these records becomes difficult as the number of users grows.

Build a tool that reads login logs, detects suspicious patterns, and explains which events triggered each alert. The tool should help a user investigate activity without treating every alert as proof of an attack.

## Input

Accept a local CSV file with the following columns:

```csv
timestamp,username,ip_address,status
2026-01-01T10:00:00Z,alice,192.0.2.10,failure
2026-01-01T10:01:00Z,alice,192.0.2.10,failure
2026-01-01T10:02:00Z,alice,192.0.2.10,failure
2026-01-01T10:03:00Z,alice,192.0.2.10,failure
2026-01-01T10:04:00Z,alice,192.0.2.10,failure
2026-01-01T10:04:30Z,alice,192.0.2.10,success
```

Each row represents one login attempt. Use UTC timestamps in the format shown above and accept `success` or `failure` as the status. Use synthetic records while developing the tool.

## Required functionality

### Read and validate logs

Check that the required columns exist. Validate each row's timestamp, nonempty username, IP address, and status. Skip invalid rows with an understandable message and show how many were skipped. Sort valid records by timestamp so that unsorted input can still be analyzed.

### Detect suspicious patterns

Implement these three rules:

1. **Repeated failures against one account:** Flag five or more failed attempts for the same username from the same IP address within five minutes.
2. **Failures across multiple accounts:** Flag failed attempts against at least five distinct usernames from the same IP address within five minutes. This may indicate broad credential guessing.
3. **Success after repeated failures:** Flag a successful login when at least five failures for that same username and IP address occurred during the preceding five minutes.

Use rolling time windows rather than fixed clock intervals. For each event at time `t`, consider events from `t - 5 minutes` through `t`, including the boundary. For the third rule, count only failures before the successful login. Allow users to change the count thresholds and window duration.

For the sample input, the fifth failure triggers the first rule, and the subsequent success triggers the third. The second rule does not trigger because only one username appears.

### Explain the results

Display the total number of valid login attempts, successful attempts, failed attempts, and skipped rows. For each alert, show the rule name, source IP address, relevant username or usernames, time range, and matching failure count.

Let users inspect the events behind an alert. If overlapping windows produce repeated alerts, either group them or clearly identify the event that triggered each alert.

If no rule matches, display a clear message. Explain that these rules identify patterns for investigation: shared networks and ordinary user mistakes can also produce alerts, and activity below the thresholds can still be suspicious.

## Implementation scope

Use Python or another language you are comfortable with. A command-line interface is sufficient; a simple local web interface is also acceptable. Process uploaded or local files only. Live monitoring, machine learning, and automatic account or IP blocking are outside the scope of this project.

## Final deliverables

- **A GitHub repository** containing the working project.
- **A proper README** explaining the problem, setup, how to run the tool, input format, detection rules, configuration options, example usage, and limitations.

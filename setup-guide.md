# Setup Guide

## Overview

This repository documents an AI crawler analysis workflow that leverages Cloudflare Firewall Event exports to identify user agents and evaluate the URLs accessed by AI assistants, crawlers, and automated agents.

The implementation code and generated reports are maintained in a private repository.

This repository contains documentation, architecture information, methodology, and example outputs.

---

## Prerequisites

### Software

- Git
- Visual Studio Code (recommended)
- Python 3.12+ (private implementation only)

### Accounts

- Cloudflare Account
- Access to Cloudflare Firewall Events

---

## Data Collection Process

### Step 1: Access Cloudflare

Navigate to:

Security → Events

or

Security → Analytics

depending on your account configuration.

---

### Step 2: Configure Filters

Example filters:

Verified Bots

AI Crawlers

Allowed Bot Traffic

---

### Step 3: Export Event Data

Export firewall event logs as JSON.

Typical export fields include:

- userAgent
- clientRequestPath
- clientCountryName
- clientASNDescription
- datetime
- action
- description

---

## Analysis Workflow

The private implementation performs the following steps:

### User Agent Discovery

All unique User Agents are identified from the Cloudflare export.

### Crawl Grouping

Requests are grouped by:

- User Agent
- URL
- Country
- ASN (optional)

### URL Deduplication

URLs are deduplicated to identify unique content accessed by each crawler.

### Reporting

A timestamped CSV report is generated containing:

- User Agent
- AI Flag
- Total Requests
- Unique URL Count
- URLs Visited

---

## Screenshots

### Cloudflare Export

[screenshots\output-screenshot-redacted.png](Cloudflare Export)

### Script Execution

[screenshots\output-screenshot-redacted.png](Script Execution)

### Report Output

[/screenshots/report-output.png] (Report Output)

---

## Repository Structure

cloudflare-ai-crawler-analysis/
│
├── README.md
├── SETUP.md
├── ARCHITECTURE.md
│
├── docs/
│   ├── methodology.md
│   └── screenshots/
│
└── LICENSE


---

## Security Notice

No production code exists within this repository.

The following assets remain private:

- Python source code
- Cloudflare exports
- Generated reports
- Internal analysis findings

This repository serves as documentation only.
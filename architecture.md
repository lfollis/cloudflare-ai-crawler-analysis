# Architecture

## Overview

The AI crawler analysis process transforms Cloudflare firewall event exports into actionable reporting that reveals:

- Which AI assistants accessed the website
- Which URLs were requested
- Request frequency
- Crawl behavior patterns

The implementation resides in a private repository.

---

# High-Level Architecture


Cloudflare Firewall Log &rarr; Json Export &rarr; Parse JSON Records & Validate Data &rarr; Identify Crawlers & Group requests &rarr; Deduplicate URLS & Aggregate Requests &rarr; CSV Export & Analyst Review

---

# Data Flow

Cloudflare &rarr; Firewall Events &rarr; JSON Export &rarr; Private Python Analysis &rarr; User-Agent Mapping &rarr; URL Aggregation &rarr; CSV Reporting &rarr; Analysis

---

# Core Components

## Data Source

### Cloudflare Firewall Events

Primary source of traffic information.

Example fields:
{
  "userAgent": "...",
  "clientRequestPath": "...",
  "clientCountryName": "...",
  "clientASNDescription": "...",
  "datetime": "..."
}

## Ingestion Layer

Responsibilities:

- Read exported JSON files
- Validate records
- Normalize fields
- Prepare structures for analysis

### Inputs

JSON Export

### Outputs

Normalized Event Records

## Classification Layer

Responsibilities:

- Group requests by User Agent
- Flag known AI assistants
- Aggregate request counts

Examples:

DuckAssistBot
GPTBot
ClaudeBot
PerplexityBot
GoogleOther
Google-Extended

---

## URL Analysis Layer

Responsibilities:

- Collect URLs associated with each crawler
- Deduplicate requests
- Calculate unique URL counts

Outputs:

Crawler:
 - URL A
 - URL B
 - URL C

---

## Reporting Layer

Generates analyst-friendly reports containing:

### Metrics

- Total Requests
- Unique URLs
- AI Classification

### Deliverables

Timestamped CSV Report


Example:

ai_agent_url_report_20260101_000101.csv

---

# Repository Scope

This repository focuses on documenation and methodology. Implementation assests are intentionally excluded.

---

# Future Enhancements

Potential areas of expansion:

## ASN Reporting

Track:

- AWS
- Azure
- Google Cloud
- Cloudflare

---

## Geographic Analysis

Track:

- Country
- Region
- City

---

## Crawl Pattern Detection

Detect:

- Repeated URL access
- Path enumeration
- Utility-page discovery

---

## Dashboarding

Potential integration targets:

- Power BI
- Tableau
- Looker Studio
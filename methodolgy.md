# Methodology

## Data Source
Cloudflare firewall event exports were used as the primary source of crawl activity data

## Key Fields
The analysis focuses on:
1. userAgent
2. clientRequestPath
3. clientCountryName
4. clientASNDescription
5. datetime

## Processing Steps

### Step 1
Extract  all user agents from the cloudflare export

### Step 2
Group records by user agent

### Step 3
Create a unique list of URLs visited by each user agent

### Step 4
Generate a CSV report containing:
1. User Agent
2. Total Requests
3. Unique URL Count
4. URLs Visited

## Goals
The Goal of the analysis was to:
1. Understand AI assistant crawl behavior
2. Identify non-standard page access
3. Validate whether utility pages were being requested
4. Review craw distribution across content types
5. Validate analytic anomolies due to bot traffic

## Repository Design
The script itself is intentionally excluded from this repository and maintained separately in a private codebase
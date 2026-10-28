# Cloudflare AI Crawler Analysis

## Overview

This project documents a workflow used to analyze AI assistants, crawlers, and automated agents observed in Cloudflare firewall events.

The workflow was developed to answer the following questions:

- Which AI assistants are accessing website content?
- Which URLs are being requested by each assistant?
- How frequently is each assistant accessing the site?
- Are utility or non-indexable pages being accessed?

## Purpose

As AI assistants continue to crawl and reference website content, understanding crawl behavior has become increasingly important for:

- SEO monitoring
- AI discoverability analysis
- Crawl budget evaluation
- Security investigations
- Analytics validation

## Solution

A Python-based analysis process was developed that:

1. Reads exported Cloudflare firewall events
2. Identifies unique user agents
3. Groups requests by user agent
4. Deduplicates URL requests
5. Produces reporting suitable for further analysis

## Repository Notice

The actual Python script and generated reports reside in a private repository and are not included here.

This public repository exists solely to document the methodology, workflow, and resulting insights.

## Sample Workflow

Cloudflare Export &rarr; JSON Processing &rarr; User-Agent Identification &rarr; URL Grouping &rarr; Reporting
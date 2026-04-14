# SponsorSeek-AI-Agent
SponsorSeek is an autonomous AI agent designed to discover, filter, and prioritise visa-sponsored job opportunities across multiple sources for early-career professionals seeking roles in fields such as Machine Learning, AI, and Data.

The system automates the job search workflow by aggregating listings from structured job APIs and public ATS platforms, applying sponsorship-focused filtering, ranking relevant opportunities, and generating downloadable CSV reports with optional email delivery.

---

## Overview

Searching for visa-sponsored roles manually across multiple job boards is time-consuming, repetitive, and often inconsistent. SponsorSeek was built to reduce that friction by creating an agentic workflow that automates discovery across multiple sources and returns structured, usable results.

This project combines multi-source retrieval, text-based sponsorship classification, deduplication, ranking, CSV generation, and email-based delivery into a modular pipeline designed for future web deployment.

---

## Key Features

- Multi-source job aggregation from:
  - Adzuna API
  - Greenhouse public job boards
  - Lever public job boards
- Sponsorship-focused filtering using rule-based NLP techniques
- Deduplication of repeated listings across sources
- Ranking pipeline to prioritise relevant opportunities
- Clean CSV export for download and reporting
- Email delivery of generated job reports
- Extensible backend design for future UI integration
- Support for user-provided API keys

---

## How It Works

The system follows an agentic workflow:

1. Accepts search inputs such as role, country, experience level, and sponsorship preference
2. Uses user-provided API credentials where required
3. Retrieves jobs from multiple structured sources
4. Normalises and merges job records into a unified schema
5. Applies sponsorship classification using keyword-based filtering
6. Removes duplicates and ranks the results
7. Generates a clean CSV output
8. Optionally sends the report directly to the user’s email

---

## System Architecture

```mermaid
flowchart TD
    A[User Input] --> B[Search Request Builder]
    B --> C[Adzuna API]
    B --> D[Greenhouse Jobs]
    B --> E[Lever Jobs]

    C --> F[Job Aggregator]
    D --> F
    E --> F

    F --> G[Normalisation]
    G --> H[Deduplication]
    H --> I[Sponsorship Classification]
    I --> J[Ranking Engine]
    J --> K[CSV Generator]
    K --> L[Downloadable Report]
    K --> M[Email Delivery]

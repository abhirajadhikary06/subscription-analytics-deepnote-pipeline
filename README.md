<p align="center">
  <img width="7090" height="2043" alt="image" src="https://github.com/user-attachments/assets/396608ab-a698-4c6d-9369-69c86dc51f32" />
</p>

# BigQuery Subscription Analytics Project

This project implements a robust dimensional modeling pipeline within Google BigQuery, designed to transform raw operational data into actionable business intelligence.

## Overview

The `n8n test` project follows a structured data architecture, moving raw ingestion through enrichment and dimensional modeling, ultimately delivering curated metrics for executive reporting and support analysis.

## Google Cloud Services Used

- **BigQuery** — Core data warehouse for storage, transformation, and SQL execution.
- **BigQuery Studio** — Integrated workspace used for query development, pipeline orchestration, and job management.
- **Dataform** — Used to define, document, and schedule data transformation workflows, managing dependencies between tables.
- **Looker Studio** — Connected to the finalized Mart layer for visualizing executive KPIs and support metrics.
- **Cloud Shell** — Used for environment configuration and gcloud CLI management.

## Project Architecture & Workflow

The pipeline is organized into distinct layers to ensure data quality and maintainability:

1. **Raw Layer**: Ingestion of raw source data (e.g., `raw_customer_cases`).
2. **Core/Dimensional Layer**: Standardization into dimensional and fact models (e.g., `dim_customer_core`, `fct_subscription_core`).
3. **Enrichment Layer**: Logic application to merge and refine datasets (e.g., `enriched_customer_case`, `enriched_subscription`).
4. **Mart Layer**: Aggregated, business-ready tables for reporting (e.g., `mart_customer_360`, `mart_product_performance`, `mart_monthly_executive_kpi`, `mart_support_metrics`).

## Key Technical Features

- **Dimensional Modeling**: Implementation of a Star Schema approach with explicit Dim and Fact tables.
- **SQL-based Transformations**: Complex logic encapsulated within reusable, version-controlled scripts.
- **Automated Orchestration**: Scheduled data tasks ensuring datasets like `mart_customer_360` are refreshed automatically.
- **Dependency Management**: Dataform logic ensuring that downstream Mart tables only refresh after upstream Core/Fact tables successfully complete.

## Getting Started

To explore the architecture:

1. Open **BigQuery Studio** in the `lucid-arch-464008-n1` project.
2. Navigate to the **Pipelines** tab to view the dependency graph.
3. Inspect the SQL logic within the `raw`, `dim`, `fct`, and `mart` queries.
4. Open the connected reports in **Looker Studio** to view the live KPIs.

## Project Status

The pipeline is fully operational with active enrichment and mart-level aggregation logic driving business analytics.

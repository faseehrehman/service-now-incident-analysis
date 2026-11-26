# ServiceNow Incident Analysis

## Project Overview

This portfolio project demonstrates how ServiceNow incident data can be analysed in Power BI to understand support demand, incident priorities, affected services, callers and assignment-group workload.

The original analysis was based on approximately 7,910 incident records from 2026. Because the source data relates to a workplace environment, the original dataset is not published. The `data` folder contains a small synthetic sample that demonstrates the intended structure without exposing company, employee, customer or system information.

## Project Objectives

The analysis is designed to answer practical operational questions:

1. How many incidents were raised during the reporting period?
2. Which priorities and statuses account for the highest volumes?
3. Which affected services generate the most support demand?
4. Which anonymised callers raise the most incidents?
5. How is workload distributed across anonymised assignment groups?
6. How does incident demand change over time?
7. Are incidents concentrated among a relatively small number of services?

## Tools Used

- Power BI
- DAX
- Power Query
- Excel
- ServiceNow export data

## Dataset

The original analysis used approximately 7,910 incident rows from 2026. Relevant analytical fields included incident date, status, priority, affected/impacted service, caller and assignment group.

The original organisational dataset is deliberately excluded from this public portfolio. `data/sample_incidents.csv` is synthetic and is provided only to illustrate the expected schema.

## Data Preparation

Before analysis, the workflow should include:

- validating data types, particularly incident dates;
- checking blank and inconsistent category values;
- standardising fields used for grouping and filtering;
- checking for duplicate records where appropriate;
- validating row counts after transformation; and
- reviewing fields for confidential or personally identifiable information before publication.

## Power BI Report

The report is designed with separate overview and deeper-analysis pages rather than placing every visual on a single page.

### Overview

The overview should give a quick picture of overall support demand using headline KPIs and concise breakdowns of status, priority and affected services.

Add a sanitised screenshot here as:

`./screenshots/overview.png`

### Analysis

The analysis page should focus on where demand is concentrated, including affected services, caller volumes, assignment groups and other patterns that warrant further investigation.

Add a sanitised screenshot here as:

`./screenshots/analysis.png`

## DAX

Representative measures and explanations are documented in [`dax/measures.md`](dax/measures.md).

## Analytical Interpretation

The purpose of this project is not simply to identify the largest bar on a chart. High incident volume can indicate an area worth investigating, but it is not by itself evidence that a service is unreliable or that a caller is using a system incorrectly.

Useful follow-up analysis could compare service incident volume with user population, transaction volume, recurring categories and resolution performance.

## Key Findings Structure

When publishing the final portfolio, use evidence from the sanitised report to document findings such as:

- services contributing the greatest share of incident demand;
- the distribution of incidents by priority and status;
- concentrations of workload across assignment groups;
- periods with unusually high or low incident volumes; and
- repeat patterns that could justify root-cause investigation, documentation or automation.

Do not publish findings copied from confidential production data unless they have been approved for public disclosure.

## Limitations

- Incident volume alone does not measure application reliability.
- High-volume services may have larger user populations or transaction volumes.
- Caller volume should not be interpreted as individual performance or behaviour.
- Assignment group data can represent routing rather than the team that ultimately resolved an incident.
- A 2026-only dataset does not establish longer-term trends.
- Additional categorisation and resolution data would support deeper root-cause and service-performance analysis.

## Potential Next Steps

- Analyse resolution time by priority and affected service.
- Identify recurring incident categories.
- Compare incident demand with application user populations.
- Investigate repeat incidents and high-frequency issues.
- Assess whether knowledge articles or automation could reduce common support requests.
- Extend the dataset across multiple years for trend and seasonality analysis.

## Skills Demonstrated

- Power BI report development
- DAX
- Power Query
- Data cleaning and validation
- KPI development
- Operational data analysis
- Data visualisation
- Analytical interpretation
- Business problem solving
- Data confidentiality awareness

## Repository Structure

- `data/` - synthetic example data only
- `dax/` - representative DAX measures and explanations
- `docs/` - methodology and publication guidance
- `screenshots/` - sanitised Power BI screenshots

## Confidentiality

This repository is designed as a public portfolio case study. It must not contain production exports, real employee or customer details, internal URLs, server names, IP addresses, credentials, API keys, connection strings, confidential ticket descriptions or other proprietary information.

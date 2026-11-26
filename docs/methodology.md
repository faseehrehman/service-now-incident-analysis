# Methodology

## 1. Define the analytical questions

The project begins with operational questions rather than chart selection. The focus is support demand: volume, priority, status, affected services, callers, assignment groups and trends.

## 2. Extract and protect the data

The original analysis was performed on a ServiceNow export. The production export must remain outside the public GitHub repository.

For portfolio publication:

- use synthetic or explicitly approved public data;
- anonymise people, groups and services where required;
- remove free-text descriptions that could reveal confidential information;
- remove ticket identifiers when they are not analytically necessary; and
- never publish credentials, URLs, server names, IP addresses or connection information.

## 3. Validate the dataset

Checks should include:

- row count;
- duplicate records;
- blank values;
- appropriate date and numeric data types;
- consistent priority/status categories; and
- expected date range.

The original Power BI work used approximately 7,910 incident rows, so row-count validation is an important control when filters or transformations are introduced.

## 4. Transform for analysis

Power Query can be used to standardise data types and categories before loading the model. Transformations should be documented and kept proportionate to the analytical need.

## 5. Build measures

DAX measures should answer defined business questions. Examples are stored in `../dax/measures.md`.

## 6. Design the report

Keep the overview simple. Separate headline monitoring from deeper investigation.

Suggested structure:

### Overview page
- total incidents;
- status summary;
- priority summary;
- affected-service overview;
- date trend or reporting-period context.

### Analysis page
- affected-service concentration;
- caller analysis using anonymised identities;
- assignment-group workload;
- priority/service combinations;
- supporting explanatory text and findings.

## 7. Interpret carefully

Descriptive analysis identifies patterns, not causes. For example, a service with the largest incident count may also have the largest user base. A caller with many incidents may have a role that naturally requires more support interaction.

Treat these results as evidence for further investigation rather than conclusions about system quality or individual behaviour.

## 8. Communicate findings

A strong portfolio project explains:

1. the question;
2. the method;
3. the result;
4. the limitation; and
5. the next investigation or action.

This demonstrates analytical reasoning rather than only Power BI visual-design ability.

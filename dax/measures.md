# DAX Measures

These are representative measures for documenting the Power BI analysis. Table and column names may need to be adjusted to match the final sanitised model.
# DAX Measures

This section documents some of the key DAX measures used within the Power BI report. The measures support the headline KPIs and provide consistent calculations across the different analytical pages.

## 2026 Total Incidents

Calculates the total number of unique incidents within the dataset using the incident number.

```DAX
2026 Total Incidents =
DISTINCTCOUNT('incidents'[Number])
```

This is the main incident count used throughout the report and acts as the base measure for several other calculations.

## Active Tickets

Calculates the number of incidents currently in an Active state.

```DAX
Active Tickets =
CALCULATE(
    [2026 Total Incidents],
    'incidents'[State] = "Active"
)
```

This measure is used to provide visibility of the current active incident workload and responds to filters applied within the report.

## Closure Rate

Calculates the proportion of total incidents that have been closed.

```DAX
Closure Rate =
DIVIDE(
    [Closed Tickets],
    [2026 Total Incidents]
)
```

The measure provides a simple KPI for understanding how much of the overall incident workload has reached a closed state.

## High Priority

Calculates the number of incidents classified as **2 - High** priority.

```DAX
High Priority =
CALCULATE(
    [2026 Total Incidents],
    'incidents'[Priority] IN {"2 - High"}
)
```

This measure provides visibility of higher-priority demand and helps distinguish more significant incidents from the wider incident population.

## High Critical %

Calculates the proportion of total incidents represented by high and critical incidents.

```DAX
High Critical % =
DIVIDE(
    [High Critical Incidents],
    [2026 Total Incidents],
    0
)
```

This provides additional context to the incident count by showing high and critical demand as a percentage of the overall workload rather than as a standalone number.

## Application High Critical %

Calculates high and critical incidents as a proportion of total incidents within the current report filter context.

```DAX
Application High Critical % =
DIVIDE(
    [High Critical Incidents],
    [2026 Total Incidents],
    0
)
```

This measure is used within the service-level analysis to provide context around the proportion of high and critical incidents when analysing affected services.

## Measure Dependencies

Some of the measures above build on other measures within the Power BI model, including:

- `Closed Tickets`
- `High Critical Incidents`
- `2026 Total Incidents`

Using reusable base measures helps keep calculations consistent throughout the report and allows the results to respond dynamically to report filters and slicers.## Notes

Use measures as analytical tools rather than portfolio filler. For the final repository, retain only measures that are actually used by the published report and explain the business question each one supports.

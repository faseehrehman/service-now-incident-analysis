# DAX Measures

These are representative measures for documenting the Power BI analysis. Table and column names may need to be adjusted to match the final sanitised model.

## Total Incidents

Counts incident rows in the current filter context.

```DAX
Total Incidents =
COUNTROWS(incidents)
```

## Total Incidents Ignoring Filters

Useful as a validation measure when checking why slicers or page filters change headline totals.

```DAX
Total Incidents Ignore Filters =
CALCULATE(
    COUNTROWS(incidents),
    REMOVEFILTERS(incidents)
)
```

## 2026 Total Incidents

Restricts the count to incidents opened in 2026.

```DAX
2026 Total Incidents =
CALCULATE(
    COUNTROWS(incidents),
    YEAR(incidents[Opened Date]) = 2026
)
```

## Open Incidents

Example status measure. Update the status values if the final model uses different labels.

```DAX
Open Incidents =
CALCULATE(
    [Total Incidents],
    incidents[Status] = "Open"
)
```

## Top 3 Application Incidents

Counts incidents for the three highest-volume affected services in the current analytical context.

```DAX
Top 3 Application Incidents =
VAR TopServices =
    TOPN(
        3,
        ALLSELECTED(incidents[Affected/Impacted Service]),
        [Total Incidents],
        DESC
    )
RETURN
    CALCULATE(
        [Total Incidents],
        KEEPFILTERS(TopServices)
    )
```

## Notes

Use measures as analytical tools rather than portfolio filler. For the final repository, retain only measures that are actually used by the published report and explain the business question each one supports.


## select

```
StormEvents
| sort by StartTime desc
| take 10
```

## project

show only some columns

example
```
StormEvents | sort by StartTime desc 
| project StartTime, EndTime, State, EventType, DamageProperty, EpisodeNarrative | take 10
```

zoom in on StormSummary to expand json
```
StormEvents
| sort by StartTime desc
| project StormSummary
| take 10
```

## draw bar chart

summarize: add columns with "group by" operation
where: filter
project: select columns
render: visualization

```
StormEvents
| summarize event_count=count(), mid = avg(BeginLat) by State
| sort by mid
| where event_count > 1800
| project State, event_count
| render columnchart
```

## filter

```
StormEvents
| take 10000
| where StartTime == datetime(2007-01-14T00:35:00Z)
```

## pivot table

Explode column values into new columns.
Use in result UI.


## Search in results

Magnifying glass


## Share query

For "Link, Query, and Results to clipboard", paste in Excel.
## Splunk Search
##### displays all indices and the amount of events associated with each
```sql
| eventcount summarize=false index=* | dedup index | fields index count
```
##### displays total event count per hour for a given index
```sql
| tstats count where index=[YOUR_INDEX] groupby _time span=1h 
```
##### setting a variable to the current hour
```sql
| eval hour=strftime(_time,"%H")
```

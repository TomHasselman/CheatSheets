```sql
//displays all indices and the amount of events associated with each
| eventcount summarize=false index=* | dedup index | fields index count
//displays total event count per hour for a given index
| tstats count where index=[YOUR_INDEX] groupby _time span=1h 
//setting a variable to the current hour
| eval hour=strftime(_time,"%H")
```

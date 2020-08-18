# Calculating a Percentage 
(i.e. variable/ total OR sum(variable)/ total SUM)

## In SQL
(for reference)

ex: (browser page views percentage from the total of pageviews collected)
```
SELECT
  SUM(pageviews) as total,
    pageviews / total as perc
```
    
    
## In Qlik   

ex (percentage of successful projects from the total number of projects)
```
count({$<state={'successful'}>}ID) / count(ID)
```


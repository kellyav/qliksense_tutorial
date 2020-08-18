# Calculating a Percentage 
(i.e. SUM of variable/ total SUM)

## In SQL
(for reference)

ex: (browser page views percentage from the total of pageviews collected)
```
SELECT
  (select SUM(pageviews) as total from pageviews),
    pageviews / total.total 
```
    
    
## In Qlik   

ex (percentage of successful projects from the total number of projects)
```
count({$<state={'successful'}>}ID) / count(ID)
```

- 




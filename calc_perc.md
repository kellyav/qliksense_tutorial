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


- 

Let vSales  = 'Sum(Sales)' ;
Let vSales2  = '=Sum(Sales)' ;

In the second variable, we add an equal sign before the expression. This will cause the variable to be calculated before it is expanded and the expression is evaluated

If you add a dollar-sign expansion and call $(vSales) in the expression, the variable is expanded, and the sum of Sales is displayed.

Finally, if you call $(vSales2), the variable will be calculated before it is expanded. This means that the result displayed is the total sum of Sales. 
The difference between using =$(vSales) and =$(vSales2) as measure expressions is seen in this chart showing the results:

https://help.qlik.com/en-US/sense/September2020/Subsystems/Hub/Content/Sense_Hub/Scripting/work-with-variables-in-data-load-editor.htm

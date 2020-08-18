# Set Analysis in qlik

## Example

- SUM({$<Year={"2025}>}Sales) 

Summarises Sales for the year 2015. Useful KPI chart object for this, 
to diplay 2 KPI charts for the SUM of Sales in 2015, and the sum of sales in 2014. 

Breakdown: 
  - Sum(Sales) -> this outer layer is obvious. takes the sum
  - **{ ... }** -> (i.e. Sum({ ... }Sales) this expression syntax represents a set of conditions 
  for that Sum of Sales. Excludes/ includes data.
    - **Expression Syntax**
      - **{1}** Use all the data, ignoring selections. Measure value for the chart object 
      will not change or update when selections are made in user interface. 
      - **{$}** represents current selections. Will take dimensions on the app you want to 
      filter on into conisderation and the chart value will change.
      based off those current selections
      - **{1-$}** excludes the current selection. 
      i.e. 
```
Sum({$-1<Year={"2015"}>}Sales) excludes Sales from 2015
```
  - **< ... >** -> set modifier. Defines the condition we want our measure to reflect. i.e. 
```
<Year={"2015, 2016"}> or {$<Year={2015}, Country={"Germany"}>}
```
  

Selecting 'France' in one chart typically will change the results of the other charts that have Country (and therefore France) as a variable, to reflect insights on only France. AKA the charts are dependent on variables that are selected in the dashboard (if applicable). 

** This will not happen if a set modifier is defined. AKA if Chart1 has the code: 
```
Sum({$<Country={"Italy"}>}Sales) 
```
then this chart will NOT be affected when the user chooses 'France' in another chart. This means that defining a set modifier in the charts code will lock in that particular category for that chart. 


### Credits/ Sources

- [Beginners' Introduction to Set Analysis - Qlik Sense and QlikView](https://www.youtube.com/watch?time_continue=77&v=YMQJnKMkfxg&feature=emb_title)

- [Natural Sets (community board)](https://community.qlik.com/t5/Qlik-Design-Blog/Natural-Sets/ba-p/1470953)

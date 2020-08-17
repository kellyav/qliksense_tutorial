# Set Analysis in qlik

## Example

- SUM({$<Year={"2025}>}Sales) 

Summarises Sales for the year 2015. Useful KPI chart object for this, 
to diplay 2 KPI charts for the SUM of Sales in 2015, and the sum of sales in 2014. 

Breakdown: 

  - Sum(Sales) -> obv
  - { ... } -> (i.e. Sum({ ... }Sales) this expression syntax represents a set of conditions 
  for that Sum of Sales. Excludes/ includes data.
  
    - **Expression Syntax**
      - {1} Use all the data, ignoring selections. Measure value for the chart object 
      will not change or update when selections are made in user interface. 
      - {$} represents current selections. Will take dimensions on the app you want to 
      filter on into conisderation and the chart value will change.
      based off those current selections
      - {1-$} excludes the current selection. i.e. Sum({$-1<Year={"2015"}>}Sales) excludes Sales from 2015
  - < ... > -> set modifier. Defines the condition we want our measure to reflect. 
    - i.e. <Year={"2015, 2016"}> or {$<Year={2015}, Country={"Germany"}>}
  



### Credits/ Sources

- [Beginners' Introduction to Set Analysis - Qlik Sense and QlikView](https://www.youtube.com/watch?time_continue=77&v=YMQJnKMkfxg&feature=emb_title)

- [Natural Sets (community board)](https://community.qlik.com/t5/Qlik-Design-Blog/Natural-Sets/ba-p/1470953)

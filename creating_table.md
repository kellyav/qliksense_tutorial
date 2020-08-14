# LOAD and Creating Tables

To create a table, 

```
Table1:   // table name
LOAD // loads the columns of the file
  col1,
  col2,
  "col 3" AS "Column 3"
  "col 4" AS Col4

FROM [lib://DataFiles/Sales.xlsx]    // the path *on Qliksense* where you uploaded the excel file
(ooxml, embedded labels, table is [Sales data])   // The name you gave it on the left menu

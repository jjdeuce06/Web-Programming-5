# Web Programming Assignment 5
## Overview
This program kept track of a table of transactions. Each row on the table has a checkbox, transaction number, date,
description, and a transaction amount. There is a total amount that updates with the sum of all transaction amounts
on the table. There are 4 buttons: Add new row, insert row before, insert row after, and delete selected row. This program
introduced concepts of adding and removing nodes, using a date input type, and using a checkbox input type

## HTML and CSS
CSS
- h1 made to color white
- h3 made to color white
- body's background color made green
- table, th, and td have a 1 pixel solid black border with a red background color
- buttons have the font-family of Lucida Handwriting and a background color of yellow

HTML
- title of the webpage set to Project 5
- onload the webpage calls the setTValue() function
- h1 on the table is set to the text, "Transaciton Table"
- table is declared, with id set to "Transaction table"
  - First table row section has headers of Select, Trans #, Date, Description, and Amount
  - Second table row section declares input types for each row (Select has checkbox, Trans # and Description are text, Date is of date type, and amount is a number)
- h3 declared with id "totalvalue", and a label of Total amount: 0.0
- Buttons declared with their function name ("Add New Row", "Insert Row Before", "Insert Row After", "Delete Selected Row")
  - Add new row -> calls genericAdd() function
  - Insert row before -> calls tableinsertBefore() function
  - Insert row after -> calls insertAfter()
  - Delete Selected Row -> calls deleteAfter()

 ## JavaScript
-  Begins with list of global variables that are continuously updated
  - list
  - addlist
  - table
  - checked
  - checkboxes
  - checknext
  - checkednext
  - total (set to value 0.0)
### Functions
- genericAdd()
  - updates table by grabbing the Transaction table using getElementById
  - local avriable new row creates a new tr element
  - newrow's inner HTML is set to the same HTML code used in the second table row section
  - table appends a child of new row
  - a call to setTValue() is made
- tableInsertBefore()
  - updates table by grabbing Transaction table using getElementById
  - sets global checked value to the value returned by our getChecked() function
  - if checked is true, make a local new row with inner HTML value of our second section of table row, and insert the new row before the checked row
  - call to setTValue() is made
- insertAfter()
  - updates table by grabbing Transaction table using getElementByID
  - sets global checkednext to value returned by getCheckedAfter() function
  - if checkednext is true, make a newrow with inner HTML of the the second section of table row, and insert newrow before the checkednext (it will be inserted after)
  - call to setTValue() is made
- deleteAfter()
  - update the table by grabbing Transaction table using getEementByID
  - set global variable checkboxes to an array of all checkboxes using getElementsByClassName with parameter "myCheck"
  - begin a for loop with an integer c set to 0, c will be less than the length of checkboxes, and will increment by 1
    - if the current checkbox is checked, delete the row, call setTvalue() and addTotal()
- getChecked()
  - set global checkboxes to array of all checkboxes using getElementsByClassName with parameter "myCheck"
  - start another for loop with c, c less than the checkboxes length, and incrementing by 1
    - return the row of the first checkbox that is checked
- getCheckedAfter()
  - set global checknext to an array of all checkboxes using getElementsByClassName with parameter "myCheck"
  -  start another for loop with c, c less than the checkboxes length, and incrementing by 1
    - return the row of the first checkbox that is checked
- addTotal()
  - set global addlist to array of all elements of class transactionAmount using getElementsByClassName
  - rese total to 0.0
  - begin a for loop that will sum up all elements of the array addlist
  - set total to a floating point number with one decimal point
  - if the total is greater than 0, set totalValue's inner HTML to "Total amount: " + total using getElementById
  - otherwise, set totalValue's inner HTML to "Total amount: 0.0" using getElementById
- setTValue()
  - update global list to get all transactionum elements using getElementsByClassName
  - start a for loop that will set the current row's value to "___" + parseInt(i+1) + "___" (i+1 to offset array starting at 0)      
  
    

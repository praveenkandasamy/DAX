# Microsoft Power BI: Deep dive into DAX evaluation context - BRK3060
Notes from youtube video
Date - 19/03/2020
link - https://www.youtube.com/watch?v=teYwjHkCEm0

### What is an filter context?
Image : 
![alt text](https://github.com/praveenkandasamy/DAX/blob/master/1.PNG)
* Tuple - Value for a set of columns
* Filter - Table of tuples
* Filter context - Set of filters
        + better to have relational filtering
        +  

### What is an evaluation context?
* Filtering context + row context 
* Row context means that when you write a formula row context is assumed
    + SUMX is the same as SUM - SUMx does the evaluation row by row
                **SUM** ( TABLE[COLUMN] )
                **SUMX** (
                    TABLE,
                    TABLE[COLUMN] 
                )

##### Relationships and filters
* A filter applied automatically propagates to a related table via the relationship
* So  relationship is just a tool to transfer a filter to a table
* Filter directioni has to correct
* Best practice to have one to many



https://github.com/praveenkandasamy/DAX/blob/master/2.PNG



Reference-style: 
![image2][logo]

[logo]: https://github.com/praveenkandasamy/DAX/blob/master/2.PNG "Logo Title Text 2"






# Microsoft Power BI: Deep dive into DAX evaluation context - BRK3060
Notes from youtube video
Date - 19/03/2020
link - https://www.youtube.com/watch?v=teYwjHkCEm0

### What is an filter context?
Image1 : 
<img width="600" height="400" src="https://github.com/praveenkandasamy/DAX/blob/master/1.PNG" />

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

Image1 : 
<img width="600" height="400" src="https://github.com/praveenkandasamy/DAX/blob/master/2.PNG" />

* A filter applied automatically propagates to a related table via the relationship
* So  relationship is just a tool to transfer a filter to a table
* Filter directioni has to correct
* Best practice to have one to many and cross filter direction single
* If you use both be clear on outcome
* Rather than create a bi directional filter use a specific calculation to do this
*  

 ### Base table and expanded table
 * This is for example when you have product category expanded to sales table
 * 


-----------
            Red sales =
            Calculate(
                SUMX(
                    Sales,
                    Sales[Quantity]*Sales[Net Price]
                ),
                Product[Colour] = "Red"
            )
--------

Order in which the formula is evaluated
* Inner filter context
* Outer filter context
* Row context

Insert image 3 below : 
<img width="600" height="400" src="https://github.com/praveenkandasamy/DAX/blob/master/3.PNG" />

    
     
This is how DAX computes a calculate function 
Insert image 4 below : 
<img width="600" height="400" src="https://github.com/praveenkandasamy/DAX/blob/master/4.PNG" />


















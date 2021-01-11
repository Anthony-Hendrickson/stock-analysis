# stock-analysis

##**Overview of Project**

The project was to help Steve analyse stock performance so he can help guide his parents. They invested in DAQO with very little reasearch and Steve wanted to know how the company was performing. We used stockmarket data from 2018 to check the overall return of the stock that year.

Steve liked the analysis so much that we began our assignment to also build a macro to help him do the same analysis for of 12 other stocks.

##**Results**

Unfortunately for Steve's parents, the 2018 performance of the DQ stock was quite poor. DQ experienced a 63% decrease in value over the period. After expanding the scope of our analysis to 12 other stocks we can see that 9 other stocks also experienced a year of poor performance, having depreciated in value of the year.

Below you will see a capture of our analysis of the 12 stocks. Cells highlighted in Red in the "Return" column indicate a negative return. Cells highlighted in Green in the "Return" column indicate a positive return. 

![alt text](https://github.com/Anthony-Hendrickson/stock-analysis/blob/main/2018%20Stock%20Performance%20Data.PNG)

We did the same analysis on 2017 data for the same stocks and saw performance overall was generally far better in this year. In fact, in 2017 DQ doubled its value, compared to losing 63% in 2018. See the capture of our analysis for 2017 below:

![alt text](https://github.com/Anthony-Hendrickson/stock-analysis/blob/main/2017%20Stock%20Performance%20Data.PNG)

When we ran the macro for the 12 stock analysis it ran at a reasonable pace but, if we were to drastically increase the scale of our analysis, we would begin to encounter far slower run times. To future proof our macro against this situation, we refactored the code. Specifically, we replaced a nested loop with some neat array referencing. The original nested loop section is captured below:

![alt text](https://github.com/Anthony-Hendrickson/stock-analysis/blob/main/Original_Loop.PNG)

The refactored code leveraging an array is below:

![alt text](https://github.com/Anthony-Hendrickson/stock-analysis/blob/main/Refactored_Code.PNG)

By using the array instead of the loop we have reduced the number of read throughs that the Macro needs to do overall. The result of the refactoring was a significant decrease in runtime while performing the same analysis. Running the analysis on the 2018 data, we noted that it took 0.7265625 seconds to run:

![alt text](https://github.com/Anthony-Hendrickson/stock-analysis/blob/main/2018%201st%20run.PNG)

After the refactoring we noted that the macro took 0.09375 seconds to run

![alt text](https://github.com/Anthony-Hendrickson/stock-analysis/blob/main/2018%201st%20run%20-%20post%20refactoring%202018.PNG)

This means the macro runs about 8 times faster after refactoring.

##**Summary**

I think that, so long as the scope of our analysis remains small the initial code with the nested loop will serve you fine. I think it actually is easier to follow for a novice (but that might be my own bias) so in that sense the code may actually be more readable to others and it doesn't require any more investment of time. Other than that, there is absolutely no reason not to do it with the array once you understand the concept. The code is shorter, looks cleaner, and takes less time to run while producing the same reuslts.

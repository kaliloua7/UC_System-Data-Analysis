### Kalilou's Workspace
## Project description 



As an international student, the first question that came to mind when exploring the admission data for UC institutions was “what is the admission rate like for international students and where does most of these students come from?”. To answer this question, I would need to compute a cumulative admission rate per year for international schools. Additionally, I am interested in finding out from which international high school does UC admits the most international students? The answer to this question involves computing the total number of admitted students for each high school and sorting them in ascending order. Finally, I would like to plot the yearly admission rates for applicants from international high school from 2016 to 2020. I hope to identify a trend in the observed admission rates over this time period.

To achieve these goals, I will use the FR EN_croostab.csv file that contains the number of students that applied to UC institutions per highschool, the city of the highschool, a breakdown of the number of applications, admissions and enrolment, and an ethnic breakdown as reported by the applicants. Note that this dataframe only shows data for one year, I will therefore have to produce more data frames that correspond to different years.  plotly graph objects to create visualization that illustrate my points and arguments.  


In my initial attempt at working with the data, I encountered multiple issues regarding the process of cleaning up the data. The first hurdle was to figure out the encryption scheme used on the csv file and then I needed to identify the delimiter which was ‘\t’ and finally, I had to omit some lines as they were filled with nonsensical information. I also noticed that the city column for international schools was always set to NaN whereas the city column of US based highschools was non NaN. To verify my assumptions, I needed to prove that the non null list of cities was only filled with US cities. I achieved this by first extracting the list of all the cities in the data frame and then compared it to a list that includes most US city names. After this process, I had to manually verify the list of cities that didn’t have a match in the list of US cities. In the end, I was able to establish that all non na city names were indeed in US territory which would mean that all the internationally based highschools had their city field set to NaN. 



Next, I needed to calculate the cumulative admission rate for international highschools. I did this by computing the total number of applications and then computing the total number of for all international highschools. I used plotly’s graph object to plot a pie chart that displays the percentage of admissions among international highschools. Then, I computed individual admission rates for each international highschool and plotted the data of the 15 highschool from which UC institutions accept the most students in a pie chart. The figure below shows the cumulative admission rate and the top highschools from which most UC institutions select the most international students from. 

{%include_relative Vis\UC_crosstab_2016.csv.html%}

From the figure above, we can see that in 2016, the cumulative admission rate of international highschools is 66.7%. During that year, most international students were admitted from Asian highschools(7 of 15 were in Asia).

The next visualization shows the same metrics for the 2017 year:

{%include_relative Vis\UC_crosstab_2017.csv.html%}

We observed that the CAR (cumulative admission rate) of that year increased to 71.9%. Most international students of that class were also from Asian highschools (6 out 15 were located in Asia)

In 2018, the metrics are as follow:

{%include_relative Vis\UC_crosstab_2018.csv.html%}

The CAR of 2018 decreased to 69.6% with most international students coming from Asian highschools(8 out 15).

The 2019 metrics’ are:

{%include_relative Vis\UC_crosstab_2019.csv.html%}

In 2019, the CAR was 69.8% with most students coming from Asian highschools(8/15) and a fair amount of them are from an European based highschool (4/15).

Finally, the 2020’s metric are the following:

{%include_relative Vis\UC_crosstab_2020.csv.html%}

In 2020, the CAR dropped  to 66.9% with the majority of the students again coming from Asian highschools (9/15 which is the largest block of admitted students from Asia).

To conclude my report on this data, I would like to show this graph that displays the CAR per year for UC institutions. 

{%include_relative Vis\CRA_per_year.csv.html%}

This visualization shows that the CRA has remained more or less the same over the considered time period. On average, about 68% of the applications from international high schools are admitted. One reason as to why this value does not show much variance over the year could be that UC institutions have a cap on the percentage of international students that they can admit in a year. Otherwise, it is quite hard to justify why the CAR hardly fluctuates over the year.


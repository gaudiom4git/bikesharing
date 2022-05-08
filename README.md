# BikeSharing Analysis

## Overview

One of the main objectives of Data Analytics to is to be able to tell a story by showing visualizations that provides answers
to business questions.  This module asked students to analyze bike trip data from a NYC bike rental program to
provide information to investors for a similar program in Des Moines, Iowa.

The analysis required us to read data using Pandas and convert a tripduration field to a datetime data type to be used
as a dimension for use in Tableau Visualizations. 

Tableau is a non-coding tool that will take large amounts of data that students used to plot bike trip data points such as
trip duration, bike checkout dates and times, and rider gender.  Tableau also has the ability to add filters, connect to different
datasources such as an Excel spreadsheet, text files, and databases.

The visualizations help communicate information in a graphical way instead of looking at a bunch of numbers on spreadsheets.  
It is very important for the data scientist to provide the story points needed so that stakeholders can make business
decisions.


## Results

There were 7 Tableau worksheets built (vizzes) that were placed in a single story 

### Checkout Times for Users

This graph plots the number of bikes checked out and trip duration across each hour of the day.  There is a spike in the 0 hour which shows 
that most riders take out the bike in the same hour and have a trip duration of about 20 miinutes.  All subsequent hours have minimal trips compared
to the 0th hour.  If you remove the 0 hour from the filter, the 1st and 2nd hour will show better detail.  

0 hour would normally be 12 midnight, but that is not the time of checkout.  This happened because the trip duration was a datetime 
conversion on the seconds only.  You would have to incorporate the start date in the conversion to get the actual hour.

### Checkout Times by Gender

When we break out the checkout times by gender, we see that there are more male riders than female and unknown riders.  
Male and Female peaks at 5 or 6 minutes.  Both male and female riders seem to follow a similar curve which peaks at 5 or 6 minutes.  
The unknown rider is much more flat and peaks between 7 and 25 minutes.

However, if you only filter on the 2nd hour, you will see that the trip duration is more spreadout across all genders.

### Trips by Weekday Per Hour

This heatmap shows the checkout times by weekday and hour.  Darker shades show heaviest checkout on Thursday evenings
between 5 and 6pm.  Monday thru Thursdays are light between 10 and 3, heavier in the morning at 8am and between 5 and 6pm.  As you get
closer to the weekend checkout times seem to be spread across the day.

### Trips By Gender By Weekday

This heatmap clearly shows that Male subscribers take the most trips across all days.    Thursdays are the heaviest for both male and
female subscribers.  Weekends (Saturday and Sunday) seem to be the heaviest for off the street customers across all genders, especially 
the unknown gender.  We can also conclude that most subscribers will identify male or female gender as the unknown gender is lightest across 
all days.

### Trips where start station and end station are the same

This bar chart is filtered on trips where the start station is the same as the end station.  We can see that Soissons Landing has the 
highest amount of returns to the same station they started.  The number of unknown gender is the highest at this station as well.
Could be helpful to see why Soissons Landing has the most.  

### Trips by Age and Gender

This bar chart shows the age where the number of trips is the highest.  Because there are so many ages, I filtered on the age where the
number of trips is at least 100.  Tableau was giving me a warning to say that there were too many members and since the bar chart
got very small as age became older than 77.   Interestingly, the number of unknown gender peaks at age 53 with 207,638 trips.  Next
highest looks like age 32 at 1028 trips.  Could be that those with unknown gender do not wish to provide an accurate age, so it
defaults to 53.

### Citibike Story

This story shows all of the data visualizations that give investors and idea of who is renting bikes, when they rent bikes, and how
long their trips are.  Planners and investors can interpolate this data and compare demographics in NYC to Des Moines to get a 
better sense on demand for this program.  Questions to ask would include:

* Does the gender ratio of renters support the gender ratio of people that live and work in Des Moines?
* Where and how many stations do we need in Des Moines?
* How many bikes would we need at each station?


* Check out [NYC Citibike Viz](https://public.tableau.com/app/profile/mae.gaudio/viz/CitiBikeTripAnalysis_16519359960670/TripsbyGender) 

## Summary

Basec on the Trips by Age bar chart, we know that riders are generally aged between late 20's and late 50's.  Males in their late 20's and 
early 30's seem to be the most riders.  Trips usually last 5 to 6 minutes.    We see that the busiest station is Soissons Landing as that 
is the station where people start and end at the same station.  Would help to see what businesses or points of interest are around that 
location to help determine where to place a large station in Des Moines.  

We can see using the Trips by Weekday Per Hour heatmap that during the weekday, riders checkout bikes mostly in the morning at 8am
or in the evening between 5 and 6pm.  During the weekends, it is staggerred throughout the day.





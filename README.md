# bikesharing

## Project Overview
Using Tableau to visualize relationships in NYC CitiBike rental data from August, 2019 to inform decision making about potential bike rental service opportunities. 8 visualizations of the data are created using Tableau and published on Tableau Public in the form of a Story. The Tableau Story can be viewed here : [NYC CitiBike Analysis](https://public.tableau.com/views/NYC_Citibike_Challenge_16679167714460/NYCCitibike?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link "link to dashboard")

### Resources
- Data Source: "Resources/201908-citibike-tripdata.csv" retrieved from https://s3.amazonaws.com/tripdata/index.html
- Software : Tableau Public 22.3, VS Code v1.71.2, Python 3.7, Pandas 1.3.5

## Results
To begin we loaded the data into a Jupyter Notebook and utilized Pandas to convert the tripduration in the dataset from seconds to a datetime format from its original int64 datatype. This conversion is necessary to create the checktime visualizations in the story. The conversion is added as an additional column, and the tripduration column is kept for use in other visualizations. Once the conversion is completed the data is exported to a new csv file.


The data is then loaded into Tableau to begin creating our story.

The first viz created shows the trip durations for all rides broken down by hour and then minutes.

![checktime_users](https://github.com/Jforbus/bikesharing/blob/main/Resources/checktime_users.png)

The chart is filterable based on the hours of duration, and plots a line showing the number of rides at each duration.
This line graph clearly shows that the vast majority of rides are less than half an hour long, with most lasting less than 20 minutes.


Next, we break down the users by gender to develop our picture of the user demographic.

![gender_brk](https://github.com/Jforbus/bikesharing/blob/main/Resources/gender_brk.png)

The pie chart created here shows the 3 gender groups found in the data: Male, Female, and Unkown. Males make up 2/3 of the users in the dataset. Females account for just a 1/4, with the remainder made up of unknowns.


Then we recreate the checktime line graph, this time broken down by gender.

![checktime_gndr](https://github.com/Jforbus/bikesharing/blob/main/Resources/checktime_gndr.png)

The graph appears much like before, but with each gender represented by a different color. Here we see that each gender group holds to the prior trend line, with the majority of trips being under 30 minutes. Unknowns may take slightly longer trips, but not by a large amount.


Next, we use a heatmap to visualize the Usertypes(Customer, Subscriber) and their usage rates across the days of the weeks, broken down by gender.

![trip_user_gnder](https://github.com/Jforbus/bikesharing/blob/main/Resources/trip_user_gnder.png)

This chart uses color to show higher and lower usage rates based on usertype, gender, and day of the week. The darker the color, the higher number of rentals are found in that timeslot for that particular group. The heatmap shows an interesting contrast that may reveal some user demographic information. The largest user group is Subscribers, and their usage is heavily concentrated in the weekdays(Mon-Fri). We also see that Unknown genders are more likely to be Customers rather than subscribers, and their usage is higher on the weekends(Sat-Sun). This visualization leads us to ask some additional questions that may reveal important information. Are short term customers less likely to provide complete information at the time of rental? Do subscribers tend to be those that live and work in the area?


The next viz created is a heatmap to display usage rates over the days of the week broken down by the hour of the day.

![trip_wkdy_hr](https://github.com/Jforbus/bikesharing/blob/main/Resources/trip_wkdy_hr.png)

As before this heatmap uses color to show which days of the week and at which hours the bikes are being rented. This chart adds further information to the types of uses the bikes are seeing. During the weekdays usage is heavily concentrated in the morning and evening, specifically 7-9 am and 5-7pm. These are commuting hours. On the weekends the usage is more spreadout out across the daytime hours.

Next we break down our usage time heatmap by gender.

![trip_wkdy_hr_gndr](https://github.com/Jforbus/bikesharing/blob/main/Resources/trip_wkdy_hr_gndr.png)

This chart is identical to the one above, except further broken down by gender. This expands the picture from before, and confirms some prior guesses. We see the weekday concentration at the morning and evening hours in both the Male and Female groups, with the Unknowns showing no concentration at these times, and a slightly higher increase on the weekend daytime hours. This may suggest that the majority of the users in this dataset are Male commuters who subscribe to the service, followed by Female subscribing commuters. The Unknowns are likely tourists who provide incomplete information at the time of rental, and do not subscribe. This would explain their increased usage rate on the weekends.

Our last two charts show the trip durations and trip counts based on the birth year of the user.

![tripdur_age](https://github.com/Jforbus/bikesharing/blob/main/Resources/tripdur_age.png)

![tripcnt_age](https://github.com/Jforbus/bikesharing/blob/main/Resources/tripcnt_age.png)

A line graph is presented for each that plots the Average Trip Duration, and Number of rentals based on the birth year of the user. In the first graph we can clearly see that younger users tend to take longer trips, as expected. The second line chart reveals that a higher usage rate exists in the 20-40 age group. This supports our prior supposition of male and female commuters making up the majority of the users in the data.

## Summary
Overall these visualizations reveal several key points about the data. First we note that the majority of rentals are for short periods of time, less than half an hour. Next we see that Males make up the majority of the bike rentals. Subscribers are represented in much larger numbers than Customers, and usage rates are much higher during the week, specifically at commuting times, rather than on the weekends. This analysis suggests that the largest user demographic may be Males aged 20-40 who subscribe to the service for commuting, followed distantly by Female Subscribers. 

Two additional visualations that could provide more information about this data are:

- An Area chart showing Usertype by Birth Year: To see if certain age groups are more likely to be subscribers.
- A Packed Bubble Route showing Starting and Ending station names: To visualize which routes are most popular. 

# Independent Project

link to Tableau Public: https://public.tableau.com/profile/hariz.hisham#!/vizhome/seond_checkpoint/Dashboard1

## 1. Collecting the data

To replicate these visualizations, you will first need to download the datasets. Click on the links below:

* [Ward data](https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Ward-Offices/htai-wnw4/data)
* [Speed camera violation data](https://data.cityofchicago.org/Transportation/Speed-Camera-Violations/hhkd-xvj4/data)
* [Chicago public school locations data](https://data.cityofchicago.org/Education/Chicago-Public-Schools-School-Locations-SY1819/8vyn-k2j3)

Once you've clicked on these links, click on the export button and save each file as a .csv file.

## 2. Consolidating data

Time to fire up Tableau Desktop. Be sure to have the most recent version of Tableau installed on your machine. I created these visualizations using Tableau Desktop v2019.3.

Start with Speed Camera Violations dataset. Load the speed camera violations into Tableau. Next, drag and drop the ward offices dataset into the same space. when prompted, join the two tables using an 'Inner Join', with Wards = Ward. 

<img src="images/first_join.PNG" width = "500" >

Next, drag the school location dataset and do the same thing. However, this time use a 'Left Join' with Zipcode = ZIPCODE instead.

<img src="images/second_join.PNG" width = "500" >

Now, we're ready to visualize.

## 3. Visualize data

<img src="images/downward.PNG" width = "800" >

The first chart uses only two attributes - average violations per camera and date. Since the chart uses only two attributes, it is a fairly simple chart to digest. Since there is no differentiating factor between each data point, a consistent color throughout the chart makes it easy to read. 

The title of the chart says what the chart is intending to show - that there is an overall downward trend for violation recordings. However, having only the scatterplot points would not have easily shown the downward trend, overlaying Tableau's trend line helps to visualize the decrease over time. Additionally, using vertical gridlines have helped to differentiate onto which time segments the scatterplot falls. 

This chart gives the reader a good overview of the current state of speed camera violations in the city of Chicago relative to how it was 4 years ago. It is likely that the city's new traffic inititive "Vision Zero" has resulted in more speed cameras being installed around schools and parks [1]. Given this information, the downward trend is quite expected, as more speed cameras being installed might mean a lower proportion of cameras capturing speed violations, or that drivers behavior have changed due to knowing more speed cameras are installed.

<img src="images/neighborhood.PNG" width = "800" >

For the second visualization, an attempt to quantify speed camera violations per neighborhood was made. The rationale behind this was to see where most speed camera violations were concentrated. However, a visualization with only zipcode and average violations would not have been particularly useful - after all, what is a zipcode but a way to divide a city?

This is where the ward and school location datasets came useful. The ward dataset was used to bridge the speed camera violations dataset with the school location dataset. Then, the number of schools for each zipcode were calculated. Next, the following formula was used to calculate what we will call the "Negative Social Impact" (NSI) score:

No. of violations * log(No. of schools)

The rationale behind this formula is that zipcodes with more schools AND higher numbers of speed camera violations would be punished by the score, since it is a safety hazard to people within that zipcode.

Given that, the bar chart produced is rather simple in design. We end up with a chart with only two attributes, and some high-school level math under the hood. The y-axis is ordered according to which zipcode has the highest NSI score, making it easy for the reader to pick out which zipcodes to focus on. The x-axis shows the average NSI score for those zipcodes, so there might be some bias to zipcodes that have abnormally large spikes in violations, but taking the sum or count would not have made any more sense.

The caption below the visualization helps the reader understand the math going on behind the scenes. The interpretation however, can be debated since there are many other ways to manipulate the math to punish areas with more schools and more violations.

This chart gives a good snapshot and interpretation on how speed violations might negatively affect neighborhoods with a high concentration of schools. More school zones mean that more children are exposed to traffic safety hazards. This hazard is further compounded if those schools are within close proximity of roads where drivers tend to drive above the speed limit. As such, a program like that mentioned in [1] would help deter drivers from driving dangerously.

<img src="images/zips.PNG" width = "800" >

For the final visualization, it would be useful to see how each of these Zipcodes are performing in terms of speed camera violations over time. 

## References

[1] Wisniewski, Mary. "City will add speed cameras near 3 schools, 2 parks this summer." Chicago Tribue. 3 July 2018. https://www.chicagotribune.com/news/ct-biz-speed-cameras-20180703-story.html

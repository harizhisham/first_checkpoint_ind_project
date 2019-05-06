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

## References

[1] Wisniewski, Mary. "City will add speed cameras near 3 schools, 2 parks this summer." Chicago Tribue. 3 July 2018. https://www.chicagotribune.com/news/ct-biz-speed-cameras-20180703-story.html

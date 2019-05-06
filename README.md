# Independent Project

link to Tableau Public: https://public.tableau.com/profile/hariz.hisham#!/vizhome/first_checkpoint/calculatedfield

## 1. Collecting the data

To replicate these visualizations, you will first need to download the datasets. Click on the links below:

* [Ward data](https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Ward-Offices/htai-wnw4/data)
* [Speed camera violation data](https://data.cityofchicago.org/Transportation/Speed-Camera-Violations/hhkd-xvj4/data)
* [Chicago public school locations data](https://data.cityofchicago.org/Education/Chicago-Public-Schools-School-Locations-SY1819/8vyn-k2j3)

Once you've clicked on these links, click on the export button and save each file as a .csv file.

## 2. Consolidating data

Time to fire up Tableau Desktop. Be sure to have the most recent version of Tableau installed on your machine. I created these visualizations using Tableau Desktop v2019.3.

Start with Speed Camera Violations dataset. Load the speed camera violations into Tableau. Next, drag and drop the ward offices dataset into the same space. when prompted, join the two tables using an 'Inner Join', with Wards = Ward. 

![](images/first_join.PNG)

Next, drag the school location dataset and do the same thing. However, this time use a 'Left Join' with Zipcode = ZIPCODE instead.

![](images/second_join.PNG)

Now, we're ready to visualize.

## 3. Visualize data


This website is my Master's Project for the MS Data Journalism program at Columbia University. You can access the story [here](https://itsliuhongyu.github.io/MasterProject/). Below are some explanations of how and where I gathered data and information.

## 1. Hurricane Ida Precipitation Map:

The original data were kindly offered by the Office of New Jersey State Climatologist, which shows the accumulated precipitation from Sept. 1, 2021, to Sept. 2, 2021. 

Using QGIS, 
1. I plotted the location of these observatories using the latitude and longitude.
2. Then, I created a triangle shape on each of these data points and defined the height of these triangles being the accumulated precipitation.
3. Next step, I let all the triangles with a data more than 9 inches purple, while keeping the rest blue.

## 2. Hurricane Ida flooding Map:

I cannot find any official map indicating which region saw the most severe flood, so I decided to use peripheral data to create an estimate. The [OpenFEMA Dataset: Individuals and Households Program - Valid Registrations - v1](https://www.fema.gov/openfema-data-page/individuals-and-households-program-valid-registrations-v1) provides information regarding all individuals who noticed FEMA about their home being flooded, and that they need housing assistance. The dataset specifies the locations of these reports to the zipcode level, and recorded the flood depth of each households in inches.

With the data provided, using Python,
1. I filtered the data so that all the reports are reported to be in New Jersey, and the incident code is 4611, FEMA's disaster code for Hurricane Ida.
2. Grouped by zipcode, I calculated the average flood depth reported by each of these reports. To be noted, this chart is just an estimation of the flood depth, as the FEMA dataset might be incomplete, and some households might lived in the same building, hence resulting in data redundancy. Also, there's no way to verify the accuracy of each report.

Then, using QGIS,
1. I created a color scheme from white to blue, and assigned the individual color based on the average flood depth I calculated.

## 3. Flooded area in Manville:

The map was kindly offered by Cleighton Smith, Manville's flood plain manager. I exported the original shapefile into Illustrator and reformated it.

## 4. FEMA Floodplain Map for Manville and Highland Park:

The map can be directly downloaded from [FEMA](https://msc.fema.gov/portal/home). 

Then, using Illustrator,
1. I recolored the regulatory floodway to blue, 100 year flood plain to red, and 500 year flood plain to yellow.
2. Then, I overlayed the mapshape over a Google Map satellite image, and added captions.

---
title: "Automating Existing Conditions Analysis: One City a Time"
date: 2023-01-01
published: true
tags: [python, geopandas, dash, dataviz, folium]
excerpt: "A Python data pipeline script to streamline various urban analyses. Tech stack includes Python, GeoPandas, Dash, ACS API, and Notebook."
folium-loader:
  folium-chart-1: ["charts/Total Population.html", "400"] # second argument is the height
  folium-chart-2: ["charts/Median Age.html", "400"] 
  folium-chart-3: ["charts/pct Total- White Alone.html", "400"] 
  folium-chart-4: ["charts/pct Total- Black Or African American Alone.html", "400"] 
  folium-chart-5: ["charts/pct Total- Asian Alone.html", "400"] 
  folium-chart-6: ["charts/pct Total- Hispanic Or Latino.html", "400"] 
  folium-chart-7: ["charts/Average Household Size.html", "400"]
  
  folium-chart-8: ["charts/pct Total- Bachelor'S Degree.html", "400"]
  folium-chart-9: ["charts/pct Total- Master'S Degree.html", "400"]

  folium-chart-10: ["charts/lu_treemapchart_2.html", "600"]
  folium-chart-11: ["charts/lu_barchart.html", "400"]

  folium-chart-18: ["charts/Median Year Structure Built.html", "400"]
  folium-chart-12: ["charts/Median Gross Rent.html", "400"]
  folium-chart-13: ["charts/Median Monthly Housing Costs.html", "400"]

  folium-chart-14: ["charts/pct Total- Car Truck Or Van- Drove Alone.html", "400"]
  folium-chart-15: ["charts/pct Total- Public Transportation (Excluding Taxicab).html", "400"]
  folium-chart-16: ["charts/pct Total- Bicycle.html", "400"]
  folium-chart-17: ["charts/pct Total- Walked.html", "400"]
  

toc: true
toc_sticky: true
---

This post shows an examples of an automated workflow from data processing, analysis and visualization that focuses on inspecting the current status of the City of Oakland, California, USA. The author developed a python script within Jupyter Notebook that gathers the data from publicly accessible API data points and generates interactive visualizations including tables, charts, and maps with [Plotly](https://plotly.com/) and [Folium](https://github.com/python-visualization/folium). This brief report firstly demonstrates the potential benefits this workflow brings about at scale and some of the key insights the analysis unveils regarding urban planning and policy making. Then, it introduces the major components of the developed Python Script.

# The Quick Snapshot of a City
## Where is the City of Oakland?
Oakland sits to the east of san Francisco across the bay. Below are two maps showing the City's location and street network, as well as its land cover from aerial photograph:
![street map](/assets/images/basemap-6.png)
![aerial map](/assets/images/aerial_map.png)

## Who live in the City?
The City of <b>Oakland</b> has a total population of 437,548 based on ACS 2017-2021 5 years estimate. 
<div id="folium-chart-1"></div> 
The median age of Oaklanders is 36.9, slightly younger than that of the California median age, and younger than the Alameda County overall.
<div id="folium-chart-2"></div>
Oakland has a diverse population. Among the population, 33.4% are White alone, much lower than the share in the state overall. 22% Oaklanders are Black or African Americans, and 15.7% are of Asian races, followed by other races and two or more races.
<div id="folium-chart-3"></div>
<div id="folium-chart-4"></div>
<div id="folium-chart-5"></div>
Currently 27.2% of Oaklanders have Hispanic or Latino origin, higher than that of the Alameda County, but lower than that of the State's overall share.
<div id="folium-chart-6"></div>

The average household size of Oakland is 2.6 people, which is smaller than the State average. 
<div id="folium-chart-7"></div>
It is coexisted with a higher percentage of population with higher education. 26.9% of Oaklanders have obtained a Bachelor's Degree, and 13.9% have a Master's Degree, compared to 21.9% and 9.1% of the State levels.
<div id="folium-chart-8"></div>
<div id="folium-chart-9"></div>


## What Uses are in the City?
The City encompasses various land uses, from residential to commercial and industrial. Below is a chart showing the breakdown land uses from the most general category to the more granular uses. Hover over the chart to see detailed acreages by land use type.
<div id="folium-chart-10"></div>
A different way to look at this is the bar chart below. Except waterbody, which is due to the fact that the City Limits extend over the SF bay, residential uses is the main land use in the City, followed by open space, civic/institutional and then transportation.
<div id="folium-chart-11"></div>

### Existing Land Use Map
Below is an overall map showing the various uses' distribution. Indeed most of the City area is covered by residential uses.
![exlu map](/assets/images/Existing Land Use Category (L1).png | width=600)

## How much does it cost to live here?
As a City that dates its history back to the mid-19th century, Oakland's housing stock is generally older than that of the Alameda County and State of California overall.
<div id="folium-chart-18"></div> 
As a middle-sized city, Oakland has a lot to offer in terms of housing. However, Oaklanders also face considerably rising housing costs, something that has been commonly experienced throughout California.
<div id="folium-chart-12"></div>
<div id="folium-chart-13"></div>

#### Median Monthly Housing Costs
![med housing costs map](/assets/images/tract-Median Monthly Housing Costs.png)
#### Median Household Income
![med income map](/assets/images/tract-Median Household Income In The Past 12 Months (In 2021 Inflation-Adjusted Dollars).png)


### Where is the most/least affordable neighborhood?
The City's housing cost can range largely from average to very expensive levels, depending on locations. Below is a map of the median gross rent per month across different neighborhoods in the City. Places with better transportation access, such as Downtown Oakland and the border area with Emeryville, generally show up with higher rent, while central and east Oakland along the industrial corridor generally are more affordable to rent.
![med rent map](/assets/images/tract-Median Gross Rent.png)
Comparing the above map with the below map of median home value, it is also observable that the traditionally wealthy neighborhoods on the hills have much higher property values. 

![home val map](/assets/images/tract-Median Value (Dollars).png)
It is also evident in the below map to see that the percentage of people living in poverty is reversely correlated with the property values.
![poverty map](/assets/images/tract-pct Total- Income In The Past 12 Months Below Poverty Level.png)

## How do people ger around?
The City encompasses various ways of mobility options, from driving on the City's highways and roads, taking public transportation, and biking or walking.
<div id="folium-chart-14"></div>
<div id="folium-chart-15"></div>
<div id="folium-chart-16"></div>
<div id="folium-chart-17"></div>

### Measuring Walkability
Intersection density has been used as a proxy metric to measure the walkability of a place. Below is a map visualizing this in space:
![int dens map](/assets/images/intersecti.png)

## Other Existing Condition Maps
![year built map](/assets/images/tract-Median Year Structure Built.png)
![DU map](/assets/images/du per ac.png)
![FAR map](/assets/images/FAR.png)
![job dens map](/assets/images/emp per ac.png)


# The Python Script
Following are some code snippets that correspond to each major steps in this automated data pipeline script.

## Data Fetching via APIs
```python
def print_message(message):
  print(message)

print_message("Request data via APIs")
```

## Charting via Dash and Plotly
```python
def print_message(message):
  print(message)

print_message("Making interactive charts")
```
## Geospatial Mapping via GeoPandas

```python
def print_message(message):
  print(message)

print_message("Making maps")
```
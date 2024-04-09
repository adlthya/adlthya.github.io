---
name: Illinois Buildings Visualization
tools: [Python, HTML, vega-lite]
image: assets/pngs/buildings.png
description: This visualization uses vega-lite to analyze buildings in Illinois. 
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Visualization

<vegachart schema-url="{{ site.baseurl }}/assets/json/buildings.json" style="width: 100%"></vegachart>


## Write-up

The scatter plot displays the square footage of buildings in five Illinois cities with the greatest total square footage (namely Chicago, Springfield, Carbondale, Urbana, and Champaign). 
For this chart, I chose to represent the year of construction on the x-axis and the square footage on the y-axis. Each point represents a building. 
I made several specific encoding choices. For one, I decided to restrict the domain of the x-axis from the year 1750 to 2020, as there are no buildings constructed before 1750. Furthermore, on the y-axis, I chose to use a logarithmic scale, as this would prevent data from clumping near the bottom right of the chart. In terms of color, the color of each data point corresponds to the city it is in. I decided to stick with the default colorway. 

The bar chart shows the count of buildings in each of the cities. I chose to encode the city name on the x-axis and the building count on the y-axis. The colors are the same as the scatter plot, with each color representing a specific city. 

In terms of interactivity, I wanted to find a way to link the two charts in a useful and intuitive manner. To accomplish this, I used the selection interval feature and added it as a parameter to the scatter plot. I then used the transform filter function to link the user's selection of the scatter plot to the bar chart. The effect of this is that the user can see the count of buildings in each city based on the selected years and square footage. The interactivity enables the user to see, for instance, buildings that are greater than 100,000 sqft, or buildings built prior to the year 1850. 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/adlthya/adlthya.github.io/blob/main/python_notebooks/Workbook.ipynb" text="The Analysis" %}
</div>


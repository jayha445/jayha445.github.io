---
name: Illinois State Buildings
tools: [Python, HTML, vega-lite]
image: assets/pngs/illinois.jpg
description: HW 5
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


## Illinois State Buildings

I went with the dataset at https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv to focus on what agencies have the most building space and to examine how the build date of buildings differ depending on the usage type.

### Which agencies have the most building space?

<vegachart schema-url="/assets/json/agency_sqft.json" style="width: 100%"></vegachart>

The bar chart shows teh total square footage of buildings owned by the top 10 agencies by space owned. I used quantitative encoding on the x axis and nominal encoding on the y axis, sorted from largest to smallest. I only went with one color as there's only one variable. I replaced square footage values of 0 wit NaN as they were hidden missing values and didn't want them to falsely affect the chart, and I only went with the top 10 largest agencies as I thought going beyond that would be too much and not as relevant to the question of which agencies own the most. 

### What types of buildings were built when?

<vegachart schema-url="/assets/json/usage_decades.json" style="width: 100%"></vegachart>

For my second chart I thought it would be interesting to see how the build date of buildings can differ depending on what usage case they were built for. The left chart shows the number of buildings per usage type and allows you to click to select what usage type to view for the right chart. The chart on the right shows the number of buildings for the selected usage type sorted by which decade they were built in. I sorted each build year by decade by dropping the one's place, so 1999 would count as 1990. Once I made the charts I also found that it gave greater insight into what types of buildings were deemed necessary to build in what decade, and the increases and decreases in the trajectory of how many of each type of building were built. I used nominal encoding for usage type and quantitative for number of buildings for the left chart. For the right chart I used ordinal for the decades as they have an order, and number of buildings as quantitiative. I used the hexcolor #417548 because it's one of my favorite shades of green and a nice neutral color and light gray for the unselected bars to differentiate and signify that they were not being used. I again replaced 0 with NaN and then dropped the rows.

I chose the interactivity option of clicking a building type for the left chart. Clicking a usage type selects it and affects what usage type is shown for the right chart. A double click resets and unselects. I thought this would ne useful as it makes it easy to compare when different types of buildings were built and how some buildings saw a surge in the number built as time goes on and some drop off.

## Search The Data & Methods

<div class="left">
<a class="m-1 btn btn-outline-primary btn-2 " href="https://github.com/UIUC-iSchool-DataViz/is445_data/blob/main/building_inventory.csv">
  The Data
</a>
</div>

<div class="right">
<a class="m-1 btn btn-outline-primary btn-2 " href="https://github.com/jayha445/jayha445.github.io/blob/main/python_notebooks/hw5notebook.ipynb">
  The Analysis
</a>
</div>
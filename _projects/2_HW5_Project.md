---
name: HW5 Project
tools: [Python, HTML, altair, Vega-Lite]
image: assets/pngs/building_inventory.png
description: This project showcases interactive visualizations based on the building_inventory.csv dataset using Altair for advanced interactivity!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Building Inventory Interactive Visualization

This project uses the building_inventory.csv dataset to create a set of advanced interactive visualizations. Using Altair, which outputs Vega-Lite JSON specifications, we constructed two linked interactive views that go well beyond basic pan and zoom.

## Visualization 1: Stacked Bar Chart by County and Building Status
- The first visualization presents the number of buildings by county, categorized by building status (e.g., Abandoned, In Progress, In Use). 
- The design choice of a stacked bar chart allows for easy comparison between counties and clear visualization of status composition within each county. I encoded counties along the x-axis as nominal data and the building count on the y-axis as quantitative data. The building statuses are color-coded using a categorical color scheme to distinctly highlight differences. 
- Data preprocessing included converting relevant numeric columns, such as "Year Acquired," into numerical types and removing rows with missing values.

For interactivity, this chart includes two interactive filters: a year slider and a county dropdown menu. The "Starting Year" slider allows the viewer to dynamically filter the buildings acquired after a selected year, enhancing exploration through temporal dimensions. The county dropdown provides further granularity, letting the viewer focus on data from specific counties or view data from all counties simultaneously. These interactive components significantly enrich the analytical depth of the visualization.

<vegachart schema-url="{{ site.baseurl }}/assets/json/bar_chart.json" style="width: 100%"></vegachart>

## Visualization 2: Linked Scatter Plot and Bar Chart

- The second visualization features a linked scatter plot and bar chart to explore relationships between floors above grade, floors below grade, and building usage. 
- The scatter plot displays "Floors Above Grade" versus "Floors Below Grade," with each point representing a building. Point sizes are scaled according to "Square Footage," providing a quick visual indicator of building size, and colors are assigned based on "Usage Description," utilizing a qualitative color palette for clarity and ease of differentiation.

Interactivity in this visualization is provided through brushing (interval selection). Users can select areas on the scatter plot, dynamically updating the adjacent bar chart, which shows the distribution of selected buildings by their building status. This interactive linkage between the scatter and bar charts enables deeper data exploration and facilitates identifying patterns or anomalies within specific subsets of the data.

<vegachart schema-url="{{ site.baseurl }}/assets/json/linked_view.json" style="width: 100%"></vegachart>



<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/Jiaxin0303/Jiaxin0303.github.io/blob/main/python_notebooks/HW5.ipynb" text="The Analysis" %}
</div>

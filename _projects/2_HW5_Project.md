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

The first visualization is a stacked bar chart with a year slider. In this chart, the horizontal axis represents the county, and the vertical axis shows the number of buildings. The data is further split by building status (Bldg Status) using color. Users can adjust the slider to filter out buildings acquired before a selected year, allowing an in-depth exploration of building acquisition over time.

<vegachart schema-url="{{ site.baseurl }}/assets/json/bar_chart.json" style="width: 100%"></vegachart>

The second visualization is a linked view that combines:

- A scatter plot showing building characteristics – with "Floors Above Grade" on the x-axis, "Floors Below Grade" on the y-axis, point size indicating "Square Footage" and color representing "Usage Description".

- A bar chart that dynamically updates based on an interval brush selection on the scatter plot, presenting the distribution of building statuses (Bldg Status) within the selected region.

These interactive features—implemented via parameter binding for the slider and brush selection for the linked view—enable a more insightful exploration of the multi-dimensional building inventory data.

<vegachart schema-url="{{ site.baseurl }}/assets/json/linked_view.json" style="width: 100%"></vegachart>




## Search The Data & Methods

Below is where we can put some links to both the data and the analysis code as buttons:

```
<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://blog.4dcu.be/programming/2021/05/03/Interactive-Visualizations.html" text="The Analysis" %}
</div>
```

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>

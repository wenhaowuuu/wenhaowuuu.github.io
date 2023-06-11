---
title: "Predicting Customer Behavior with SVM Classification"
date: 2022-12-07
published: true
tags: [dataviz, folium]
excerpt: "Understanding what's it like living in any given city within seconds."
folium-loader:
  folium-chart-1: ["charts/Median Age.html", "400"] # second argument is the height
  folium-chart-2: ["charts/Median Gross Rent.html", "400"]
  folium-chart-3: ["charts/lu_treemapchart_2.html", "600"]
  folium-chart-4: ["charts/Average Household Size.html", "400"]

toc: true
toc_sticky: true
---

This post shows an examples of an automated workflow from data processing, analysis and visualization that focuses on inspecting the current status of the City of Oakland, California, USA. The author developed a python script within Jupyter Notebook that gathers the data and generates interactive visualizations including tables, charts, and maps with Plotly and [Folium](https://github.com/python-visualization/folium). This brief report demonstrates the potential benefits this workflow brings about at scale and some of the key insights the analysis unveils regarding urban planning and policy making.

## The Quick Snapshot of a City

The City of <b>Oakland</b> has a total population of xx.
The average household size of Oakland is xx.

<div id="folium-chart-4"></div>

<div id="folium-chart-1"></div>

## Percentage of Households without Internet

<div id="folium-chart-2"></div>

## What Uses are in the City?

The City encompasses various land uses, from residential to commercial and industrial. Below is a chart showing the breakdown land uses from the most general category to the more granular uses.

<div id="folium-chart-3"></div>

See the [lecture 9B slides](https://musa-550-fall-2020.github.io/slides/lecture-9B.html) and the [lecture 10A slides](https://musa-550-fall-2020.github.io/slides/lecture-10A.html) for the code that produced these plots.

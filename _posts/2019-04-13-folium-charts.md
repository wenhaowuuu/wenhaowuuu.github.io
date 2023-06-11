---
title: "Example: Embedding Folium charts"
date: 2019-04-13
published: true
tags: [dataviz, folium]
excerpt: "Embedding interactive Folium charts on static pages using Jekyll."
folium-loader:
  folium-chart-1: ["charts/foliumChart.html", "400"] # second argument is the height
  folium-chart-2: ["charts/percent_no_internet.html", "400"] # second argument is the height
toc: true
toc_sticky: true
---

This post will show examples of embedding interactive maps produced using [Folium](https://github.com/python-visualization/folium).

## OSMnx and Street Networks

The shortest route between the Art Museum and the Liberty Bell:

<div id="folium-chart-1"></div>

## Percentage of Households without Internet

<div id="folium-chart-2"></div>

See the [lecture 9B slides](https://musa-550-fall-2020.github.io/slides/lecture-9B.html) and the [lecture 10A slides](https://musa-550-fall-2020.github.io/slides/lecture-10A.html) for the code that produced these plots.

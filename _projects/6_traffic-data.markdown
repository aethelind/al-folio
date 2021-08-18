---
layout: page
title: 🚦 Ottawa Traffic Accidents # Data Mart
description: >
    Combined Ottawa traffic collision data with environment Canada's hourly weather data in order to create a data warehouse. Then, we explored the interplay between weather and traffic accidents, assessing various trends. 
#Based on the data, the most accident prone intersection is the roundabout at St. Joseph Blvd. and Jeanne D'arc Blvd.

stack: SQL, Regex, data analysis concepts, OLAP 
demo: 
repo: 
presentation: /assets/pdf/ottawa-traffic-data-mart.pdf
img: /assets/img/traffic-data.png
importance: 6
category: work
---

## Introduction
This project was completed for CSI4142 (Introduction to Data Science) in a team of 2. 

The City of Ottawa maintains [details of traffic accidents in their open data portal](http://data.ottawa.ca/)

As well, Environment Canada [maintains information about the hourly weather reports across Canada](http://climate.weather.gc.ca/historical_data/search_historic_data_e.html). 

We want to create an integrated data mart in order to study the interplay between the weather and traffic accidents. 

## Data Staging

Before we can do analysis, we must stage the data.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/data-staging-plan.jpg' | relative_url }}" alt="" title="Data staging plan."/>
    </div>
</div>
<div class="caption">
    High level data staging plan.
</div>

## Analysis
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/olap-demo-1.jpg' | relative_url }}" alt="" title="OLAP demo."/>
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/olap-demo-2.jpg' | relative_url }}" alt="" title="OLAP demo."/>
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/olap-demo-3.jpg' | relative_url }}" alt="" title="OLAP demo."/>
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/olap-demo-4.jpg' | relative_url }}" alt="" title="OLAP demo."/>
    </div>
</div>

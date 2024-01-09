---
layout: post
title:  Interactive charts on a static page
date: 2020-04-01 22:25:00
description: Plotly is nice. (Ignore the read time! )
tags: plotly python code
categories: python-posts
featured: true
---
Turns out I don't need to worry about hosting plotly iteractive charts elsewhere. Plotly has apparently released many cool things into the open source side since the last time I used it. Basically, by only using ````plotly.express```` and ````plotly.io````, following can meet the need:

First export plotly-express charts to some html file (eg. test_plot.html using the snippet I picked from [Plotly Express Walkthrough](https://nbviewer.jupyter.org/github/plotly/plotly_express/blob/gh-pages/walkthrough.ipynb) ). This file holds the data loaded javascript (that operates the interactive chart at the client side) as well.

````python  
import plotly.express as px
import plotly.io as pio

gapminder = px.data.gapminder()
gapminder2007 = gapminder.query("year == 2007")

fig = px.scatter(gapminder, 
                x="gdpPercap", 
                y="lifeExp",
                size="pop", 
                size_max=60, 
                color="continent", 
                hover_name="country",
                animation_frame="year", 
                animation_group="country", 
                log_x=True, 
                range_x=[100,100000], 
                range_y=[25,90],
                labels=dict(pop="Population", 
                            gdpPercap="GDP per Capita", 
                            lifeExp="Life Expectancy")
                )
pio.write_html(fig, file='test_plot.html', auto_open=True)
````

Then you can either:
* Grab everything between <body></body> tags and put it in your static html.
* OR create a template html file with it and include it in a ```div``` where it needs to be shown.


You will see something like:

{% include plotly-express-demo.html %}

---
title: Analysis of the Solar Self-Sufficiency of my own house.
description: >-
  And discover the challenge of domestic solar systems in relation to household
  electricity consumption.
date: '2022-01-05T19:35:32.788Z'
categories: []
keywords: []
slug: >-
  /@bartroossien/analysis-of-the-solar-self-sufficiency-of-my-own-house-3f2a36bb0dd8
---

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__rf9fwvJHg5cvUlm36d7PZA.png)

My wife and I moved into our current house in the summer of 2019 and by November of that year, a solar panel system was installed. Now, two years later, it made me wonder. What if I would disconnect from the grid? Could I provide my house with electricity, just from the solar system?

**Solar system**

Our solar panel system consists of 14 panels of 305 Wp each, one string of 7 panels facing south-west and another string of 7 panels north-east. While facing southwards would have resulted in an increased yield, We wouldn’t have been able to mount all 14 panels on our flat roof. Each panel is inclined about 15 degrees. This brings the total installed power to 4,27 kW. But as the power peak of the two strings doesn’t coincide, this peak is never reached.

A Solis 4000 is the inverter that turns the DC power from the solar panels into AC grid power. It has a Wi-Fi dongle, allowing it to send its yield to the manufacturer, Ginlong. Ginlong provides a website and app to view the yield. I have been able to [extract the data](https://medium.com/@bartroossien/exporting-solar-panel-system-data-from-ginlong-solis-for-data-analysis-78be8662495e) of the website, which I have used for my analysis.

**Smart meter**

We live in a modern terraced family house of 138 m2, which is slightly larger than the Dutch average. It is well insulated (label A energy performance), but electricity is not (yet) used for heating or domestic hot water. We do cook on induction and have air-conditioning installed, though due to the cold weather in the summer, it has not been used much yet.

The house, like most houses in the Netherlands, has a smart meter. Data can be retrieved via third parties who have a contract with the grid company. I have been using [Enelogic](https://www.enelogic.com). Smart meter data consists of net import and feed-in of produced electricity.

**Results**

I’ll leave the mathematics on how I have deduced the results for another post and just show the results here. Throughout the year, our total consumption is almost 3,300 kWh, while our solar system produced over 4,000 kWh.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__3AFZvn9szI7z9qwo3oDPOw.png)

On paper, this means that we produce over 700 kWh of electricity more than we consume. Yet, we are not even close to being self-sufficient. Breaking down the production and consumption at a monthly level provides more insight.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__J5GM34jw0__0TDzyLy3f__gw.png)

In 7 of the 12 months, the solar system provides more electricity than we consume in that month. But in the winter months, it doesn’t come close to our needs.

But even in months with more production than consumption, there is a mismatch. We consume electricity throughout the entire day, particularly in the early evening, while the solar system provides electricity only during daylight. The image below, from the 24th of September highlights this well. When the graph is blue, we consume more than we produce, when it is green there is more production than consumption.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__t7Nvp7vSI__PRYBhhgenomQ.png)

**Self Sufficiency**

Self sufficiency of solar energy is defined as the energy produced by a solar system that is consumed immediately by the household, without going through the electricity meter, as a ratio of the total consumption, i.e

   Self sufficiency = \[solar energy directly used\] / \[consumption\]

The following image shows our self sufficiency per month. The entire bar that is above the x-axis (dark green + orange) is our total consumption for that month. The dark green part indicates the part of that consumption that is provided with our own produced solar energy. The orange part is what is left and taken from the grid. The light green part is the abundance of solar energy that is fed into the grid.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__rf9fwvJHg5cvUlm36d7PZA.png)

As you can see, the self sufficiency of our solar energy is relatively low. On average, 35% of our consumption is provided by solar energy. This varies throughout the year from 10% in December, up to 60% in June.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__ap1PB8JCuikM4PdOL__MfYw.png)

**Challenge**

So while on a yearly basis, our solar system produces 21% more energy than we consume, our self sufficiency is only 35%. To get to (near) 100% self-sufficiency, two main challenges have to be tackled.

First, the seasonality of solar energy. In the summer months, solar panels provide significantly more energy than in winter. But household consumption is approximately the same throughout all seasons (heating not included).

Secondly, even in the best producing month, May, when production is 2,2 times higher than consumption, the self-use is still only 54%. The cause is easy understood: there is a mismatch in when solar energy is produced and when household appliances are used.

In the next few articles, I’ll explore how self sufficiency can be increased with home batteries, more solar panels, urban wind and demand response.

_This article was inspired by_ [_Thomas Vogel_](https://medium.com/u/c9b5ccbe0e0)_’s view on_ [_his solar panel system_](https://tom-vogel.medium.com/solar-self-sufficiency-is-feasible-even-in-moderate-climates-40a91e5624b2)_._
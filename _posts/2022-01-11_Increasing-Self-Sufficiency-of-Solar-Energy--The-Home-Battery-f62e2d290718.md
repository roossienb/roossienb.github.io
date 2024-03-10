---
title: 'Increasing Self-Sufficiency of Solar Energy: The Home-Battery'
description: How much can a battery at home help consume your own generated solar energy?
date: '2022-01-11T20:16:41.125Z'
categories: []
keywords: []
slug: >-
  /@bartroossien/increasing-self-sufficiency-of-solar-energy-the-home-battery-f62e2d290718
---

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__eCb83C84nQ__te__feaGUx9Q.png)

With the increase in popularity of residential solar panels, homeowners are wondering how they can use their solar energy most effectively. Additionally, the significant increase in installed solar power increases the stress on an already vulnerable electricity grid. Batteries for electricity storage are seen as a solution. In this article, I research their potential to increase the self-sufficiency of the house my wife and me live in.

In a previous article, [I analysed the self-sufficiency of our own solar panels on my house](https://bartroossien.com/analysis-of-the-solar-self-sufficiency-of-my-own-house-3f2a36bb0dd8). With a maximum self-use of 60% in June and a minimum of 10% in December, the overall yearly self-sufficiency is at 35%. This means that 35% of my yearly energy consumption is directly provided by my solar panels, without being fed into the grid first.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__k7DhMVCqVTuaTMTMu5kK3Q.png)

### Battery

A home battery temporarily stores produced solar energy, so it can provide that energy at a later moment when there is a net demand. This reduces both the net export and net import from/to the grid. and increases self-sufficiency.

To research the potential of the home battery for our situation, I’ve built a simulation model, which is fed by consumption and production measurement data from my house. The model has the following characteristics:

*   The battery charges when there is a net export (and thus, reducing net export) and discharges when there is a net import.
*   Charging respectively discharging stops when the battery is full respectively empty.
*   Charging and discharging incur a 5% energy loss each to take into account internal battery resistance and DC/AC inverter losses.
*   Battery degradation and self-discharge are not taken into account.

In the below figure the monthly import, export and self-use are displayed for three different scenario’s: no battery, a 1 kWh battery and a 5 kWh battery.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__S1Xrv__t1s8zHMbiY3eOTOQ.png)

It is clear that the summer months benefit the most of the battery. After all, there is an abundance of solar energy in these months. During the day, the battery charges and during the night, it discharges. On most summer days, there is enough solar energy to charge the battery. With just a 5 kWh battery, June even reaches 100% self-sufficiency.

The winter months suffer from the lack of solar energy. A battery isn’t much help here. With just a 1 kWh battery, all net export in December is already turned into self-use, bringing it from 14% to 19%. But with the lack of additional solar energy, the 5 kWh battery cannot increase the self-use any further.

On a yearly basis, a1 kWh battery increases self-sufficiency from 35% to 44%. A 5 kWh battery pushes it to 65%. However, increasing battery size further doesn’t improve self-sufficiency much more. A 10 kWh battery for example results in a self-sufficiency of 69%, only 4 percent points more than a battery half the size.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__eCb83C84nQ__te__feaGUx9Q.png)

A 4 to 5 kWh battery seems to be the optimum for what you can get in case of our living situation.

Because we produce more electricity than we consume, we could be 100% self-sufficient on paper. Simulation return that this requires a battery of a whopping 1020 kWh, the same capacity as 13 Tesla Model 3s combined! But as batteries suffer from self-discharge — which we didn’t account for in the model — this wouldn’t work in practice. The battery would be mostly empty by December.

### **Conclusion**

A relatively small 5 kWh battery increases the self-sufficiency of our home by almost a factor of 2, from 35% to 65%. But due to low solar yield in the winter months, it is nearly impossible to increase it much further with batteries alone. Other means to increase self-sufficiency in the winter period need to be explored.
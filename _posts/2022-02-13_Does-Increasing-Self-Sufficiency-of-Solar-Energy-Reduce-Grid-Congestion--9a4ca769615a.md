---
title: Does Increasing Self-Sufficiency of Solar Energy Reduce Grid Congestion?
description: >-
  In previous articles, I looked at the self-sufficiency is of my solar-powered
  house and that I can increase it from 35% to 70% using…
date: '2022-02-13T19:27:56.285Z'
categories: []
keywords: []
slug: >-
  /@bartroossien/does-increasing-energy-self-sufficiency-solves-grid-congestion-9a4ca769615a
---

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\0__WkW0BjpWy__rUat2J.jpg)

In previous articles, I looked at the [self-sufficiency is of my solar-powered house](https://bartroossien.com/analysis-of-the-solar-self-sufficiency-of-my-own-house-3f2a36bb0dd8) and that I can [increase it from 35% to 70% using batteries](https://bartroossien.com/increasing-self-sufficiency-of-solar-energy-the-home-battery-f62e2d290718). However, I only looked at self-sufficiency, but not its economical feasibility nor impact on the electricity grid. Reader [Chiem Ringers](https://medium.com/u/59c90aa74595) rightfully pointed out the grid congestion that solar energy is causing in the Dutch grid and [wondered if batteries could help with it](https://medium.com/@chiemringers/interesting-insights-bart-47ff6d871f0d).

### **Grid congestion**

So what is the actual problem with solar panels and grid congestion? Electricity grids are designed with a certain capacity or power (measured in e.g. kW) in mind. The capacity required determines the thickness of distribution cables the size of transformer stations.

So how large should a transformer station be if I want to connect100 households to it? If I consider a single household, I may be doing the laundry (1.5 kW), vacuum-cleaning (2 kW) and running the television in the background (0.2 kW) all at the same time, bringing it to a total of 3.7 kW.

So would the transformer then have to provide 100 households time 3.7 kW? Not really, because while I’m vacuum-cleaning, my left neighbour is just playing some computer games, while my right neighbour is out the door.

The fact that households don’t do the same thing all the time is called ‘simultaneity’. Vacuum-cleaning has a very low simultaneity (very few households vacuum clean at the same time) while turning the lights on has a very high simultaneity.

Combining power usage with simultaneity is a statistical exercise with which electricity grids have been designed. To give you an idea, while a standard Dutch household can draw around 5.8 kW based on its fuse, the grid is designed for 1.2 kW of simultaneous power load.

#### How does solar energy cause grid congestion?

So why does solar energy create grid congestion? For one, the amount of power installed in the Netherlands is typically around 3 to 5 kW. Secondly, it has a very high simultaneity. If the sun shines on my roof, it shines on my neighbour's roof as well.

On a beautiful sunny day, around noon, this system will provide this maximum power. And so will your neighbour’s systems. If everyone in your street has solar panels, it results in a peak that is two to three times larger than what the grid has been designed for. And we simply don’t consume enough during the day to compensate for this.

This large amount of produced electricity cannot be fed back to the transformer, it is too small. Now we have grid congestion.

### **Does increased self-sufficiency help?**

In my previous article, I demonstrated that a 5 kWh battery could bring the self-sufficiency of my house (with a true consumption of about 3.300 kWh per year) and my solar panels (max power of 4.2 kW and yield of 4.000 kWh per year) to about 70%. In other words, 70% of the energy produced would be consumed in my house without using the grid.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1____sxdPzgB4cz2fVQWG8VHBQ.png)

In the summer months, self-sufficiency would reach almost 100%. I would have to buy little to none in electricity from the grid. However, I am still feeding significant amounts of electricity back to the grid.

To give you an idea, I’ll take a sunny day at the end of May. This day yields almost 30 kWh in solar energy, providing energy from 7 am to 9 pm. The 3 kW peak (I’ll leave it to another post to explain why this peak isn’t 4.2 kW) is visible at around 1:30 pm.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__O2KRJZ2zO6mq6vIgnv1HOA.png)

My average daily consumption is only 9 kWh, only 30% of my production this day. The remaining 70% has to be fed back into the grid. I cannot even store it into a battery.

Now for simplicity assume that the 9 kWh I consume is evenly distributed throughout the day. This constitutes a continuous power of about 375 watts. The net power is the difference between my consumption and production. During the night, electricity is bought from the grid (the net power is > 0), while during the day, abundant electricity is fed back (net power < 0). The power peak around 13:30 is still clearly visible, although 375 watts smaller than the production peak.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__clrDMU6nwWyEZN0vZ9__BEw.png)

If I aim for self-sufficiency, I can use a simple algorithm for the battery charge controller. When I consume more electricity than I produce, I’ll take it from the battery until it is empty. If I produce more than I consume, I’ll charge the battery until it is full. While it looks simplistic, it ensures maximum self-sufficiency.

So what happens with the net power? In the ‘night’, it goes to zero as all electricity is provided by the battery. The night lasts about 11 hours, in which I consume just over 4 kWh. The 5 kWh battery isn’t even completely depleted.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__96oeWvVOQD__BF__BddE9q6g.png)

Starting from around 6:00 am, solar panels start to provide electricity and partially take the consumption load. By 7:30 am, there is enough solar energy to cover my consumption. At this point, the battery switches from discharging to charging. By 11 am, the battery already is full. But the solar panels have at least another 20 kWh to produce. That production is fed straight back to the grid.

From a grid perspective, the 1:30 pm power peak is yet to come when my battery is already fully charged. There is nothing the battery can do the alleviate the grid congestion that is starting to happen.

So while self-sufficiency for this day is at 100%, grid congestion is still at the same level, because I did not reduce my power peak.

### **Smart charging**

Now I could introduce some intelligence in the battery charging algorithm. I don’t have to start charging immediately in the early morning if I know I have so much solar energy during the day. If I pick specific times and regulate charging power, I can charge following the pattern in the figure below.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__l3JIBVteFaUMNW2wuJgn4w.png)

I still charge the battery with the same amount (about 4 kWh, the amount that is discharged during the night). But because I manage when and how much I charge, I can reduce my power peak from 2.6 kW to 1.7 kW, a reduction of 36%. And all the while, I’m still self-sufficient on this day.

**Controller complexity**

A perfect day like the scenario above is relatively easy for a smart battery charge controller. But what if the day is partially clouded? The figure below shows the solar yield on a partial clouded day. The total yield is only half of that of a fully sunny day (about 15 kWh) but still enough for 100% of self-sufficiency. And the power peaks during midday remain when the sun shows itself a few time.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__ZsOkaWPhxZ153rs7ZCxfCA.png)

If I would use the same intelligence as early, I would charge the battery when the production peak is at about 2 kW or higher. By 16:30 when the last peak has been mitigated, the battery is only 60% full, requiring another 2 kWh to be fully charged. But that 2 kWh is nowhere to be seen in the rest of the day. The sun just disappears after 16:30.

On top of that, I have to start discharging to battery at 16:30 to cover my consumption, because there is not enough sun to provide the 375 watts I need.

To be able to maximize self-sufficiency and mitigate grid congestion on a day like this, the charge controller needs a lot more intelligence. For example, I could forecast the solar yield based on weather information, so I can better plan the charging of the battery, reducing production peaks, while still charging early enough to fill up the battery before the production comes to a hold. This requires risk management (forecasts aren’t accurate) and adaptation to a changing environment.

### **Conclusion**

Increasing self-sufficiency with a battery by itself does not alleviate grid congestion. It smarter battery charge controller is needed to reduce the peak power. To ensure both self-sufficiency and grid congestion management requires significant and complex intelligence that comes at a cost. Grid companies will have to provide ample financial incentive for consumers to convince them to buy such intelligent charge controllers.
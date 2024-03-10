---
title: 'Energy consumption analysis with MATLAB Part 2: Correlations'
description: Contents
date: ''
categories: []
keywords: []
slug: ''
---

### Contents

*   [Introduction](https://web.archive.org/web/20160323012551/http://www.geekgravity.com/#1)
*   [Weather data](https://web.archive.org/web/20160323012551/http://www.geekgravity.com/#4)
*   [Scatter plot](https://web.archive.org/web/20160323012551/http://www.geekgravity.com/#7)
*   [Identify correlations](https://web.archive.org/web/20160323012551/http://www.geekgravity.com/#8)
*   [Fitting data](https://web.archive.org/web/20160323012551/http://www.geekgravity.com/#9)
*   [Key information](https://web.archive.org/web/20160323012551/http://www.geekgravity.com/#11)
*   [Solar](https://web.archive.org/web/20160323012551/http://www.geekgravity.com/#12)

### Introduction

For almost 6 years, I kept track of my energy consumption. First by manually writing down the values of my electricity and gas meter on an (almost) weekly basis, then by collecting smart meter data through a RaspberryPI. Although I’ve done some analysis on it, I never truly researched the data. So why not write a series of blog posts about it, on how I’ve analysed this data?

In [Part 1](https://web.archive.org/web/20160323012551/http://www.geekgravity.com/article/14/energy-consumption-analysis-with-matlab-part-2) of this series, we discussed how meter value data is digitalized, verified and then processed into validated consumption data. In this article, we’ll perform correlation analysis on the gas consumption.

This blog post starts from where part 1 finished. The validated data in the CorrectedData structure is renamed to Data for this article and assumed to be present in MATLAB’s work space.

To remind ourselves of how the data looked, we’ll plot the gas consumption data again. This time, we’ll use the correct plot type for discrete data. Because MATLABs bar function cannot handle the datetime type, we convert the date to MATLABs build-in numerical time format and set the axis labels manually.

fh = figure();  
ah = axes('Parent', fh);  
bar(ah, datenum(Data.date), Data.gas, 'r');  
ah.XTick = datenum(2009, 4:3:54, 1);  
ah.XTickLabel = datestr(datenum(2009, 4:3:54, 1), 'mmm-yy');  
ah.XTickLabelRotation = 90;  
ylabel('Gas consumption \[m^3/week\]');

The heating seasons, which usually starts halfway October and ends somewhere in April, are clearly visible by the high consumption. The non-zero values in the summer is the hot tap water consumption, which is approximately constant throughout the year.

There is a lot of variation among the heating seaons. In every winter, the size and width of the seasonal peak is different. Not entirely suprising as every (Dutch) winter is different. So we know that weather has an influence on the gas cosumption. Time to see if we can find a correlation by combing the consumption data set with a weather data set.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\0__SbKKYbmpaQbmv5__n.png)

### Weather data

Dutch weather data can be obtained from [http://www.knmi.nl](https://web.archive.org/web/20160323012551/http://www.knmi.nl/). In this case I’m using daily averages from the Schiphol weather station. I’ve written my own class that reads these types of data files, called KnmiReader.

weather = KnmiReader.getDailyData('Data/knmi\_day.txt');

Let’s plot the average daily temperature for the same time interval as our gas consumption data, just to get a feeling for the data.

figure();  
plot(weather.time, weather.temperature);  
xlim(datenum(Data.date(\[1 end\])));  
ylabel('Outside temperature \[^oC\]');

The temperature seasons are clearly recognizable. To match the consumption data, we need to turn the daily weather data into weekly data. We take the average of 7 days for the ambient temperature and the sum of 7 days of global solar irradiation. I’ll explain later why I also include solar irrradiation.

startIdx = find(weather.time == Data.date(1));  
endIdx = find(weather.time == Data.date(end));

weekWeather.time = weather.time(startIdx:7:endIdx);  
weekWeather.temperature = zeros(size(weekWeather.time));  
weekWeather.solarIrrad = zeros(size(weekWeather.time));

for k = 1 : 7  
    idx = (startIdx - 7 + k) : 7 : (endIdx - 7 + k);  
    weekWeather.temperature = weekWeather.temperature + weather.temperature(idx);  
    weekWeather.solarIrrad = weekWeather.solarIrrad + weather.global\_irradiation(idx);  
end  
weekWeather.temperature = weekWeather.temperature / 7;

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\0__ldcq1l8E2GD0M__eW.png)

### Scatter plot

Scatter plots are the easiest way to discover relationship and potential correlation between two sets of data. The axis represents the values of each of the data sets. In case of time series, the time component is not plotted amd only used to match the values of the first data set with the values of the second data set.

Let’s plot our ambient temperature against our gas consumption. Because the vectors share the same time vector, we can use the vectors directly.

figure();  
axes('NextPlot', 'Add', 'Box', 'on', 'XMinorTick', 'on');  
plot(weekWeather.temperature, Data.gas, '.', 'MarkerSize', 15);  
xlabel('Ambient temperature \[^oC\]');  
ylabel('Gas consumption \[m^3/week\]');

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\0__D__38pAyglsli__X6R.png)

### Identify correlations

If there would have been no relationship between temperature and gas consumption, the blue markers would have been all over the place. Instead, they are rather confined to a narrow band, indicating a strong correlation.

You may see that the markers are roughly on two lines, one descending line at lower temperatures and one horizontal line at higher temperatures. This matches the theory of gas consumption in households: during higher ambient temperatures, there is no space heating, only hot tap water production. And the latter is roughly constant each week. In building physics, one can proof that there is a linear proportional correlation between space heating and ambient temperature. This results in the descending line at lower ambient temperatures.

There is a transition point, i.e. an ambient temperature, at which space heating is no longer required. This is at about 13.5 degrees Celsius. Let’s mark that point. We now have visually split our scatter plot in two parts.

plot(\[13.5 13.5\], \[0, 40\], '--', 'Color', \[0.5 0.5 0.5\], 'LineWidth', 2);

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\0__JpVda1Ef9TKhvdRT.png)

### Fitting data

We now want to find the two lines through our data set, using a technique called fitting. Fitting means finding the parameters of a function (e.g. a line) such that the function matches the data points in the best possible way. There are a many mathematical algorithms that can do that for you, but MATLAB already provides those. In this case, we use polyfit, which fits a polynomial of any order that you specify.

Of course, we only use the data points that match the range in which we want to fit the function. For the tap water, it is ambient temperatures higher than 13.5 degrees Celsius and for space heating temperatures equal or below 13.5 degrees Celsius.

idx = weekWeather.temperature > 13.5;  
tapWaterFitParam = polyfit(weekWeather.temperature(idx)', Data.gas(idx), 0);  
spaceHeatingFitParam = polyfit(weekWeather.temperature(~idx)', Data.gas(~idx), 1);

And let’s add those lines to the plot

plot(\[-5 15\], polyval(spaceHeatingFitParam, \[-5,15\]), 'LineWidth', 3);  
plot(\[5 25\], polyval(tapWaterFitParam, \[5,25\]), 'LineWidth', 3);

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\0__NVHcLXhFdNnhzsLI.png)

### Key information

These two lines give us a lot of information

*   The horizontal line is a constant. The constant equals the average weekly gas consumption for tap water.
*   The slope of the descending line is a net heat demand characteristic for this specific building.
*   The point where the two lines intersect is the actual transition point. Note that it is very closely to what we ‘eyeballed’.

fprintf('Tapwater usage   = %3.1f m3/week\\n', tapWaterFitParam(1));  
fprintf('Net heat demand  = %3.1f m3/oC\\n', spaceHeatingFitParam(1));  
fprintf('Transition point = %3.1f oC\\n',  fzero(@(x) polyval(spaceHeatingFitParam, x) ...  
                                                    - polyval(tapWaterFitParam, x), 13.5));

Tapwater usage   = 4.2 m3/week  
Net heat demand  = -1.8 m3/oC  
Transition point = 13.7 oC

### Solar

You may have noticed that there is a lot of spread around the descending line. That’s because temperature is not the only parameter affecting the gas consumption. One thing I would like to show you, without going in depth, how another parameter can affect your scatter plot, and how you can visualize it’s effect.

We’ve separated our previous scatter plot data into four segments. Each segment is defined by the amount of solar irradiation. I’ll make the scatter plot again, the same way as before, but color each of the segments.

figure();  
axes('NextPlot', 'Add', 'Box', 'on');

for k = 1 : 4  
    idx = weekWeather.solarIrrad >= 45 \* (k-1) & weekWeather.solarIrrad < 45 \* k;  
    plot(weekWeather.temperature(idx), Data.gas(idx), '.', 'MarkerSize', 15);  
end

plot(\[-5 13.6\], polyval(spaceHeatingFitParam, \[-5,13.6\]), 'LineWidth', 3, 'Color', \[0.5 0.5 0.5\]);  
plot(\[13.6 25\], polyval(tapWaterFitParam, \[13.6,25\]), 'LineWidth', 3, 'Color', \[0.5 0.5 0.5\]);

xlabel('Ambient temperature \[^oC\]');  
ylabel('Gas consumption \[m^3/week\]');  
legend('0-45 MJ/m^2', '45-90 MJ/m^2','90-135 MJ/m^2', '135-180 MJ/m^2');

What we see is that if there is little to no solar irradiation (blue markers), the gas consumption is generally higher than the fitted line. If there is a significant amount of solar irradiation (red and yellow markers), the gas consumption is generally lower than the fitted line. The purple markers (long sunny days) only occur in the summer. Note that we’ve had cold summer days, although they are rare.

This figure clearly shows the impact of solar irradation on our gas consumption. How to handle multiple correlations at the same time is something for another time. A one word teaser for the solution: regression.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\0__NAY77zNq9V6Z3Fls.png)

Published: 29 February 2016
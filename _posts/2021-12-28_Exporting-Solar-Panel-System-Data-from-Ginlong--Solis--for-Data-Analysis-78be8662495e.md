---
title: Exporting Solar Panel System Data from Ginlong (Solis) for Data Analysis
description: >-
  I have 14 solar panels in two strings connected to a Solis inverter. Through
  an app, I can see my daily production live. It’s manufacturer…
date: '2021-12-28T19:38:07.706Z'
categories: []
keywords: []
slug: >-
  /@bartroossien/exporting-solar-panel-system-data-from-ginlong-solis-for-data-analysis-78be8662495e
---

I have 14 solar panels in two strings connected to a Solis inverter. Through an app, I can see my daily production live. It’s manufacturer, Ginlong Technologies, also has a website with a dashboard. This dashboard provides more insight in inverter data, such as voltages and currents.

The Solis inverter sends its data to [https://m.ginlong.com](https://m.ginlong.com). You can login with your username and password, the same one as for the app and probably given to you by the installation company.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__pwaOz2fEDbNbM9qBpvYPmQ.png)

### Plant production

The main page provides information about the solar yield, per day, month or year for the plant. A ‘plant site’ can contain multiple inverters. In my case, and like many other households, the site only contains one inverter.

I’m only interested in the real-time data, provided on the Daily Production page, as I will perform my own data analysis.

When a day is selected, a POST request is made, which turns out also works as a GET request:

https://m.ginlong.com/cpro/epc/plantDetail/showCharts.json?plantId=xxxx&type=1&date=2021/12/21

The plantId is found under the tab ‘plant info’. You can enter any date since the moment your inverter is operational. The type parameter is mandatory, although I have no clue what it does.

The above request returns all data points for that day that have been registered. Note that for the time the inverter is shut down (when there is no sun), no data points are registered. The response is a JSON:

{  
  "result": {  
    "chartsDataAll": \[  
      {  
        "bt": 0,  
        "date": "1640593800000",  
        "minllis": 60,  
        "power": 0.03  
      },  
      {  
        "bt": 0,  
        "date": "1640594100000",  
        "minllis": 60,  
        "power": 0.03  
      }  
    \]  
  }

The important data here is ‘date’, which is the UNIX timestamp in milliseconds and ‘power’, the power output of the plant site in kW.

### Inverter data

If you go to _devices_ and then select your inverter, you will find more information. This includes per string voltages and currents, AC voltages and currents and inverter temperature. I’ve noticed that in my case, this data is only available since the 31st of May at 17:00 UTC. I don’t know if this has to do with data retention, or that it is a new feature only rolled out in May 2021.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__2KDujMufDfaDrOIq__u__12w.png)

Like the plant data, a POST request is made to retrieve this data, which also works as a GET request:

[https://m.ginlong.com/cpro/device/doInvGraph.json?deviceId=xxxxxx&type=1&day=2021/12/21](https://m.ginlong.com/cpro/device/doInvGraph.json?deviceId=101772941&type=1&day=2021/12/21)

The deviceId can only be found through the development tools (F12), I have not been able to find it anywhere else. The parameter ‘day’ is the date for which the data is obtained. As said, for me it only work since May 31st 2021. And again, I have no idea what ‘type’ does.

It returns something that should go through as JSON, but it isn’t valid. I figured out four text replacements need to be made to turn it into valid JSON:

Replace \\" by "  
Replace "{ by {  
Replace }" by }  
Replace ' by "

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__t2f__RfoDG8nKE9nCvwft7Q.png)

After making the JSON valid, it turns into gibberish as the data has been obfuscated. With the help of the official export function, I have been able to reverse engineer most of it. I’ve left out the non-relevant fields, such as inverter identifiers and error codes.

{  
  "date": 1640086011000,          // UTC date in UNIX time in       
                                  // ms data point received  
  "1a": "249.70",                 // DC voltage string 1 (V)  
  "1b": "240.10",                 // DC voltage string 2 (V)  
  "1j": "0.30",                   // DC current string 1 (A)  
  "1k": "3.00",                   // DC current string 2 (A)  
  "1ab": "794",                   // Total DC input power                 
  "1ah": "232.80",                // AC voltage phase 1 (V)  
  "1ai": "0",                     // AC voltage phase 2 (V)  
  "1aj": "0",                     // AC voltage phase 3 (V)  
  "1ak": "3.30",                  // AC current phase 1 (A)  
  "1al": "0",                     // AC current phase 2 (A)  
  "1am": "0",                     // AC current phase 3 (A)  
  "1ao": "774",                   // AC total power active (W)  
  "1ar": "50.00",                 // AC output frequency (Hz)  
  "1ez": "1022",                  // Inverter status  
  "1aw": "1.40",                  // Generation yesterday (kWh)  
  "1bc": "7505.00",               // Total generation  
  "1bd": "1.30",                  // Generation today (kWh)  
  "1be": "25",                    // Generation this month (kWh)  
  "1bf": "3336",                  // Generation this year (kWh)  
  "1bs": "768",                   // AC Total apparent power (VA)  
  "1bt": "1.00",                  // Power factor  
  "1jq": "21-12-21 12:28:37",     // System time (yy-MM-dd HH:mm:ss)  
  "1df": "33.00",                 // Inverter temperature (deg C)  
  "1hk": "3600",                  // Rated power (W)  
  "1ru": "76",                    // Generation of last month (kWh)  
},

### Automation

To retrieve more than one day, automation is required. To perform the GET calls outside of a browser, authentication is required. It is a simple cookie called ‘rememberMe’ that provides this authentication. It’s value is found through the Developer Tools (F12) of any modern browser.

To automate the retrieval of data for longer periods, I have written an application in C# / .NET 5.0. The code is available on my [Github page](https://github.com/roossienb/Ginlong-reader).

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__NcCvcE9__QNQoxIwWWKwZmg.png)
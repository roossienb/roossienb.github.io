---
title: The one skill that makes you a better engineer.
description: It provides a quick answer to complex problems.
date: '2021-05-27T07:27:00.576Z'
categories: []
keywords: []
slug: /@bartroossien/the-one-skill-that-makes-you-a-better-engineer-233c1c57ee54
---

It provides a quick answer to complex problems.

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\0__Z4oi2atr1K9feLWJ.jpg)

If the ice on Antarctica would all melt, the global sea level rises by 57.9 meters. But how would you know that this answer is correct?

As an engineer, consultant and former scientist, I am capable of performing accurate calculations for complex problems. The downside is that those calculations take lots of time to perform. In many cases, a quick approximate of the answer comes a long way.

Such an answer is valuable. It allows the continuation of the discussion with stakeholders without having to wait another few weeks for the exact answer to be calculated.

Quick estimates of complex problems, without using anything but your own brain can be performed with a technique called **Fermi estimation**.

### **Enrico Fermi**

On the 16th of July 1945, the world’s first nuclear weapon was detonated at a location 200 miles south of Los Alamos in New Mexico, United States. The moment the explosion took place, Italian physicist Enrico Fermi — one of many famous physicists working on the atomic bomb — dropped a few scraps of paper. The scraps were blown away by the shockwave blast. Based on the time the scraps fell and the distance covered, Fermi estimated the power of the atomic blast at 10 kilo-tons of TNT, without using a pencil or calculator.

Weeks after the blast, scientists had calculated the precise power at 20 kilo-tons of TNT. While it seems like Fermi’s estimation was 50% off the actual value, his estimate was a decent order of magnitude. Given that nobody at the time had any idea about the true yield of atomic weapons, Fermi’s answer provided him with an immediate estimate of the test results, rather than having to wait for the full analysis.

### Example: Antarctica

So if the ice on Antarctica would all melt, how much will the global sea level rise? Let’s break the problem down. We need to know the volume of ice that melts, and how much the sea level rises if that amount of ice-melted water is added to the current oceans.

The volume of ice equals the area of Antarctica, times the thickness of the ice. I happen to know that Antarctica is a mountainous plateau. I have been on the Hardangervidda, a plateau in Norway, which is about 1500 meters high, so I guess it is about the same height.

Yes, I know I could look up what the average thickness of the ice is, but the whole point of Fermi estimation is that you do not look things up. You work from what you do know.

If I take a map in my mind, I guess that Antarctica is about the size of the United States. I have no idea what the exact area of the United States is either, but I have a better feeling for it than Antarctica. I estimate it is about 5,000 km from the East to West coast and about 3,000 km from Canada to Mexico. That brings the area at 5,000 x 3,000 = 15 million square km.

Multiplying the area with the estimated 1,5 km thickness brings the volume of the ice to roughly 22 million cubic km.

Although ice is more voluminous than water, I guess that this difference is neglectable compared to more sizeable errors in my estimation, so I ignore the density differences.

The only thing left is to estimate the area of the oceans on Earth.

I know the Earth has a radius of around 6.500 km. If you would not have known that, maybe you remember that the circumference of the earth is around 40.000 km (from which you can deduct the radius).

Earth is a sphere. The surface of a sphere is given by 4 x PI x radius x radius. I could use a piece of paper or a calculator, but as I’m estimating here, I can do without. With 6 x 6 = 36 and 7 x 7 = 49, 6.5 x 6.5 is somewhere around 45 (million). With pi approximated by 3, the surface of the earth is 4 x 3 x 45 (million), which is roughly 500 million square km.

Two-thirds of the earth is an ocean, making the total ocean surface around 300 million square km.

The only thing left is to divide 22 million cubic km of ice by 300 million square km of ocean, or simply put 22/300 km. If we convert that to meters, we end up with 22,000 / 300, or simply 220/3, which is about 70 meters.

[My estimation is pretty close to the accurate value of 57.9 meters.](http://www.antarcticglaciers.org/glaciers-and-climate/what-is-the-global-volume-of-land-ice-and-how-is-it-changing/) Well within an order of magnitude. Note that I wrote this paragraph without looking up any data, nor did I use a calculator. And I’m only 20% off from the accurate answer.

### How it works

When solving a Fermi problem, one has to make justified guesses and their uncertainties by breaking the problem into small pieces. It involves working with what you know and what you can.

Every guess imposes an error in the answer. But as one guess overestimates the answer, another guess underestimates it. In the end, many of these errors (partially) cancel each other out.

A great example is my estimation of the area of Antarctica. My first guess was that Antarctica is about the same size as the 48 contiguous states of the United States and my second guess was that this area was about 3,000 x 5,000 km in size. The reality is that Antarctica is [14.2 million square km](https://en.wikipedia.org/wiki/Antarctica), very close to my answer, but that the contiguous states are only [8 million square km](https://en.wikipedia.org/wiki/Contiguous_United_States#:~:text=Together%2C%20the%2048%20contiguous%20states,to%20the%20area%20of%20Australia.).

I underestimated the size of Antarctica when I compared it to the United States, but I did overestimate the area of the United States. These two errors cancel each other out. My answer of 15 million square km was only 6% off.

I did something similar when I had to calculate the surface area of the earth. By rounding values, such as the number pi (3.14), It made for an easy calculation. As some numbers were rounded upwards and others downwards, the errors cancelled themselves out. With the actual surface area of the earth being [510 million square km](https://en.wikipedia.org/wiki/Earth), my answer underestimated it by just 2%.

### Practical application

Fermi believed that the ability to make a quick estimate was a vital skill for physicists. But I believe that Fermi-estimation is a must-have skill for anyone involved in engineering, (analytic) consulting or science.

Fermi estimation is an easy way to get a good guess for an answer to a difficult problem. This is useful when a quick rough answer is required.

> The Fermi rule: Better be approximately right than precisely wrong.

Imagine being able to give a customer an (almost) immediate estimate on a complex problem. It helps the customer to focus on the problem definition. And it helps you and your colleagues to move the discussion towards the details or lay the foundation for a sales opportunity.

And as a bonus, towards both your colleagues and the customer, you present yourself as a knowledgeable professional that can come up with an answer quickly. In my experience, this is a valuable trait that will boost your career, as people will more frequently request your involvement in (complex) projects.

Another great application for Fermi-estimation is to check the answer of a (complex) analysis or calculation. Does the answer that your model calculated make any sense? A quick estimation helps to understand in which order of magnitude the answer should be found, providing you with valuable information if the model may contain errors.

### Conclusion

Fermi-estimation is all about making educated guesses based on information that you already know. From my personal experience, it helps to keep discussions with customers going and safeguards against possible errors in complex models.

With a bit of practice, it does not require any calculator. And the only sheet of paper you need is the one that you shred to estimate the yield of a nuclear weapon. Just like Enrico Fermi did.

#### Practice yourself

Here are some business-oriented questions to practice Fermi estimation yourself.

*   How many pieces of luggage does your nearest international airport handle each year?
*   What is the market size valued for pizza’s in New York City?
*   How much is the fuel bill for a plane on a trip from London to Auckland?
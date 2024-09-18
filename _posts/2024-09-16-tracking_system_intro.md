# What I Track

My long-term goal is to track as wide a range of variables related to my body and environment as possible, while minimizing the time investment by automating the process to the greatest extent. In this blog, I aim to outline what I track and how I go about it.

I began tracking in earnest on February 16, 2021. The range of variables I monitor has gradually expanded. Currently, I track over 300 variables across the following  categories/devices:

* Daily habits
* Supplements
* Exercise
* Diet
* Smoothie
* Sleep
* Fitbit tracker
* Withings scale
* Blood pressure
* Heart rate variability
* Fasting glucose (daily)
* Bi-monthly blood tests
* Medication

In addition to these regularly tracked variables, I also conduct various one-off  (or very occasional) tests, such as food intolerance and genetic/epigenetic tests, which
are not directly part of this tracking framework, but may become relevant as I delve deeper into the analysis.

Below, I provide a brief overview of each category and the rationale behind its inclusion. While I won't list all the tracked variables here, I plan to explore each category in more detail in future posts. In the next blog I will then outline the  technological stack I have implemented to collect and analyze all this data.

## Daily Habits

This category encompasses a diverse array of health indicators that I manually log every evening, such as my overall energy levels, sleep quality, and mood or stress levels.

## Supplements

As the name suggests, this category is where I record the supplements I take daily. Over the years, I've experimented with a wide range of supplements, and future analyses will focus heavily on this category.

## Diet

This is the area where I'm least satisfied with my current tracking methodology. Ideally, I would track the exact weight of each basic food ingredient daily, but I haven't found a sufficiently simple and time-efficient solution. Eating out for almost every lunch and cooking a wide variety of dishes at home makes tools like Chronometer impractical without significant extra time, planning, and discipline. With the advent of strong AI, solutions are on the horizon that might crack this problem for me. We'll see.

Currently, I track a broad set of dietary components, which is however far from comprehensive, in a simplified manner, using levels such as ['none', 'a little', 'a lot'] or a binary flag to indicate whether I consumed a particular component that day. There are a few exceptions where I do track the exact weight, such as for key but simple to track nutrients such as 'added sugar'.

## Smoothie

I prepare a fresh smoothie daily, and its composition has evolved significantly over time. I track all its components daily, warranting its classification as a separate category.

## Sleep

Every day, I receive a questionnaire at 8 AM to assess my sleep quality, coinciding with my commute to work. I track both subjective aspects of sleep and environmental factors, such as pre-sleep activities like reading or listening to music.

## Fitbit Tracker

I wear a Fitbit tracker, currently the Fitbit Charge 6, and have automated the data extraction process. Notable parameters include Sleep Score, sleep duration, deep and REM sleep duration, deep sleep HRV, daily HRV, resting heart rate, distance walked, skin temperature, breathing rate during sleep, and sedentary minutes, but I track all available via the Fitbit API.

## Withings Scale

I use the Withings Body scale each morning to measure weight, body composition, and pulse wave velocity. An automated script imports these values into my central database.

## Blood Pressure

Each evening after I get into bed, I measure my blood pressure with the Withings BP monitor, with an automated script importing the data.

## Heart Rate Variability

Immediately upon waking, I measure my heart rate variability (HRV) with a Polar chest strap and KubiosHRV application while still in bed. On top of HRV, I also track readiness index, stress index, SNS index, and PNS index that this measurement produces.

## Fasting Glucose (Daily)

Each morning, I measure my fasting blood glucose using a standard strip-based glucometer.

## Bi-monthly Blood Tests

About every two months, I undergo a basic blood test panel that includes around 40 key biomarkers. I also occasionally test additional parameters that are too costly for frequent analysis.

## Medication

I log any medication I take.

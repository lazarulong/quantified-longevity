My long-term goal is to track as many variables related to my body and environment as possible, while minimizing the time required by automating the process to the greatest extent. In this blog, I’ll outline what I track and how I go about it.

I began tracking in earnest on February 16, 2021, and the range of variables I monitor has gradually expanded. I now track over 300 variables across the following categories/devices:

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

In addition to these regularly tracked variables, I also conduct various one-off (or very occasional) tests, such as food intolerance and genetic/epigenetic tests. While not part of my core tracking framework, these may become relevant as my analysis deepens.

Below is a brief overview of each category and the rationale for tracking it. I won't list every variable here, but I plan to explore each category in detail in future posts. In the next post, I'll outline the technological stack I've implemented to collect and analyze all this data.

## Daily Habits

This category includes a diverse range of health indicators that I manually log each evening. These for example include my overall energy level, sleep quality, mood, or stress level.

## Supplements

This section tracks the supplements I take daily. Over the years, I’ve experimented with a wide variety of supplements, and future analyses will put a lot of focus on this category.

## Diet

This is the area where I’m least satisfied with my current tracking approach. Ideally, I would log the exact weight of each ingredient I consume daily, but I haven't yet found a simple, time-efficient solution. Given that I eat out for most lunches and prepare a wide variety of meals at home, tools like Chronometer are impractical without significant extra effort, planning, and discipline. However, with advancements in AI, I’m hopeful a solution will emerge soon. Time will tell.

For now, I track a broad set of dietary components in a simplified manner, using levels like ['none', 'a little', 'a lot'] or binary flags to indicate whether I consumed a particular component that day. A few key nutrients, like added sugar, are exceptions where I do track exact amounts.

## Smoothie

I prepare a fresh smoothie daily, and its composition has evolved significantly over time. I track all the ingredients daily, which justifies its classification as a separate category.

## Sleep

Every day, I receive a questionnaire at 8 AM to assess my sleep quality, coinciding with my commute to work. I track both subjective aspects of sleep and environmental factors, such as pre-sleep activities like reading or listening to music.

## Fitbit Tracker

I wear a Fitbit, currently the Charge 6, and have automated the data extraction process. Notable metrics I track include Sleep Score, sleep duration, deep and REM sleep stages, deep sleep HRV, daily HRV, resting heart rate, steps taken, skin temperature, breathing rate during sleep, and sedentary minutes. I track all parameters available via the Fitbit API.

## Withings Scale

Each morning, I use the Withings Body scale to measure my weight, body composition, and pulse wave velocity. I’ve automated the import of these values into my central database.

## Blood Pressure

Occasionaly, after I get into bed, I measure my blood pressure with the Withings BP monitor, and an automated script uploads the data into my system.

## Heart Rate Variability

Immediately upon waking, I measure my heart rate variability (HRV) with a Polar chest strap and KubiosHRV application while still in bed. On top of HRV, I also track readiness index, stress index, SNS index, and PNS index that this measurement produces.

## Fasting Glucose (Daily)

Each morning, I measure my fasting blood glucose using a standard strip-based glucometer.

## Bi-monthly Blood Tests

Approximately every two months, I undergo a basic blood panel, which includes around 40 key biomarkers. Occasionally, I test for additional parameters, that are too costly for frequent analysis.

## Medication

I log any medication I take.

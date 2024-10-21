# Implementation of the tracking system

In the following figure you can see the architecture of my personal tracking system that I have developed:

![Fig 1](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot from 2024-02-06 18-36-10.png)

As you can see, all the different data sources feed into the central database, where they are enriched with metadata.The analytical platform can then access all this data via a unified interface.
The design of the system was motivated by minimizing any new code development, while maximizing flexibility. It allows for straightforward addition of new data-sources. At the level of the central database, all the data is enforced to have a simple unified format, which then allows for efficient implementation of the analytical platform. 

A key simplification has been done here, which is that I assume that each tracked variable is recorded at most once a day. This is reasonable assumption for tracking long-term processes relevant for longevity, but it does somewhat limit the use-cases where the platform can be applied.
It however greatly simplifies the data-representation - essentially all the data are one big simple table, with rows being days and columns being the individual tracked variables. It is worth pointing out that this table has a lot of 'missing' values, because many variables are not recorded daily (e.g. blood tests). 

Let me now dive into each of the components a little bit deeper.


## Different data sources and their date feed automation

### Telegram surveys
I have coded a simple Telegram survey bot, that allows pre-defined surveys to be sent to the user onto a telegram channel at pre-specified time each day (or subset of days depending on configuration). Here you can see an example of such survey in the telegram channel that I respond to every morning that assesses the subjective quality of my sleep. It takes about 2 minutes to fill in.

![Fig 2](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot_20240206-181700.png)


The telegram bot collects the data and sends it via API into the AirTable database. New surveys can be rapidly added or modified in
a simple configuration file. In the figure below you can see a configuration of a simple survey that allows me to rapidly enter lung function test results after I obtain them from the SmartOne device, which unfortunately does not offer an API for automated data downloads:

![Fig 3](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot from 2024-02-06 18-49-23.png)

A bonus of this approach is that for example this specific survey is scheduled only once a week, but by receiving it on Telegram every Saturday it seconds also as a reminder to take the lung test using the SmartOne device.

### Fitbit 
I used the [Make](www.make.com) no-code platform to automate the daily export of data from Fitbit to Airtable database. Here is a screenshot of the Make scenario that does that:

![Fig 4](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot from 2024-02-10 21-09-33.png)

It was pretty easy to setup. In ideal world I would prefer to use this solution for automating pulling of data from all the data sources. Unfortunately I found that even for those data sources where and API exists, the authentification protocols have idiosyncrasies that I have difficulty to fulfill with the Make tools. Early on I was able to also use it to access the Withings data, but not since their last change of API. I am far from an expert on Make and web authentication, so it is possible one can actually make this work. Feel free to let me know if you managed :-). Make costs me roughly 10$ per month to run. 
Unfortunately Fitbit doesn't provide access to few key variables, notably Fitbit Sleep Score in their API, and I have to track these manually (see bellow).

### Polar & Withings
I use Polar H10 belt whenever I run and Withings Body Scale and BP monitor daily. Both Polar and Withings provide REST API. Unfortunately I wasn't able to get the authentication for these working on Make so I was left with coding it in Python. I run the code that pulls the data daily on a server I rent in the cloud, that also runs the Telegram bot. The server costs me about 10$ per month to rent.

### Habits, Supplements, Nutrition, Medication, Exercise (other than running), HRV, Blood tests
Unfortunately, for all these categories I haven't yet found satisfactory way of automated data insertion, and so I insert them directly into the tables via the AirTable website. I have developed a routine that every evening I sit down to computer for about 10-15 minutes and enter all the data into the AirTable tables. I find this way rather efficient and so I am able to track about 200 variables using this allotted time (note that on most days I need to insert only about 15-30% of the manually tracked variables this way).

## The central database

I have decided to use Airtable as the central database, due to the combination of great user interface that allows for efficient manual insertion and inspection of data, which is essential for a system that will rely at least partially on manual data entry and is constantly evolving, and availability of powerful API for both automated read and write operations.

For convenience, the data is split into multiple smaller Airtable tables, which are linked together via the Date field. They are all concatenated into one large table upon import to the analytical platform. Bellow you can see an example of the table that holds the HRV data:

![Fig 5](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot from 2024-02-11 20-06-18.png)

An important feature is the Metadata table, that holds various information about the individual tracked variables, that facilitate automated analysis of the data:

![Fig 6](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot from 2024-02-11 20-10-36.png)

## The analytical platform
The analytical platform is written in Python using numpy, scipy libraries for data analysis, and pandas DataFrames for data representation. The user interface is written in [Bokeh](http://bokeh.org/) library, which allows rapid development of user interface and visualization of data using web technology directly in Python.
The app is organized into multiple tabs, each offering different inspection or analysis of data. Let me now briefly introduce each of them:

### Exploratory paired analysis tab

![Fig 7](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot from 2024-02-11 20-53-44.png)

This tab allows for elementary data inspection. User can pick two variables. At the top user will see the plot of the two variables over time on a common time axis allowing for inspection of temporal relationship. User can also use filter to smooth the data, or perform basic analysis that assumes accumulation of a given intervention (think for example that vitamin levels gradually accumulate in the body due to its supplementation, before reaching certain level). User can also zoom into a certain time period of the data. User can also shift data by one day in either direction - this is a very common requirement when inspecting data as for example supplements taken on previous day can impact the sleep quality that is recorded on the day after.

In the bottom left part of this tab, the user sees a scatter plot of the two variables and crucially also the Pearson correlation: 
![Fig 8](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot from 2024-02-11 21-04-03.png)

Note that in this case the time points look like 'sitting on trajectories' due to the Gaussian smoothing filter that is switched on for both variables. On the bottom right, the user can see the cross-correlation between the two variables, that can reveal a delayed relationship between the two variables.


### Semi-automated correlation analysis tab

![Fig 9](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot from 2024-02-11 21-05-02.png)
This tab allows for semi-automated data analysis based on simple Pearson correlations. Essentially, for all pairs of variables Pearson correlation is calculated and the results are displayed in one large table. User can filter the results in the table by restricting entries only to those that pass certain statistical significance threshold (p-value provided by the Pearson correlation). User can also restrict the table only to relationships which contain predefined variable. Finally the user can sort the table based on the statistical significance, or the correlation coefficient to easily spot the dominant relationships. To add to the nuance, the correlation is calculated not only for unshifted data but also when the data in the given pair is shifted by one day in each direction relative to each other. The shift with the highest correlation is then reported. There is also a button the lets me quickly switch to exploratory paired analysis of the given pair of variables.

Finally, it is reasonable to assume that a common non-linear relationship between variables will be due to accumulation of the impact of certain interventions, such as the aforementioned accumulation of some supplemented molecule over time. To take this into consideration, for each pair of variables A and B, I also perform correlation between B and transformation of the variable A, where for a given time-constant T days calculate the accumulated variable A. I do this for all the pre-specified time constants (2,4,8,16,32,64,128,256 days) and also where I instead accumulate variable B and correlate it with A. The results of this accumulation analysis (in the form of resulting pearson correlations) are then listed in additional columns of the table, and user can sort the table based on them.

### Relationship tab

Many relationships between variables are trivial, and would clog the automated analysis as they would constantly pop out as the most significant relationships, even if they are uninteresting. A perfect example is a Fitbit Sleep Score vs. Deep Sleep duration, as the FSS formula uses deep sleep, and hence the two are highly correlated. To address this issue, I allow user to keep a list of variables to ignore. This tab allows user to inspect the ignore list, and add or remove relationships from it.

<!-- In fact, I have two levels a 'black list' and 'ignore list' where the former are variables that make no sense to even inspect, like the FSS example, while the second list are relationships that I am aware of, but are unsurprising, and I do not want to see them in the results most of the time.> <-->


### Blood tests tab
This tab allows me to track the evolution of my blood biomarkers. I take blood panels about every 2-3 month. In this panel I can pick a category of biomarkers, and then see in a table how all the biomarkers that belong to the category evolve in time. I have compiled from literature the normal (marked as yellow) and crucially also the optimal ranges (marked as green), defined as the range within which the given biomarker level predicts lowest all-cause mortality.

![Fig 10](https://github.com/lazarulong/quantified-longevity/blob/master/assets/images/posts/tracking_system_implementation/Screenshot from 2024-02-14 09-30-56.png)


## Under development
Few more tabs are under development:
* I am developing event-based analysis that will be able to detect the impact of low-frequency interventions that cause a step change to other biomarkers (think of a single, or occasional, short course of senolytics that cause improvement of some aspect of the aging process). Such relationships are difficult to detect through simple correlations. 
* I am developing a multivariate analysis in the form of a novel machine-learning model that will be able to better detect the interactions of multiple interventions and their impact on the aging process.
* I hope in future to apply more rigorous techniques from the domain of causality detection to advance my analysis from testing association to testing causation.

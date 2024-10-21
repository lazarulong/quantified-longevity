# Sleep efficiency

A major influence on both subjective perception of quality of sleep as well as fitbit sleep score is the overall length of the sleep. Unfortunately, as much as I try to get about 7.5 and half hours of sleep a night, being disciplined going to the bed early has been an issue throughout my life, and am still failing at having truly consistent sleep schedule. Whats worse, my sleep habits fluctuate significantly over relatively long time scale, depending on the season and general stress levels. This major variable impact sleep might thus confound the impact of various interventions on sleep. 

One way of controlling it is to instead of looking at the overall sleep quality is to look at variables that indicate the quality of the sleep, not matter how long it was. I have at least 
two such variables available.

1. Sleep efficiency, which indicates what percentage of the in bed time I spent asleep.
2. Tossing & turning, which is a Fitbit reported variable indicating how restless the sleep was.

In this blog I will investigate what other tracked variables are associated with these two sleep efficiency proxies.

## Vitamin D and Glycing improve sleep efficiency 

Interestingly I observe very strong correlation between the amount of vitamin D and glycine that I supplement and 
the sleep efficiency. This is particularly visible by local smoothing of the data, bellow I am showing the vitamin D
relationship, but the pattern looks very similar for glycine:

![alt]({{ site.url }}{{ site.baseurl }}/assets/images/posts/sleep_efficiency_and_tossing_and_rurning/vitd.png)

## Strength training seems to worsen my sleep efficiency

I also discovered a rather interesting patterns where strength training seems to have negative impact on my sleep efficiency, but cardio has not impact:



## 	Systholic blood pressure is positively associated with tossing & turning

I observe that on the days when I experience more tossing and turning I also tend to have slightly
higher systolic blood pressure. I almost always measure it in the evening after I get to bed. 
Unfortunately, in this case, I have no idea in which direction the causality might be pointing in,
but I thought this is an interesting observation. Perhaps there is a common factor such as stress or large amount of exercise that both increases the blood pressure and restlessness during the night.

![alt]({{ site.url }}{{ site.baseurl }}//assets/images/posts/sleep_efficiency_and_tossing_and_rurning/UC_sleep_efficiency_and _tossing_and turning/TT_BPSys.png)

## Magnesium malate is positively associated with tossing & turning

Rather surprisingly, magnesium malate seems to be increasing the restlessness of my sleep (R=1.6; p<0.0001). This is rather unexpected, as generally magnesium tends to be hyped
as a sleep enhancing element. This corroborates my other finding, I have posted in earlier blogs, that at least for me, magnesium threonate, often explicitly sold as a sleep remedy has no positive impact on my sleep according to my data. 

## Consumption of tomatoes is positively associated with tossing & turning

Another pretty surprising positive association between the level of restlesssnes at night are tomatos (R=0.15;p<0.01). This is inline with my earlier observation that the overall sleep quality (as assed by the Fitbit sleep score) is also negatively impacted by the consumption of tomato sauce. 
I now checked, and indeed the FSS is also negatively impacted by consumption of tomatoes, but less
strongly than specifically the tossing & turning variable.

![alt]({{ site.url }}{{ site.baseurl }}//assets/images/posts/sleep_efficiency_and_tossing_and_rurning/tomatos.png)

## Walked distance reduced restlessness 

Perhaps unsurprisingly, the distance I walk on the given day seems to be positively associated with the quality of my sleep, reducing the tossing and turning (R=-0.12;p=0.02).

##
 
<!-- 
TODO

TT -> Ultra processed food
TT -> Camomile tea
-->


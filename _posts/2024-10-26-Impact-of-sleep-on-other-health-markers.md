Here I will examine how does sleep quality effect my other health markers. We will take it one marker at a time.


## Diastolic blood pressure

About twice a week I measure my blood pressure in the evening. If found that there is a significant negative correlation between my fitbit sleep score on the night before and my diastolic blood pressure in the evening (R=-0.15;p<0.005). I find it interesting that the positive effect of sleep for lowering blood pressure can still be seen in the data on the following evening.

## Sedentary minutes

This is only a indirect health impact, but I was very surprised how strong this relationship is and so I wanted to report it here. I found out that on days when I sleep less well I am much more likely
to sit around a lot (R=-0.25; p<0.0001), which of course is unlikely to be good for my health. I was never consciously aware of this, making the size of this effect (note this is one of the strongest correlation between sleep and any of the other tracked variables) even more shocking for me. 


![Fig 1](/assets/images/posts/sleep_impact_on_ohter_health_markers/sedentary_minutes.png)


I want to emphasize that the opposite relationship does not hold, if I sit a lot on the given day, my sleep is not statistically worse than on days when I sit a little:

![Fig 2](/assets/images/posts/sleep_impact_on_ohter_health_markers/sitting_to_fss.png)

Note that the latter correlation is calculated with the data for the two variables shifted by one day in time.

## Surprising absence of effect: fasting glucose

Every morning I measure my fasting glucose with a standard finger prick glucometer. I do it immediately upon getting up from bed. I wipe out the first blood drop and test only the second one, but I only take one measure every morning. 

Here is how my fasting glucose correlates with sleep markers:

|                   |  Fasting Glucose              |
|-------------------|-------------------------------|
|Fitbit sleep score |  R=-0.06 (p=0.91)             |
|Total sleep time   |  R=0.00 (p=0.94)              |
|Tossing & turning  |  R=-0.04 (p=0.67)             |

As we can see, the quality of sleep does not influence my fasting glucose, which is somewhat surprising because multiple studies suggest that sleep quality can influence glucose metabolism [1]. For example, one can imagine that cortisol levels upon waking would be linked to the quality of the sleep, and hence glucose levels to the sleep quality. Nevertheless I cannot confirm these findings in my N=1 experiment. 


[1] Knutson KL. Impact of sleep and sleep loss on glucose homeostasis and appetite regulation. Sleep Med Clin. 2007 Jun;2(2):187-197.

<!-- 
TODO

Weight and FSS
FSS -> Lymphocytes
FSS -> RBC DW
FSS -> ALT
FSS -> AST
FSS -> Hematocrite
-->


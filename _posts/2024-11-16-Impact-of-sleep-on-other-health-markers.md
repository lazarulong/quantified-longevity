Today I will examine how does sleep quality impact my other health markers. We will take it one marker at a time.


## Diastolic blood pressure

About twice a week I measure my blood pressure in the evening. I found that there is a significant negative correlation between my diastolic blood pressure I measure in the evening and the Fitbit Sleep Score from the previous night (R=-0.15;p<0.005). I find it interesting that the negative effect of poor sleep on blood pressure can still be seen in the data on the following evening.

## Sedentary minutes

This is only an indirect health impact, but I was very surprised how strong this relationship is and so I wanted to report it here. I found out that on days following poor sleep at night I am much more likely
to sit around a lot (R=-0.25; p<0.0001), which of course is unlikely to be good for my health. I was never consciously aware of this, making the size of this effect (note this is one of the strongest correlation between sleep and any of the other tracked variables) even more shocking for me. 


{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/sleep_impact_on_ohter_health_markers/sedentary_minutes.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Sedentary minutes following day vs. FSS at night" %}

The opposite relationship does not hold. If I sit a lot on the given day, my sleep is not statistically worse than on days when I sit a little, which I was also quite surprised
to find given that exercise should generally improve sleep:

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/sleep_impact_on_ohter_health_markers/sitting_to_fss.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Sedentary minutes prior day vs. FSS at night" %}

That said, I did notice that often on days where I have a lot of excercise, including a lot of walking I do have trouble falling a sleep, which might explain this latter lack of relationship, 
as the positive effects of moderate exercise on sleep cancel out with the days when I exercise a lot. 

Note that the latter correlation is calculated with the data for the two variables shifted by one day in time. 

## Surprising absence of an effect: fasting glucose

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


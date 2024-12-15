A major influence on both subjective perception of quality of sleep as well as Fitbit sleep score is the overall length of the sleep, as I've shown in this previous post. Unfortunately, as much as I try to get about 7.5 and half hours of sleep a night, being disciplined and going to the bed early has been an issue throughout my life, and I am still failing at having truly consistent sleep schedule. Whats worse, my sleep habits fluctuate significantly over relatively long time scale, depending on the season and general stress levels. Thus the sleep length, which impacts sleep in a major way, might confound the impact of various other interventions on sleep which improve its quality but not necessarily length which is mostly determined by my discipline.

One way of controlling for this is to instead of looking at the overall sleep score, look at variables that indicate the quality of the sleep, not matter how long it was. I have at least two such variables available:

* Sleep efficiency, which indicates what percentage of the in bed time I spent actually asleep.
* Tossing & turning, which is a Fitbit reported variable indicating how restless the sleep was.

In this blog I will investigate what other tracked variables are associated with these two sleep efficiency proxies.

## Sleep efficiency

### Getting up late on a given day predicts poor sleep efficiency on following night

Perhaps not surprisingly, the strongest predictor of sleep efficiency is when do I get up from bed the preceding day (R=0.2;p<0.0001;N=505). The later I get up 
the worse sleep efficiency I observe on the following night, underscoring how important a regular sleep schedule is, and high futile it is to try to 'catch up on your sleep'. 
In this case I am confident about the causal link because shifting the data just by one day either way completely removes the correlation.

### Breathing rate vs sleep efficiency

A rather interesting association I found is between breathing rate during sleep and sleep efficiency, with higher breathing rate predicting worse sleep efficiency. It is particularly visible 
after smoothing the data with kernel of about two days: 

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/sleep_efficiency_and_tossing_and_turning/BreathingRateVsSeelEfficiency.png{% endcapture %} {% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Breathing rate vs. sleep efficiency" %}

First I thought this could be just a confound of being sick from time to time, which is typically associated with faster breathing and worsened sleep quality but inspection of the data show that 
association being there also during periods of being healthy. Another confound I suspect was seasonality with perhaps fasting breathing during peak summer due to the increased temperature in the 
bedroom, but this also turned out not to be the case. My main current theory is that stress is the common factor, increasing breathing rate during sleep, but decreasing its efficiency. 

### Vitamin D and Glycine improve sleep efficiency

Interestingly I observe positive associate between the amount of vitamin D (R=0.1;p=0.009;N=630) and Glycine that I supplement and the sleep efficiency. This is particularly visible by local smoothing of the data, bellow I am showing the vitamin D relationship, but the pattern looks very similar for Glycine:

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/sleep_efficiency_and_tossing_and_turning/vitd.png{% endcapture %} {% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Vitaming D vs. sleep efficiency" %}


## Tossing & turning

### Ginger reduces tossing and turning

I occasionally mix some (about 10g) of raw ginger into my morning smoothies. Interestingly, ginger in my smoothies turned out to be the strongest association in my data with 
the Fitbit tossing & turning indicator (R=-0.24;p<10^-15;N=598):

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/sleep_efficiency_and_tossing_and_turning/Ginger_vs_TT.png{% endcapture %} {% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Ginger vs. Fitbit tossing & turning" %}

### Blueberries reduces tossing and turning

Another occasional ingredient of my smoothies is blueberries, and they also seem to have strong negative association with Fitbit tossing & turning indicator (R=-0.21;p<10^-8;N=603). I did check and my consumption
of blueberries and ginger are not correlated other than both are usually part of my smoothies (but most of the time not at the same time), but I do not find a significant correlation between my smoothie consumption overall and the tossing & turning. Also there are plenty of other ingredients that are part of my smoothies, many of them a lot more frequent, and none of them seems to have a strong association with tossing & turning, which increases my confidence that it is specifically these two plants that have positive effect.

### Systholic blood pressure is positively associated with tossing & turning

I observe that on the nights when I experience more tossing and turning I also tend to have slightly higher systolic blood pressure just before going to sleep (R=0.16;p=0.01;N=233). I almost always measure it in the evening after I get to bed. Unfortunately, in this case, I have no idea in which direction the causality might be pointing in, but I thought this is an interesting association. Perhaps there is a common factor such as stress or large amount of exercise that both increases the blood pressure and restlessness during the night.

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/sleep_efficiency_and_tossing_and_turning/TT_BPSys.png{% endcapture %} {% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Systolic blood pressure vs. Fitbit tossing & turning" %}


### Number of steps in a day impacts tossing & turning

Another very clear positive impact on quality of sleep is the number of steps I take on a day, the more the better (R=-0.16;p<0.0002;N=676):

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/sleep_efficiency_and_tossing_and_turning/StepsVsTossingTurning.png{% endcapture %} {% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Steps vs. Fitbit tossing & turning" %}

The causality here also seems to be very clear, with shifting of the data just by one day completely abolishing the association. 

### Magnesium malate is positively associated with tossing & turning

Rather surprisingly, magnesium malate seems to be increasing the restlessness of my sleep (R=0.16; p<0.0001;N=708). This is rather unexpected, as generally magnesium tends to be hyped as a sleep enhancing element. This goes along with my other finding I have posted in earlier post, that for me Magnesium Threonate, often explicitly sold as a sleep remedy, has no positive impact on my sleep according to my data.

### Consumption of tomatoes is positively associated with tossing & turning

Another pretty surprising positive association between the level of restlessness at night are tomatoes (R=0.15;p<0.01). This is inline with my earlier observation that the overall sleep quality (as assessed by the Fitbit sleep score) is also negatively impacted by the consumption of tomato sauce. Interestingly the FSS is less strongly affected by the tomato consumption than the tossing & turning variable, indicating that it is specifically this component of sleep score that is them mediating factor.

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/sleep_efficiency_and_tossing_and_turning/tomatos.png{% endcapture %} {% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Tomato consumption vs. Fitbit tossing & turning" %}

<!--

TODO Now Glucosamine Chondotrin

Walked distance reduced restlessness
Perhaps unsurprisingly, the distance I walk on the given day seems to be positively associated with the quality of my sleep, reducing the tossing and turning (R=-0.12;p=0.02).


-->
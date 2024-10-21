# On which sleep quality variables to track 

I've been tracking multiple variables that should reflect the quality of sleep.
Here, I will examine relationships between them, and determine a subset that seems to best reflect the restorative quality of the sleep. In future posts, I will narrow my focus on variables in this subset and correlate them to other tracked variables to determine what factors influence my sleep.

## Subset of sleep quality variables I track

* Fitbit sleep score (FSS) \[score 1-100\] (Fitbit Inspire)
* Subjective sleep quality (SSQ) \[score 1-10\] (Manual tracking in the evening directly into AirTables)
* Restorative quality of sleep (RQS) \[score 1-5\] (Manual tracking as a part of survey from Telegram bot)
* Total sleep time (TST) \[duration in min\] (Fitbit Inspire)
* Light sleep (LS) \[duration in min\] (Fitbit Inspire)
* Deep sleep (DS) \[duration in min\] (Fitbit Inspire)
* REM sleep (RS) \[duration in mi n\] (Fitbit Inspire)
* Tossing & turning (TT) \[%\] (Fitbit Inspire)

## The two subjective sleep quality measures SSQ & RQS vs. the Fitbit (FSS)

<!-- note that in my data RQS 1-best 5-worst - here I switch it so that it gives the same sign of correlation as FSS. For FSS it is the other way around. -->

First let me explain what SSQ and RQS mean. As I described in previous blog, I have setup automatic service that sends me a poll every morning with pre-defined set of questions with the goal of monitoring my subjective assessment of sleep. The very first key question is how restorative I feel the sleep last night was - this is the RQS quality. Whereas SSQ I usually fill in at the end of the day, and it should reflect how well I feel I slept. Note that this is meant to be overall assessment reflecting how long I slept and how much I was waking up, unlike the RQS which reflects the momentary feeling 
of how well slept I woke up.

Here are the correlations between the two subjective measures and the Fitbit sleep score (FFS):

* Pearson correlation of SSQ vs. RQS: R=0.79 (p<0.001; N=709)
* Pearson correlation of SSQ vs. FSS: R=0.69 (p<0.001; N=826)
* Pearson correlation of RQS vs. FSS: R=0.59 (p<0.001; N=602)

As you can see, the two subjective measures (SSQ & RQS) are highly correlated,
yet there are not in a perfect alignment.  
We can see that the Fitbit FSS agrees well with both measures, but is correlated more with the SSQ than RQS. I find this encouraging as of two subjective measures, SSQ in my opinion better reflects the overall quality of the sleep, because it is not just reflection of the momentarily feeling of restfulness upon waking up (the RQS) which can be influenced by factors such as in what sleep stage I was woken by the alarm. 

The main conclusions:

1. Subjective tracking of sleep can be challenging, as even the time at which the subjective sleep assessment is made has impact on the reported quality.
2. The Fitbit sleep score reflects well the overall subjective feeling of sleep quality in the following day.

## Do the SSQ, RQS and FSS translate into feeling more energetic during the day

I have been also tracking the overall feeling of energy on the given day, that I enter in the evening. Here are the correlations of SSQ, RQS and FSS with it:

* Pearson correlation of SSQ vs. Energy: R=0.46 (p<0.001; N=996)
* Pearson correlation of RQS vs. Energy: R=0.36 (p<0.001; N=741)
* Pearson correlation of FSS vs. Energy: R=0.3 (p<0.001; N=860)

The main conclusions:

1. Energy is moderately correlated with all the three sleep quality measures. The best correlation is with SSQ which could be due to the fact that I capture SSQ and Energy at the same time - in the evening, and the subjective feeling of these 
two is probably highly related.
2. The Fitbit assessment of sleep quality is predictive of my subjective feeling of energy on the given day. I am somewhat surprised that the FSS doesn't correlated more with feeling of Energy, but obviously there are many other factors impacting that. 
3. I am also somewhat surprised that the RQS (taken in the morning) correlated better with overall Energy during the day (assessed in the evening) than FSS, indicating that the subjective measures are still better

## Sleep stages and total sleep time

Fitbit Inspire also provides the duration of the three basic sleep stages: REM, Light, and Deep and their sum - the total sleep time (TST). Let's have a look at the baseline characteristics of these three variables.

I had about 265 min of Light sleep, 87 min of REM sleep, and 67 min of Deep sleep per night over the last roughly 3 years, and this seemed to have been fairly stable over time (Fig 1,2,3). My total sleep time was about 7:25 per night (Fig 4), which is roughly in line with my goal. Where I, however, have substantially shortcoming is the compOstion/quality of my sleep, but I will come back to this in future blogs.

![alt]({{ site.url }}{{ site.baseurl }}/assets/images/posts/basic_sleep_characteristics/Light_sleep.png)
![alt]({{ site.url }}{{ site.baseurl }}/assets/images/posts/basic_sleep_characteristics/REM_sleep.png)
![alt]({{ site.url }}{{ site.baseurl }}/assets/images/posts/basic_sleep_characteristics/Deep_sleep.png)
![alt]({{ site.url }}{{ site.baseurl }}/assets/images/posts/basic_sleep_characteristics/Total_sleep_time.png)


For now let us look at the relationship between these sleep components and the 
subjective measures. Does any of these correlated better with SSQ, RQS, or the perceived Energy in the following date (I deliberately ignore FFS here as Fitbit uses sleep stages to calculate it)?


|             |  SSQ              |  RQS              |  Energy           |  
|-------------|-------------------|-------------------|-------------------|             
|Light sleep  |  R=0.4 (p<0.01)  | R=0.39 (p<0.01)   | R=0.11 (p<0.01)   | 
|REM sleep    |  R=0.4 (p<0.01)  | R=0.39 (p<0.01)   | R=0.07 (p=0.03)   |
|Deep sleep   |  R=0.44 (p<0.01)  | R=0.44 (p<0.01)   | R=0.15 (p<0.01)   |
|TST          |  R=0.64 (p<0.01)  | R=0.62 (p<0.01)   | R=0.19 (p<0.01)   |


We can see that consistently, the strongest predictor for all the three sleep quality measures is total sleep time. Of the three sleep stages, the strongest predictor is Deep  sleep. REM and light sleep show similar weakest predictive power (although not much weaker for RQS and SSQ). It is encouraging to see that the Fitbit sleep score is better predictor of the overall feeling of Energy on the given day, than any of the individual sleeping components.

The main conclusions:

1. Total sleep correlates best with my subjective perception of sleep quality or feeling of energy during the day.

2. Of the sleep stages, the most important seems to be Deep sleep, but not by a large margin over the other two components.

## Tossing & Turning	

As a part of the component Fitbit sleep score, Fitbit calculates the Tossing & Turning (TT) score. In day to day experience, I had an impression that TT seems to correlate well with how rested I feel on the given day. Let's have a look what the data says:

|                  |  SSQ              |  RQS              |  Energy           |  
|------------------|-------------------|-------------------|-------------------|             
|Tossing & Turning |  R=-0.423 (p<0.01)  | R=-0.349 (p<0.01)   | R=-0.248 (p<0.01) | 

RQS is less well correlated with TT than SSQ but both show moderate correlation. Interestingly, TT is better correlated with Energy than any of the sleep stages but also total sleep time. But again note that FSS is yet a bit more correlated with Energy at R=0.3 (see earlier tables).

Since TT is itself a component of FSS this indicates that TT is the most informative component of FSS in terms of predicting energy on any given day. It also means that improving this component might have particularly positive effect on my well being. Hence, I will be paying attention to TT in future analysis, and look for interventions that impact it. 

## Sleep efficiency

As we can see, so far the strongest correlates with the subjective feeling of being well rested and having a lot of energy on the given day was the composite Fitbit Sleep Score but note that Total Sleep Time and Tossing & Turning were close. Total Sleep Time is an important component of FSS, and my data indicate that the overall duration of sleep is what matters most for my feeling of restfulness. But note, that Tossing & Turning shows strong correlation with Energy indicating that the quality of sleep shouldn't be discounted.

Currently, I dedicate about 8.0 hours to sleep each day, from which I get on average 
about 7.5 hours of actual sleep. I am busy person and so I don't like the idea of extending this time even further to increase sleep benefits. Furthermore recent research indicates
that too long sleep is also not good [1](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2864873/).

 I am thus interested whether improving the sleep efficiency could be a way to feel more rested. In principle, I can think of two ways to improve sleep efficiency. One is to simply stay less awake during the night. The second is to lengthen the Deep and REM sleep stages that were shown  (in line with my personal data - see above) to be more important then light sleep in recharging the body.

I thus constructed following two sleep efficiency scores that I want to explore here:

* Sleep Efficiency (SE) = (1-Awake/Asleep)*100 where Asleep is the sum of the three sleep stage durations
* Sleep Stage Efficiency (SSE) = (REM Sleep + Deep Sleep)/(REM Sleep + Deep Sleep + Light Sleep)*100
 
Let's have a look how do these two scores correlated with SSQ, RQS and Energy. For a good measure, let's also add Awake duration as measured by Fitbit into the mix.

|                       |  SSQ              |  RQS              |  Energy            |  
|-----------------------|-------------------|-------------------|--------------------|             
|Awake                  |  R=-0.06 (p=0.06) | R=0.01 (p=0.7)   | R=-0.10 (p<0.01)   | 
|Sleep Efficiency       |  R=0.32 (p<0.01) | R=0.21 (p<0.01)   | R=0.15 (p<0.01)   | 
|Sleep Stage Efficiency |  R=0.22 (p<0.01) | R=0.22   (p<0.01)     | R=0.06 (p=0.09)   |

As we can see, just measuring the amount of Awake time (at least with the accuracy) that Fitbit achieves is a surprisingly poor predictor of the sleep outcomes, although there is a small but significant negative correlation to feeling of Energy. Interestingly, the fraction of sleep one spends in REM or Deep sleep (the SSE) is a bit better predictor how rested I feel next day, but it does not predict how energetic I feel. Finally, the fraction of the night I spend not sleeping seems to offer better predictive power than Awake and Sleep Stage Efficiency, but still trails significantly behind the Fitbit sleep score, Total sleep time, and the Tossing & Turning. This does not directly prove, that increasing sleep efficiency would have no value, but indicates 
the gains would be modest, and I am better of optimizing directly Fitbit Sleep Score or specifically the Tossing and turning component.

## Overall conclusion


* The Fitbit FSS is the best predictor of me feeling energetic next day, and is well correlated with my subjective feeling of sleep quality, indicating that I should keep using it as the primary objective automatically tracked marker of sleep quality going further. 
* While REM and Deep sleep duration does contribute to the FSS, as does the amount of Awake time during night, we see that on their own they are poorly correlated with my subjective feeling of restfulness. This indicates to me that while some small benefits from increasing REM or Deep sleep can potentially be made, focusing on them is unlikely to give better results in terms of feeling well rested and energetic.
* but I will still try to focus on reducing the Awake time for the simple reason that it would allow me to reduce the amount of time I dedicate to sleep without compromising its benefits.
* It should be emphasized none of these conclusions imply that improving sleep quality could have other health benefits. Correlations of sleep parameters with other health parameters remain to be explored.

Plenty has been written on the importance of sufficient high quality sleep on health and longevity. In this post we will look at factors that impact quality of my sleep measured as the Fitbit Sleep Score (FSS) that I have identified as the best automatic correlate of my subjective feeling of sleep quality in the [previous post](https://www.quantifiedlongevity.org/Basic-sleep-characteristics/). Let's go.

## Alcohol

Rather unsurprisingly the single most negatively impacting intervention on my sleep is Alcohol (R=-0.2; p=1.6^-9): 


{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/what_influences_my_sleep/Screenshot from 2024-02-17 20-19-48.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Alcohol vs. FSS" %}

I track the amount of alcohol I have consumed on the given day in units where 1 unit correspond roughly to a small beer or 1.5 dl glass or wine. 
It is worth pointing out that even the smallest tracked amount - one unit (i.e. a small beer) already has a discernible negative impact.

## Sour cherry
I've been testing adding sour cherry (frozen) into my smoothies due to several potentially positive impacts, particularly for increasing dietary nitrates, helping exercise recovery, and reducing uric acid. Surprisingly, I am also detecting a mildly positive impact on my sleep:

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/what_influences_my_sleep/Screenshot from 2024-02-17 17-05-59.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Sour cherry vs. FSS" %}

The effect is small but highly significant (R=0.16; p=0.0083). The correlation completely disappears if I shift the data just by one day, which further increases my confidence this is a real effect. Interestingly, there are actually studies showing the positive effect of sour cherry juice on sleep \[[1](https://pubmed.ncbi.nlm.nih.gov/20438325),[2](https://www.cdc.gov/sleep/index.html)\]. It is worth noting that I typically have (a lot) less than 100g of the frozen cherries in my smoothie (I don't weigh them every day) and drink the smoothie before 12 am which indicates that greater impact could be gained by increasing the dose and ingesting them in the evening, as in the studies.

## Tomato souce

I am logging how much fresh tomatoes as well as tomato sauce I eat (only qualitatively - 'none', 'a little', 'a lot') on the given day. I started to do this because I had a suspicion that either tomatoes 
or tomato sauce cause heavy stomach and consequently poor sleep. To my surprise, after collecting the data for about a year, I indeed find that consumption of both tomato sauce (R=-0.14;p<0.02) and fresh tomatoes (R=-0.12; p=0.03) is negatively correlated with my fitbit sleep score. Because my tomato/tomato sauce consumption is pretty random (especially for the tomato sauce) and relatively infrequent I am fairly confident that this is not just a spurious correlation.

## Cider vinegar
Another rather surprising relationship I discovered is that cider vinegar, that I put on my salads, is also slightly correlated with the quality of my sleep (R=0.123,P=0.003). Bellow you can see the small effect:

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/what_influences_my_sleep/Screenshot from 2024-02-17 19-23-41.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Cider vinegar vs. FSS" %}

Note that very occasionally I have two such salads a day, which leads to having two tablespoons of cider vinegar on that day, but there were so far too few occasions of that leaving the error bars large. The relationship is weak, but I noticed that it is stable over time - i.e. if I look at both the first and last year of my tracked data I find the same effect in both, which makes me believe it is real.

One important confounding factor could be that I always have cider vinegar with salad, so it could be some of the other salad ingredients. The reason why I am fairly sure it is the cider vinegar is, that sometimes I put balsamic vinegar instead. Surprisingly, if I look at the correlation between salad consumption and sleep there is a negative correlation:

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/what_influences_my_sleep/Screenshot from 2024-02-17 19-30-19.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Salad consumption vs. FSS" %}

Given that I am not aware of any other ingredient systematically changing between the salads I consume with cider vinegar vs. balsamic vinegar, a conclusion at hand is that the latter has actually negative impact on my sleep. I find this rather perplexing and intend to look into this further.

Finally, I was surprised to find an internet full of claims that cider vinegar before bed helps sleep (none sufficiently reputable that I would like to link them here), but no proper scientific study that tried to test this, which is probably why this possibility was off my radar. If you know of a proper study looking into this, let me know!

## Hyaluronic Acid

The third - and also unexpected - positive intervention seems to be Hyaluronic Acid, with (R=0.123; p=0.004). I will admit that this one is particularly surprising and relatively weak so I will be monitoring it in the future if the correlations holds up. I was off Hyaluronic acid for a while now, so I will reintroduce it to further test this unexpected relationship. It could be that I just happened to sleep slightly worse lately, while off the Hyaluronic acid, which could create this spurious correlation.


## Ultra-processed food

While I try to avoid it as much as possible, it still happens from time to time that I eat some ultra-processed food. Interestingly, even with such low frequency I can still clearly see the negative impact on
my sleep the following night:

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/what_influences_my_sleep/ultra_processed_food_vs_sleep.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Ultraprocessed food vs. FSS" %}

## The surprising absence of effects.

Perhaps the most surprising findings are actually the lack of relationship between Fitbit sleep score and several interventions specifically aimed at sleep. I supplement quite regularly (before sleep) with Magnesium Threonate which is supposed to improve sleep, but I cannot see any indication of this having a positive impact in my data whatsoever.

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/what_influences_my_sleep/Screenshot from 2024-02-17 20-55-19.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Magnesium Threonate vs. FSS" %}


Likewise, I supplement lithium orotate before sleep, not specifically for sleep, but for overall moods stabilization, and the putative longevity effects, but I had the expectation it should also have a positive impact on sleep, which it does not seem so. Another supplement I tested that is hailed for its sleep improving effects is phosphatidylserine, that should have cortisol lowering effects, and hence should improve sleep, yet I cannot find evidence for this in my data at all as well.

I will disclose that I am also testing L-theanine as sleep enhancer, but for now the data are not conclusive enough for me to report it. Stay tuned.

## Conclusion

I am generally drinking rather little alcohol. On average perhaps one beer or glass of wine a week during social occasions at most, so I am not going to change anything about alcohol consumption, as the number of nights where I would reap the small benefit of not drinking the small amount doesn't justify the inconvenience.

However, I do plan to replace balsamic vinegar in my salads with cider vinegar, and monitor if the detected positive influence on sleep holds up. Likewise, I will try to increase the frequency of adding sour cherries into my smoothies and monitor the impact, while reducing tomatoes. The negative results for Magtein are rather surprising, and I will need to re-evaluate if to continue with its supplementation, especially as it is quite a pricey. I will first explore if it has any positive impacts on any of the other biomarkers I monitor, and if these will come out negative I will discontinue it.
Finally, both lithium and phosphatidylserine have other impacts, which I will cover in future blogs, which seem to be positive so these findings will not change my usage of them, but I would be curious to understand the lack of effect I found given the widely claimed impacts.

<!-- 
TODO

Chamomile tea, when analysed only around the time I was drinking it seems to have a small positive effect on FSS. Perhaps worth to drink it again an see if it works.
Rhodiola
Ultraprocessed Food -> Tossing and Turning
Blueberries -> Tossing and Turning
-->

I use a standard finger prick strip based glucometer to measure fasting blood glucose, first thing every morning after I enter bathroom. 
I do only one measurement, but I do swipe away the first drop of blood after the finger prick, and test the second drop.

I've been collecting this data for a bit over 3 years on daily basis, although I do frequently miss a day or two, and I have few 
multi-week gaps while staying on longer holidays or running out of test strips without noticing ahead.

This is how the data looks over time:

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/fasting_glucose/base_data.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Evolution of fasting glucose over time" %}

You can see considerable variation, and you can see that I do not unfortunately always stay in the ideal range bellow 5.5 mmol/l. 
Over the time I have also worn CGM a few times, and I learned that I do suffer from a mild dawn syndrome, where imediately upon waking
I have a spontaneous uptick of fasting glucose to about 6.0 mmmol/l. Most of these finger prick tests unfortunatelly measure
this up-tick, however I do believe looking at which interventions lower the morning readings is still quite valuable.
Nevertheless, I will write about my CGM experience in a later posts. In this post I will focus on identifying which 
variables impact my fasting blood glucose as measured with the finger prick test in the morning.

## Elemental Magnesium

One rather very surprising but very robust association that turned up is between the intake of elemental magnesium and 
fasting blood glucose (R=0.2;p<1e-10):

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/fasting_glucose/magnesium.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Magnesium vs fasting glucose" %}

This is highly surprising, because if you do just a cursory search on benefits of supplementing magnesium, improved blood 
glucose control is one of the most common claims that shows up. And these actually have a decent backing in clinical 
studies, e.g. [1]. 

Over the years I tried number of different magnesium formulations, and of these the strongest correlation shows up for magnesium
malate, but this is only marginally stronger than the total elemental magnesium intake, making me doubt that this is driven
primarily by any specific formulation.

I have to admit I am rather confused by this finding and I will keep an eye on this relationship going forward to see if it 
remains. 

## Lycopene

I was supplementing Lycopene on an off for last two years, and to my surprise it is rather strongly positively correlated 
with my morning fasting glucose (R=0.21;p<1e-8). 

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/fasting_glucose/lycopene.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Lycopene vs fasting glucose" %}


A cursory look through the literature yields this metanalysis of 15 clinical studies [2], that concludes that 
'lycopene intake exerted an fasting-blood-glucose-decreasing effect', in direct contradiction 
to my findings. There are two obvious options. One is that this is a spurious correlation and not causal, the second one 
is that lycopene has very individual impact on me. Regarding the former, I did some very basic extra tests, like looking
at the correlation in the first and second half of my dataset, and the correlation holds strong for both halves, indicating
that this is not just an effect of some kind of long term trend (a common phenomenon that can cause spurious correlations).  
I am keeping my mind open ragarding this, and will still do at least two rounds of lycopene supplementation. However if 
these confirm the glucose increasing effect, I will discontinue its use and report back.

## Psyllium husk reduces fasting blood glucose

For a change this, one is not that surprising. The ability of fiber, particularly the soluble form, to reduce glucose spikes through
slowing down absorption of carbohydrates is well established. And Psyllium husk si one of the richest sources of it, which is exactly
why I add it to my diet. Interestingly, in my case, I see a small but statistically significant positive effect also directly on my fasting blood glucose levels (R=-0.14;p=0.002): 

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/fasting_glucose/psyllium.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Psyllium vs fasting glucose" %}

The effect is small, the 15g intake that I usually add in my smoothie, reduces the morning fasting glucose by about 0.1 mmol/L the following morning.

## The choice of berries in smoothie and fasting blood glucose

On most days I drink a smoothie. The one ingredient that is always present is a berry, but which exact berry changes. Interestingly,
different berries seem to have quite different impact on my fasting blood glucose. I find that blueberries and 
aronia berry are associated with lower morning fasting blood glucose, while rasberries and strawberries are associated with slight increase.  

I want to emphesize, that these correlations, while strictly speaking statistically significant are relatively weak which means I do not 
trust them fully given the multiple-comparisons issues I have explained in the first blog. That said I find these findings interesting enough 
to report them, and I will keep my eye on them and report back as I gradually collect more data.

## Night breathing rate

Fitbit reports the average breathing rate during my sleep, and I found a rather strong positive association between my 
fasting morning blood glucose and the breathing rate (R=0.18;p=0.0004). Interestingly there is a substantial body off 
literature on the link between diabetes and poor sleep quality, so this link is not completely surprising, but I wasn't 
able to find any content specifically on the nocturnal breathing rate, or study within non-diabetic population. 
The main open question for me is which way does the causality arrow point - does high nocturnal glucose (which impacts 
morning fasting glucose) disrupts sleep, or does good sleep lowers my blood glucose during night that I then detect 
in the morning? I will have to perform more advanced analysis to try to make an informed guess, and will report on this
back.

## References

[1] Veronese N, Watutantrige-Fernando S, Luchini C, Solmi M, Sartore G, Sergi G, Manzato E, Barbagallo M, Maggi S, Stubbs B. Effect of magnesium supplementation on glucose metabolism in people with or at risk of diabetes: a systematic review and meta-analysis of double-blind randomized controlled trials. Eur J Clin Nutr. 2016 Dec;70(12):1354-1359. doi: 10.1038/ejcn.2016.154. Epub 2016 Aug 17. Erratum in: Eur J Clin Nutr. 2016 Dec;70(12):1463. doi: 10.1038/ejcn.2016.209. 

[2] Inoue T, Yoshida K, Sasaki E, Aizawa K, Kamioka H. Effect of Lycopene Intake on the Fasting Blood Glucose Level: A Systematic Review with Meta-Analysis. Nutrients. 2022 Dec 27;15(1):122. doi: 10.3390/nu15010122.

[3] Ilias I, Milionis C, Zabuliene L, Rizzo M. Does Iodine Influence the Metabolism of Glucose? Medicina (Kaunas). 2023 Jan 17;59(2):189. doi: 10.3390/medicina59020189	

<!--
## Water melon consumption

Perhaps unsurprisingly, the strongest positive correlation I observe is that between consumption of water melon and the fasting
blood glucose (R=0.26;p<0.0001). What to me is rather interesting is that the impact of the water melon on my morning fasting glucose 
seems to be much larger than that of added refined sugar that I track as well.


## Iodine potassium reduces fasting blood glucose

I supplement Iodine from time to time in the form of Iodine potassium. I took different dosages over the years. 125 and 30 mg per day.
I found that iodine supplementation is the single most strongly negatively associated variable with my fasting blood glucose (R=0.17; p<1e-7) - certainly not the outcome I would expect.

{% capture image_path %}{{ site.url }}{{ site.baseurl }}/assets/images/posts/fasting_glucose/iodine_vs_FSG.png{% endcapture %}
{% include figure popup=true image_path=image_path alt="this is a placeholder image" caption="Iodine vs fasting glucose" %}

A search on pubmed reveals that link between thyroid function has already been described [3] but a quick dive revealed that the 
interactions are rather complex, so I will refrain from speculating on the potential mechanisms of what I see in my data for now
but I am putting this on my reading list. 

A cursory look through all associations between Iodine supplementation and the rest of my data reveals number of other interesting
links, so expect a dedicated post on Iodine in not to distant future.

-->
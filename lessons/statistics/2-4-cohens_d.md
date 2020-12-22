[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

**Code**

def compare_weights():
    live, firsts, others = first.MakeFrames()
    firsts_mean = firsts.totalwgt_lb.mean()
    others_mean = others.totalwgt_lb.mean()
    cohen_effect = thinkstats2.CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
    return firsts_mean, others_mean, cohen_effect

def compare_preg_length():
    live, firsts, others = first.MakeFrames()
    firsts_mean = firsts.prglngth.mean()
    others_mean = others.prglngth.mean()
    cohen_effect = thinkstats2.CohenEffectSize(firsts.prglngth, others.prglngth)
    return firsts_mean, others_mean, cohen_effect
    
    #compare weight of first and other babies
    print(compare_weights())
    
    #compare pregnancy length of first vs other babies
    print(compare_preg_length())

**Results**
(7.201094430437772, 7.325855614973262, -0.088672927072602)
(38.60095173351461, 38.52291446673706, 0.028879044654449883)

**Explanation**
We can see that the mean weight of first babies is ~7.2 lbs, while the mean 
weight of non-first babies is ~7.3 lbs. So, first babies tend to be slightly
heavier. However, this difference of .1 lbs feels rather insigificant. This
is further confirmed by the Cohen's D effect size of -.09, which is
considered a low effect size, and implying much overlap between the two groups.

Similarly, we observe a small (less than .01 week) difference between the 
pregnancy legth of first babies versus non-firsts. The Cohen's D effect size 
for this comparison is even smaller at .03.

So, because Cohen's D is greater for birth weight than pregnancy length,the
standardized difference in birthweight is greater than the difference in pregnancy
length. We might say that birth order is associated with more variation in birth weight 
than length of pregancy.
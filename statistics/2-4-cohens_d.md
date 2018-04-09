[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> 
```python
import thinkstats2 as ts
import math
import nsfg

def cohens_d(group1,group2):

    diff_mean = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1 = len(group1)
    n2 = len(group2)
    pooled_var = (n1*var1 + n2*var2)/(n1+n2)
    pooled_std = math.sqrt(pooled_var)
    d = diff_mean/pooled_std

    return d

def main():

    preg = nsfg.ReadFemPreg()
    live = preg[preg.outcome == 1]
    firsts = live[live.birthord == 1]
    others = live[live.birthord != 1]
    print(cohens_d(firsts.totalwgt_lb,others.totalwgt_lb))

main()
```
Running this code yields a Cohen's d of -0.088672927072602 standard deviations.
This Cohen’s D effect size illustrates that first born babies are marginally lower in weight, since the mean weight for first born babies is 0.08867 standard deviations lower than that of other babies. While this is a marginal difference, this difference is almost three times greater than the difference observed in pregnancy length between first born babies and other babies, for which the Cohen’s D is 0.029 standard deviations.

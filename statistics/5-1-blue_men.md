[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> 
```python
import scipy.stats

mean_m = 178
sd_m = 7.7

lower_blue_m = 177.8
upper_blue_m = 185.42

cum_upper = scipy.stats.norm.cdf(upper_blue_m,loc=mean_m,scale=sd_m)
cum_lower = scipy.stats.norm.cdf(lower_blue_m,loc=mean_m,scale=sd_m)
percent_in_range = cum_upper-cum_lower

print(percent_in_range)
```
Running the code above produces the result that 34.27% (0.3427468376314737) of the U.S. male population is eligible to join the Blue Man Group.

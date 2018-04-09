[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> 
```python
import random
import matplotlib.pyplot as plt

def pdf(sample,x):

    count = 0.0
    for num in sample:
        if num == x:
            count += 1.0
    prob = count/len(sample)
    return prob

def cdf(sample,x):

    count = 0.0
    for num in sample:
        if x >= num:
            count += 1.0
    cum_prob = count/len(sample)
    return cum_prob

def main():

    random_nums = []
    for num in range(0,1000):
        random_nums.append(random.random())
    random_nums.sort()

    pdf_list = []
    cdf_list = []
    for num in random_nums:
        pdf_list.append(pdf(random_nums,num))
        cdf_list.append(cdf(random_nums,num))

    plt.plot(random_nums,pdf_list,'ro',label='PMF')
    plt.plot(random_nums,cdf_list,'go',label='CDF')
    plt.axis([0,1,0,1])
    plt.xlabel('Random Number Value')
    plt.ylabel('Probability')
    plt.title('PMF and CDF')
    plt.legend()
    plt.show()

main()
```
Running this code will generate the PDF and CDF shown below.

![Image of PDF and CDF](https://github.com/iangfreed/dsp/blob/master/PMFCDFRandomNumbers.png)

The PMF and CDF verify that the numbers random.random generate are uniformly distributed. The PDF shows that the PDF value for each random number is equal, as expected in a uniform distribution. 

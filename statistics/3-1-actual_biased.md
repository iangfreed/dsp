[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> 
```python
import nsfg
import matplotlib.pyplot as plt

def pdf(sample,x):

    count = 0.0
    for num in sample:
        if num == x:
            count += 1.0
    prob = count/len(sample)
    return prob

def mean(values):

    mean = 0
    for key in values:
        mean += key*values[key]
    return mean

def main():

    responses = nsfg.ReadFemResp()
    kids = responses.numkdhh.values
    kids.sort()

    frequency = {}
    unbiased_pdf = {}
    for num in kids:
        if num not in unbiased_pdf:
            unbiased_pdf[num] = pdf(kids,num)
            frequency[num] = 1
        else:
            frequency[num] += 1

    biased_pdf = {}
    normalizing_constant = 0
    for key in unbiased_pdf:
        biased_pdf[key] = key*frequency[key]
        normalizing_constant += biased_pdf[key]

    for key in biased_pdf:
        biased_pdf[key] /= normalizing_constant

    unbiased_mean = mean(unbiased_pdf)
    biased_mean = mean(biased_pdf)

    plt.plot(unbiased_pdf.keys(),unbiased_pdf.values(),'-ro',label='Unbiased PDF')
    plt.plot(biased_pdf.keys(),biased_pdf.values(),'-go',label='Biased PDF')
    plt.axis([0,5,0,0.5])
    plt.xlabel('Number of Children')
    plt.ylabel('Probability')
    plt.title('Unbiased vs Biased PDF')
    plt.legend()
    plt.show()
    print('Unbiased Mean: ',unbiased_mean)
    print('Biased Mean: ',biased_mean)
main()
```
Running this code yields the below graphed unbiased and biased PDFs.

![Image of Biased and Unbiased PDFs](https://github.com/iangfreed/dsp/blob/mast\
er/UnbiasedBiasedPDF.png)

The unbiased Mean is 1.024205155043831 children and
the Biased Mean is 2.403679100664282 children

# Fitting Poisson Distribution
## Aim :
To fit poisson distribution for the given frequencey distribution

image

## Software required :
Python

## Theory:
The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

image

Conditions for Poisson Distribution:

An event can occur any number of times during a time period.
Events occur independently. I
The rate of occurrence is constant.
The probability of an event occurring is proportional to the length of the time period.
Procedure :
image

## Program
```
Developed by
Register Number: 212220230037
Name: R K PRAVEEN
import numpy as np
import math
import scipy.stats
X=[0,1,2,3,4,5,6]
f=[153,169,72,31,12,6,2]
n=6
N=np.sum(f)
mean=np.inner(X,f)/N
Pr=list(); E=list(); xi=list()
print("  X P(X=x) Obs.Fr  Ex.Fre   xi ")
print("----------------------------------")
for x in range(7):
    Pr.append(math.exp(-mean)mean*x/math.factorial(x))
    E.append(Pr[x]*N)
    xi.append((f[x]-E[x])**2/E[x])
    print("%2.2f %2.2f  %4.2f   %3.2f  %3.2f"%(x,Pr[x],f[x],E[x],xi[x]))
print("----------------------------------")
cal_chi2=np.sum(xi)
print("Calculated value of Chi square is %4.2f"%cal_chi2)
tab_chi2=scipy.stats.chi2.ppf(1-.01, df=n)
print("Table value of Chi square at 1  level is %4.2f"%tab_chi2)
if cal_chi2<tab_chi2:
    print("The given data can be fitted in Poissson distribution at 1% LOS")
else:
    print("The given data cannot be fitted in Poisson distribution at 1% LOS")
```
## Output:

![PTGG](https://user-images.githubusercontent.com/77062608/167776843-351a8c89-57b3-45be-9335-c5a3430f984f.jpg)

## Results:
Thus, fitting poisson distribution for the given frequencey distribution is verified.

## 1. Background

The birthday problem or birthday paradox concerns the probability that, in a group of n randomly chosen people, some pair of them will have the same birthday. The probability of a shared birthday among 23 randomly chosen people is over 50%. The probability reaches 99.9% with a larger group of 70 people. The birthday problem is a veridical paradox, which appears to be absurd, but is demonstrated to be true. Here we provide a brief proof for the most common simplified case. Disregarding the leap year, twins,  assume that there are 365 days in a year and that every day has the same probabilities.

To compute $p(n)$ , the probability that there exist at least 2 persons have a same birthday in a set of n randomly chosen people, first consider the the probability of the opposite event $\bar{p}(n)$, i.e.  no two people in the group share the same birthday. When $n<365$ ,
$$
\begin{aligned}
\bar{p}(n) &= 1\times (1-\frac{1}{365})\times(1-\frac{2}{365})\times \cdots\times (1-\frac{n-1}{365}) \\
&=\frac{365 \times 364 \times \cdots \times(365-n+1)}{365^{n}} \\
&=\frac{365 !}{365^{n}(365-n) !}=\frac{n ! \cdot\left(\begin{array}{c}
365 \\
n
\end{array}\right)}{365^{n}}=\frac{ P_{365,n}}{365^{n}}
\end{aligned}
$$
where $P_{365,n}$ denotes the  permutation.

Thus, the complement event that at least 2 persons share the same birthday has the probability:
$$
p(n) = 1 - \bar{p}(n)
$$
The principle can be applied to attack hash function, which is referred as birthday attack. The hash function takes a message as input and transform it into a certain length number (hash value) by a predetermined algorithm. It is universally used in producing digital signatures to check file integrity. The birthday problem reveals the weakness that how much effort it may take to forge 2 different messages with the same hash value by brute force.

In the following sections, we will generalize the problem, and take into account arbitrary number of days, leap years, twins and multiple matches.

## 2. Main Findings

In this section, we will generalize the birthday problem to wider conditions. Here we calculate the probability and provide a brief proof in each case.

### 2.1 Birthday Problem  with Arbitrary Days

Considering a planet other than the earth, whose revolution cycle is N.
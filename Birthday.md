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

Considering a planet other than the earth, whose revolution cycle is d days, assuming that an individual from this planet was born on any day of the year with equal  probability, use $P(n,d)$  to denote the probability that at least two persons of a set of n people from such a planet has the same birthday.

In a group of n people, starting with an arbitrary person who was born on a certain day, the probability that a second person has a different birthday is $(d-1)/d$ . The probability that the third person who has a birthday different from the first two persons is $[(d-1)/d][(d-2)/d]$ . 

Similarly, the probability that the n-th person $(n<d)$ has a different birthday from others' is
$$
\begin{aligned}
\bar{P}(n,d) &= \frac{d-1}{d} \times \frac{d-2}{d}\times \cdots \times\frac{d-(n-1)}{d}\\ 
&= \frac{d!}{(d-n)!d^n}  = \frac{P_{d,n}}{d^n}
\end{aligned}
$$
where $P_{d,n}$ denotes the n-permutation of d.

Therefore, for the case that a year has arbitrary days, the complementary probability that at least 2 persons from a group of size n $(n<d)$ share a same birthday is:
$$
P_(n,d)= 1-\bar{P}(n,d)=1- \frac{P_{d,n}}{d^n}
$$

## 2.2 Leap Year Case

Consider the case that a special day (e.g. Feb. 29) does not exist in every year, the probability that one born in this special day is q.

To calculate the coincident probability for a group of size n, divide the event into 2 cases:

Case I:  the n persons were born on n different days other than the special day.

Case II: the n persons were born on n different days, including one was born on the special day.

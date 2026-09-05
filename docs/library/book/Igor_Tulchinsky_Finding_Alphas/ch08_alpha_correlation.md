# Chapter 8: Alpha Correlation

> Author: Chinh Dang and Crispin Bui | *Finding Alphas* (WorldQuant / Wiley 2nd Edition)

---

Alpha Correlation By Chinh Dang and Crispin Bui

Alphas are evaluated by many different metrics, such as the information ratio, return, drawdown, turnover, and margin. These metrics are derived mainly from the alpha’s profit and loss (PnL). For example, the information ratio is just the average returns divided by the standard deviation of returns. Another key quality of an alpha is its uniqueness, which is evaluated by the correlation coefficient between a given alpha and other existing alphas. An alpha with a lower correlation coefficient normally is considered to be adding more value to the pool of existing alphas. If the number of alphas in the pool is small, the importance of correlation is low. As the number of alphas increases, however, different techniques to measure the correlation coefficient among them become more important in helping the investor diversify his or her portfolio. Portfolio managers will want to include relatively uncorrelated alphas in their portfolios because a diversified portfolio helps to reduce risk. A good correlation measure needs to identify the uniqueness of one alpha with respect to other alphas in the pool (a smaller value indicates a good uniqueness). In addition, a good correlation measure has the ability to predict the trend of movement of two alpha PnL vectors (time-series vectors). The correlation among alphas can be computed based on alpha PnL correlation or alpha value correlation. ALPHA PnL CORRELATION Given two alpha PnL vectors (we use bold letters for vectors): Pi = [ Pi1 , Pi 2 ,…, Pin ] ∈  n T

### T

### Pj =  Pj1 , Pj 2 , …, Pjn  ∈  n

### (1)



### 62

where Pit and Pjt denote the PnLs of i th and j th alphas on the t th day, n is the number of days used to measure correlation, and T denotes the matrix transposition. Note: tests usually select the number of days for correlation as two or four years instead of a full history, to save computational resources. Pearson Correlation Coefficient The Pearson correlation coefficient, also known as the Pearson product-moment correlation coefficient, has no units and can take values from 1 to 1. The mathematical formula was first developed by Karl Pearson in 1895: cov Pi , Pj

### r

### Pi

### where cov Pi , Pj

### E Pi

### Pj

### Pi

### (2)

### Pj

### Pj

### is the covariance and

### Pi

and Pj are the standard deviations of Pi and Pj , respectively. For two vectors of PnLs, the coefficient is computed by using the sample covariance and variances. In particular, n

### r

### t 1

### Pit

Pit t 1

### Pi

### n

### Pi

Pjt n

### Pj

Pjt t 1

### Pj

.

### (3)

The coefficient is invariant to linear transformations of either variable. If the sign of the correlation coefficient is positive, it means that the PnLs of the two alphas tend to move in the same direction. When the return on Pi is positive (negative), the return on Pj has a tendency to be positive (negative) as well. Conversely, a negative correlation coefficient shows that the PnLs of the two alphas tend to move in opposite directions. A zero correlation implies that there is no relationship between two PnL vectors. Figure 8.1 shows the variation of maximum correlation as a function of trading signals, using two years’ worth of data. Alphas seek to make predictions about the future movements of various financial instruments. As a result, the analysis needs to be extended into a time series, which includes a sequence of random variables with the time index. In the case of an alpha PnL vector, the observation is the profit (+) or loss (−) of the alpha in one day. Below we briefly review the dot product, then discuss the temporal-based correlation.

Alpha Correlation63

### Maximum correlation

0.25 0.2 0.15 0.1 0.05

### MaxCorr



,0 ,0



### 0,



1,

### ,0

### 0,

### 1,





### Number of trading signals

### Figure 8.1

Variation of maximum correlation as a function of ­trading signals

Temporal-Based Correlation The dot (inner) product is defined as the sum of the products of the corresponding entries of the two sequences of numbers. Pi .Pj

### Pi Pi cos

### (4)

where P is the modulus, or magnitude, of the PnL vector and is the angle between the two vectors. One important application of the dot product is to find the angle between two vectors because the angle can be found via cos

### n

### Pi .Pj

### P Pjt

### t 1 it

### Pi Pi

### n

P2 t 1 it

.

### n

P2 t 1 jt

### (5)

When the angle is zero, the two PnL vectors fall on the same 1. When the angle is , the vectors are line and cos 0. orthogonal and cos The temporal-based correlation considers each alpha’s PnL vector as a time-series sequence and assigns weight to the values on each day. The correlation between two PnL vectors is thus defined as: n

### r

### n

w Pit 2 t 1 t

### Tulchinsky571216_c08.indd 63

### w Pit Pjt

### t 1 t

### n

w Pjt 2 t 1 t

.

### (6)

### 8/7/2019 7:52:39 PM

64

Naturally, larger weights are assigned to recent PnL values (wt wt 1, t t 1,…, n ). For example, wt 1 , which is inversely proportional to n the time index t. The formula transforms input pairs of vectors (Pi , Pj ) into time-scaled vectors and then computes the angle between the two scaled vectors: T

P'i =  w1 Pi1 , w2 Pi 2 , … , wn Pin  ∈  n T

P' j =  w1 Pj1 , w2 Pj 2 , … , wn Pjn  ∈  n .

### (7)

As a result, the temporal-based correlation still preserves many desirable aspects of the traditional dot product, such as commutative, distributive, and bilinear properties. The Pearson correlation coefficient can be computed here for the two scaled vectors in Equation 7. We can see that the centered variables have zero correlation or are uncorrelated in the sense of the Pearson correlation coefficient (i.e. the mean of each vector is subtracted from the elements of that vector), while orthogonality is a property of the raw variables. Zero correlation implies that the two demeaned vectors are orthogonal. The demeaning process often changes the angle of each vector and the angle between two vectors. Therefore, two vectors could be uncorrelated but not orthogonal, and vice versa. For further information about linear independent, orthogonal, and uncorrelated variables, see Joseph Rodgers et al. (1984). Generalized Correlation Data transformation can be an important tool for proper data analysis. There are two kinds of transformations: linear and nonlinear. A linear transformation (such as multiplication or addition of a constant) preserves the linear relationships among the variables, so it does not change the correlation among the variables. Below we will consider nonlinear transformations, which typically modify the correlation between two variables. The two correlation formulas above compute correlation coefficients using daily PnL values. The generalized correlation creates a matrix M k n , then transforms the two PnL vectors to a different Euclidean space: Qi = M k×n Pi ∈  k Q j = M k × n Pj ∈  k .

### (8)

Alpha Correlation65

The regular correlation now is computed in the transformed domain, k n with some additional features added by the transformed matrix M . k n n n I is the identity matrix, we obtain the regular correlation If M scheme. Here we take a look at some other particularly useful transformations. The weekly PnL correlation is computed for weekly instead of daily n and the transformation matrix becomes PnL vectors. In this case, k Mk n

### mi , j

### n

### (9)

### n

n i 1, and t 1, 5 and all other elements are zero. The weekly correlation is usually higher than daily values, but it is another way to understand alphas. The monthly PnL correlation is computed using a similar approach. The temporal-based correlation is another form of generalized correlation, corresponding to the square diagonal transformation matrix:

### where mi , i 1 *5 t

### Mk n

### where

### mi , j

### wi if i

### mi , j

### (10)

### n n

### j

. Under this transformation, the input PnL mi , j 0 otherwise vectors are transformed into time-scaled vectors, as in Equation 7. The sign PnL correlation is another form of PnL vector correlation, in which the correlation is computed over the signs of the PnL values instead of the values themselves. The transformation matrix now is a data-­dependent diagonal matrix and its element values depend on input PnL vectors. As a result, the input pairs (Pi , Pj) are transformed into the following form: Q'i = sgn ( Pi1 ) , sgn ( Pi 2 ) , … , sgn ( Pin )  ∈  n T

Q'j = sgn ( Pj1 ) , sgn ( Pj 2 ) , … , sgn ( Pjn )  ∈  n T

### (11)

where sgn x is the sign (or signum) function and takes the values 1, 0, 1 , corresponding to (positive, zero, negative) values of x .

66

ALPHA VALUE CORRELATION Denote the alpha position vector on the t th day by T

α i ( t ) = α i1( t ) , α i 2 ( t ) , … , α im ( t )  ∈  m where m is the number of instruments,

### t

### k

### ik

### (12)

### m is (or is propor-

### th

### tional to) the amount of money invested in k instrument, and

m k 1

t ik

is (or is proportional to) the total amount of money invested in the portfolio. It is sometimes useful to consider the alpha position vectors as well as the PnL vectors. In particular, portfolio managers often consider two correlation measures based on positions: the position correlation and the trading correlation. The position correlation between two alphas over a period of d days is computed by forming the following two vectors: T

### α i = α i (1) , α i ( 2 ) , … , α i ( d )  ∈  ( m*d )

### (13)

### T

α j = α j (1) , α j ( 2 ) , … , α j ( d )  ∈  ( m*d ) .

The trading correlation between two alphas over a period of d days is computed by forming the two difference vectors: T

α i = α i (1) − α i ( 2 ) , α i ( 2 ) − α i (3) , … , α i ( d ) − α i ( d +1)  ∈  ( m*d ) T

α j = α j (1) − α j ( 2 ) , α j ( 2 ) − α j (3) , … , α i ( d ) − α j ( d +1)  ∈  ( m*d ) .

### (14)

Normally, it is enough to take d 20 days, so the alpha vector is of dimension 20 * the number of instruments in the universe. If two alphas take positions on different universes of instruments, the intersection of the two universes is used for the calculations. CORRELATION WITH ALPHA POOL The above correlation methods are used for checking the correlation between two individual alphas. Naturally, given a pool of alphas, the maximum correlation has been used as a measure of the value added by

Alpha Correlation67

### Table 8.1

### A histogram of correlation

### Bins

### cnt(%)

### count_in_number

### 0.9

### c9

0.8

### c8

0.7

### c7

0.6

### c6

0.5

### c5

0.4

### c4

0.3

### c3

### 5,102

### 0.2

### c2

### 70,294

### 0.1

### c1

### 283,436

c0

### 438,720

### −0.1

### c_1

### 286,478

### −0.2

### c_2

### 36,889

### −0.3

### c_3

### 1,293

### −0.4

### c_4

−0.5

### c_5

−0.6

### c_6

−0.7

### c_7

−0.8

### c_8

−0.9

### c_9

−1

### c_10

a given alpha. As the number of alphas increases, the average correlation becomes more important than a single max correlation. T-corr is defined as the sum of the correlations of the given alpha with all other alphas. The average correlation and T-corr provide additional powerful measures of alpha value addition, along with the max correlation. A correlation density distribution is more important than a singular maximum value or even the average correlation value. Table 8.1 shows a sample histogram of correlation density (20 bins of size 0.1). Numerous features can be extracted from the histogram in addition to the maximum correlation and the average correlation. For example, the scaled average score of one alpha with the pool could be defined as j c * (c j is taken from Table 8.1). The score ranges in 1, 1 , j 10 j which increases if the number of alphas with positive correlation increases or the number of alphas with negative correlation decreases.

68

CONCLUSION We have surveyed several different approaches to evaluating the correlations between the PnLs and positions of alphas and pools of alphas. There are, of course, more statistical and less algebraic approaches to evaluate correlation, such as Spearman’s rank correlation and the Kendall rank correlation. Within the scope of this chapter, we have covered only some of the most common methods for evaluating alpha correlation. PnL correlation can be evaluated over a longer period of time (2–4 years or longer) in comparison with alpha value correlation (which requires a short, recent period of time) because of the limitations of computational resources. One reasonable idea often can be used to develop numerous alphas, depending on different techniques and datasets. Because they are developed using a single idea, these alphas have a tendency to be highly correlated. Sometimes there are instances when it is beneficial to combine some or all of these highly correlated alphas instead of selecting only one alpha and removing all others. Two alphas may have highly correlated historical performance, but the future is uncertain and it is not always clear which one may add more value in the future. Therefore, in terms of resource allocation for two high-correlation alphas (e.g. A and B), one can divide resources (not necessarily equally) between A and B instead of allocating all of the resources to a single alpha. A single alpha cannot fully describe every aspect of one idea, but each alpha represents that idea in a different way; hence, using all these alphas at once may provide a more complete view of the idea and make the overall strategy more robust. The ultimate objective of alpha correlation is to find the true value of adding one new alpha, given a pool of existing alphas, which becomes increasingly important as the number of alphas grows toward the sky. Using multiple correlation approaches leads to a better understanding of the alpha signals in recent history as well as over a longer past period. An alpha based on a completely novel trading idea is generally unique and adds the most value to the alpha pool.
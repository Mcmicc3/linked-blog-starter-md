
# Concepts to Understand

## Chapter 1
Category vs Quantative
Nominal, ordinal, interval, and ratio

A **nominal scale** is the most basic level of measurement. It's used for data that can only be categorized or labeled, with no inherent order or rank. You can't perform any meaningful mathematical operations like addition or subtraction with nominal data, as the numbers are just labels.

- **Key Property:** Categorization.
    
- **Examples:** Gender (male, female, non-binary), types of cars (sedan, SUV, truck), colors (red, blue, green), or yes/no answers. You can count how many people are in each category, but you can't say that "male" is greater than "female."

An **ordinal scale** has all the properties of a nominal scale, but with the added ability to **rank or order** the categories. The difference between the ranks, however, isn't uniform or measurable. You know the order, but not the exact distance between each item.

- **Key Property:** Order/Rank.
    
- **Examples:** A customer satisfaction survey with ratings like "very unsatisfied," "unsatisfied," "neutral," "satisfied," "very satisfied." You know that "very satisfied" is better than "satisfied," but you can't say that the difference between "satisfied" and "neutral" is the same as the difference between "neutral" and "unsatisfied." Other examples include military ranks (Private, Corporal, Sergeant) or a race's finishing order (1st, 2nd, 3rd).

An **interval scale** has all the properties of an ordinal scale, but the **intervals between the data points are equal and meaningful**. This allows you to perform addition and subtraction. The main limitation is that an interval scale **lacks a true zero point**, meaning zero doesn't represent the complete absence of the measured variable. Because there's no true zero, you can't perform multiplication or division.

- **Key Property:** Equal intervals.
    
- **Examples:** Temperature in Celsius or Fahrenheit. The difference between 20°C and 30°C is the same as the difference between 30°C and 40°C (10 degrees), so you can add and subtract temperatures. However, 0°C doesn't mean "no temperature." It's just a point on the scale, so you can't say that 20°C is twice as hot as 10°C. Other examples include IQ scores or calendar dates.

A **ratio scale** is the most informative level of measurement. It has all the properties of an interval scale, with the critical addition of a **true zero point**. This means that zero signifies the complete absence of the variable, allowing for all types of mathematical operations, including multiplication and division.

- **Key Property:** True zero point.
    
- **Examples:** Height, weight, age, or income. A person who is 0 inches tall has no height. A person who weighs 200 lbs is twice as heavy as a person who weighs 100 lbs. You can also have a zero income. The Kelvin temperature scale is another example, where 0 K represents absolute zero, the complete absence of thermal energy.


## Chapter 2
Relative frequency, 
Frequency Distribution, 
Crosstabulation, 
Scatter Diagrams

#### Relative Frequency
![[Pasted image 20250917000328.png]]
![[Pasted image 20250917000156.png]]
- ***Frequency: The frequency of a class is the number of times that class appears in the data set.***

#### Find Frequency
![[Pasted image 20250917000812.png]]
- To find **Frequency**

#### Frequency Distribution
![[Pasted image 20250917001118.png]]
- Example of **frequency distribution**, simply find the frequency for each class.

##### Cross Tabulation
A **crosstabulation** (or contingency table) is used to summarize the relationship between two categorical variables. The rows represent one variable, and the columns represent the other. In this case, x is the row variable (A, B, C) and y is the column variable (1, 2). The cells show the frequency of each combination of categories.

To fill the table, count the number of observations for each cell from the provided data. The total number of observations is 30.

![[Pasted image 20250917144926.png]]
- Cross Tabulation

 ![[Pasted image 20250917151205.png]]

###### Steps
1. Count all the frequencies
2. Compute row percentages
	1. To compute the **row percentages**, divide the frequency in each cell by its corresponding row total and multiply by 100.

```
			**Row A (Total = 4):**
			- **y=1:** (4 / 4) * 100 = **100.0%**
			- **y=2:** (0 / 4) * 100 = **0.0%**
```
3. Compute column percentages
	1. To compute the **column percentages**, divide the frequency in each cell by its corresponding column total and multiply by 100. The column totals are 19 for y=1 and 11 for y=2.
```
		**Column 1 (Total = 19):**
		
		- **x=A:** (4 / 19) * 100 ≈ **21.1%**
		- **x=B:** (13 / 19) * 100 ≈ **68.4%**
		- **x=C:** (2 / 19) * 100 ≈ **10.5%**
```
#### (D) Describe the relationship (x & y)
The easiest way to understand the relationship is to look at the **row percentages**, as they show the distribution of the column variable (y) for each category of the row variable (x). We can then see if the distribution of y is consistent across the categories of x.

- **Category A values for x:** Looking at the row for A in the row percentages table, we see that **100%** of observations in category A are associated with category 1 of y. This is a very strong, definitive relationship. There are no observations from category A in category 2 of y. Therefore, we can conclude that Category A values for x are **always associated** with Category 1 values for 

- To understand how **y influences x, you should check the column percentages.** Column percentages show the distribution of the row variable (x) within each category of the column variable (y). This helps you answer the question: "Given a specific category of y, how are the x values distributed?"

- To understand how **x influences y, you should check the row percentages.** Row percentages show the distribution of the column variable (y) within each category of the row variable (x). This helps you answer the question: "Given a specific category of x, how are the y values distributed?"

#### Scatter Plot
![[Pasted image 20250917153427.png]]
- Learn how to do this in excel (Or python?)


## Chapter 3
Section 3.1 – main topics: mean, median, mode and quartiles
Section 3.2 – main topics: range, IR, variance, standard deviation, and coefficient variation
Section 3.3 – main topics: z-scores
Section 3.4 – main topics: box plot
Section 3.5 – main topics: covariance, and correlation coefficient.

#### Mean, Median, mode
###### Mean
$$
\bar{x} = \frac{\sum x_i}{n}
$$
This formula gives us the medium
Sample data: 56, 57, 72, 61, 66, 59, 56, 71, 59, 70, 56
n = observations (11)
![[Pasted image 20250917163516.png]]

###### Medium
![[Pasted image 20250917163624.png]]
Middle observation
- If the sample size is even, the median is the average of the two middle values.
% Example of finding the average
$$
\text{Median} = \frac{x_{5} + x_{6}}{2} 
= \frac{59 + 61}{2} = 60
$$
The mode is the value that occurs the most often in a set of data.
mode = 56

#### Range, Interquartile Range, Sample Variance, and Sample Standard Deviation
Data set: `15 20 20 21 22 24 30 34` 

##### Range
Find the range by subtracting the largest value with the smallest value
range = largest value - smallest value
range = $34 - 15$
range = $19$ 

##### Interquartile Range
The interquartile range is another measure of variability and represents how spread out the middle 50% of the data are. Unlike the range, the interquartile range is not influenced by extreme values. It is calculated as the difference between the third and first quartiles, $Q3 − Q1.$ Before this difference can be calculated, we must first find the values of
$Q_1$ and $Q_3$

###### Step 1
***Find the Location of the $Q_1$***
$Q_1$ = 25th percentile. (You can figure out the rest)

To find a percentile, we must order the data in ascending order. Then find the location of the $p_{th}$ percentile using the formula:
$$
L_p= \frac{p}{100}(n+1)
$$
where _n_ is the number of observations in the data set. This data set has 8 observations

p = location (I.E: 25th, 50th, 75th)
n = Observations 
$$
L_{p}= \frac{25}{100}(8+1)
$$
$L_{25}$= $2.25$

Since the observations are only whole-numbered values, the 25th percentile will occur at a position between the **second and third** ![Correct: Your answer is correct.](https://www.webassign.net/static/wacache1d607b4989c818e6ee8581736196d357/img/questions/mCorrect.svg "Your answer is correct.") observations.

###### Step 2
***Find the 1st Quartile***
Since $L_{25} = 2.25$, the 25th percentile will occur at a position between the second and third observations. Recall the dataset: `15 20 20 21 22 24 30 34` 

To find the exact value of the 25th percentile, the first quartile, multiply the decimal portion from $L_{25}$ by the difference between the first and second observations. Then add this value to the first observation.

$$
\begin{align*}
Q_1 = \text{second observation} + \text{decimal portion of } L_{25} \text{ (Third observation - second observation)}\\
Q_{1}= 20 + 0.25(20 -20) \\
Q_{1}= 20\\
\end{align*}
$$
###### Step 3
***Find the location for the third Quartile $Q_3$***
The third quartile is another way to refer to the 75th percentile. First order the data in ascending order then use the same formula found in step 1
$$
\begin{align*}
L_{75}= \frac{75}{100}(7+1) \\\\
L_{75}= 6.75
\end{align*}
$$
###### Step 4
***Find $Q_3$***
With $L75 = 6.75$, the precise location of the 75th percentile will be 0.75 of the way **between observations 6 and 7**.

75th percentile = sixth observation + decimal portion of $L_{75}$ (Seventh observation - Sixth observation) 
$$
\begin{align*}
Q_{3}&= 24 + 0.75(30-24)\\
Q_{3}&= 28.5
\end{align*}
$$
###### Step 5
***Now Find the Interquartile Range (IQR)***
$$
\begin{align*}\\
IQR &= Q_{3}- Q1\\
IQR &= 28.5 - 20 \\
IQR &= 8.5\\
\end{align*}
$$
##### Variance
Data set = `15 20 20 21 22 23 30 34`
The variance of a set of data is used to compare the variability in two or more variables. It is based on the differences between observations and the mean of the data, called the deviation about the mean.

Often a sample from a population is obtained so the formula for the variance will be modified. The **sample variance**, $s^2$, is calculated as follows. Note that the sample mean $x$
is used **instead of** the **population mean** $\mu$, and the denominator is one less than the number of observations in the sample.
$$
s^{2}= \frac{\sum\ (x_{i} - \bar{x})^2}{n-1}
$$
###### Step 1
***Find the sample mean***
In order to use the formula for $s^2$, we will first find the sample mean $\bar{x}$.
$$
\begin{gather*}
\bar{x} = \frac{\sum{x_{i}}}{n} \\\\
\bar{x} = \frac{15 + 20 + 20 + 21 + 22 + 24 + 30 + 34} {8}\\\\
\bar{x} = 23.25 
\end{gather*}
$$
###### Step 2
Observe to understand how the numerator of the variance equation is solved
![[Pasted image 20250917180930.png]]
- The correct value is 261.17 and it is found by adding all the numbers on the far right column.

###### Step 3
***Find the sample variance***
We found that $\sum\ (x_{i} - \bar{x})^2$  and the sample size is $n = 8$. Substitute these values into the formula for the sample variance and simplify, rounding the result to two decimal places.

$$
\begin{gather*}
s^{2}= \frac{\sum\ (x_{i} - \bar{x})^2}{n-1}  \\\\
s^{2} = \frac{261.17}{8-1} \\\\
s^{2} = 37.31
\end{gather*}
$$
###### Step 4
***Find the standard deviation***
The standard deviation is the positive square root of the variance and has the same units as the given data. For this reason it is **easier to draw conclusions about the data using the mean and standard deviation** than with the variance.

The sample variance was found to be $s^2$ = $\frac{261.17}{7}$.  Use this to find the sample standard deviation, _s_, rounding the result to two decimal places.

$$
\begin{gather*}
s = \sqrt{s^{2}} \\
s = \sqrt{\frac{26.17}{7}} \\
s = 6.11
\end{gather*}
$$
##### Bell Shaped Distributions (Z scores)
Suppose that the mean retail price per gallon of regular grade gasoline in the United States is $3.48 with a standard deviation of $0.30 and that the retail price per gallon has a bell-shaped distribution.
(a) What percentage of regular grade gasoline sold between **$2.88 and $4.08** per gallon?

###### Step 1
***Find the Z-score***
Since it is given that the retail price per gallon of gas has a bell-shaped distribution, **the empirical rule** can be applied. The empirical rule uses standard deviations about the mean to describe the percentage of the data that will lie within a given range. Therefore, we must first determine how many standard deviations above and below the mean $2.88 and $4.08 are. It is given that the mean is $3.48 and the standard deviation is $0.30.

The number of standard deviations, _z_, a value is from the mean can be found using the following formula. If we are given a value that is smaller than the mean, use the following.

$$
z = \frac{\text{mean - given value}} {\text{standard deviation}}
$$
If the given value is larger than the mean, use the following.
$$
z = \frac{\text{Larger value - mean}} {\text{standard deviation}}
$$
The difference between the mean and the smaller value, $2.88, is $0.60. How many standard deviations, _z_, below the mean is $2.88?
$$
\begin{align*}\\
z &= \frac{3.48-2.88}{0.30}\\
z &= 2
\end{align*}
$$
The difference between the larger value, $4.08, and the mean is $0.60. How many standard deviations above the mean is $4.08?
$$
\begin{align*}\\
z &= \frac{4.08-3.48}{0.30}\\
z &= 2
\end{align*}
$$
###### Step 2
***The Empirical Rule***
![[Pasted image 20250917191853.png]]
- Using the empirical rule, the percentage of data that will fall within two standard deviations of the mean is 95%
- Half of one standard deviation is 34%
- Half of two standard deviations is 47.5 %

`(b)What percentage of regular grade gasoline sold between $2.88 and $3.78 per gallon?
We determined 47.5% of the data is between two standard deviations below the mean and the mean. Another 34% of the data is between the mean and one standard deviation above the mean. Thus, the percentage of gas prices between two standard deviations below the mean, $2.88, and one standard deviations above the mean, $3.78, will be the sum of  $47.5\% + 34\% = 81.5\%$

`(c)What percentage of regular grade gasoline sold for more than $3.78 per gallon?`
We already determined that $3.78 is one standard deviation above the mean.

The empirical rule states that approximately 68% of the data falls within one standard deviation of the mean. This means that the remaining $100\% − 68\% = 32\%$  of data falls beyond one standard deviation of the mean.

Since we are only concerned with the percentage of data that is **greater than one standard deviation above the mean**, we only need half of this percentage. Thus, the percentage of gas that sold for more than $3.78 is $16\%$.

##### Five Number Summary (Min, $Q_1$, Med, $Q_3$, Max)
A **five-number summary** is a set of descriptive statistics that provides information about a dataset's distribution.

Data Set: `508, 839, 1274, 1456, 1850, 1872, 2027, 2459, 2918, 3653, **3919**, 4241, 5894, 6452, 7378, 8205, 8308, 8779, 10598, 11413, 14138`

**Find the First Quartile (Q1​):** The first quartile is the median of the lower half of the data (the first 10 values). For an even number of values, we take the average of the two middle values, which are the 5th and 6th in this group.
$$
Q_{1} = \frac{1850+1872}{2} = \frac{3722}{2} = 1,861
$$
**Find the Third Quartile (Q3​):** The third quartile is the median of the upper half of the data (the last 10 values). We take the average of the two middle values in this group (the 16th and 17th values of the full dataset).
$$
Q_{3} = \frac{8205+8308}{2} = \frac{16513}{2} = 8,256.5
$$
##### Lower and Upper Limits
***Identifies Outliers***
limits are used to identify potential **outliers**, which are data points that lie unusually far from the main body of the data. The range of values that are **not considered outliers is** **determined by the interquartile range (IQR)**.
Data Set: `508, 839, 1274, 1456, 1850, 1872, 2027, 2459, 2918, 3653, **3919**, 4241, 5894, 6452, 7378, 8205, 8308, 8779, 10598, 11413, 14138`
1. **Calculate the Interquartile Range (IQR):** The IQR is the difference between the third and first quartiles.

$\text{IQR} = Q_{3}- Q_{1}= 8256.5 - 1861 = 6,395.5$

2. **Calculate the Lower Limit:** The lower limit is calculated by subtracting 1.5 times the IQR from the first quartile.
$$
\begin{gather*}
\text{Lower Limit =} Q_{1}- 1.5 * \text{IQR} \\
\text{Lower Limit =} 1861 - 1.5(6395.5) \\
\text{Lower Limit =} 1861 - 9593.25 = -7,732.25
\end{gather*}
$$
3. **Calculate the Upper Limit:** The upper limit is calculated by adding 1.5 times the IQR to the third quartile.
$$
\begin{gather*}
\text{Upper Limit =} Q_{3}- 1.5 * \text{IQR} \\
\text{Upper Limit =} 8256.5 - 1.5(6395.5) \\
\text{Upper Limit =} 8256.5 - 9593.25 = 17,849.75
\end{gather*}
$$
##### Box plot
A box plot visually summarizes the **five-number summary** and helps to identify outliers.
The central box in the plot represents the **middle 50% of your data**.
- The **left edge** of the box is the **first quartile (Q1​)**, which is 1,861.
- The **right edge** of the box is the **third quartile (Q3​)**, which is 8,256.5.
- The **line inside the box** is the **median (Q2​)**, which is 3,919.

The **whiskers** (the lines extending from the box) show the range of the data outside the middle 50%. Their length is determined by the outlier limits.
- The whiskers extend to the largest and smallest data points that are **not outliers**.
- In this specific problem, there were **no outliers**, as every data value fell within the lower limit (-7,732.25) and the upper limit (17,849.75).
- Because there are no outliers, the whiskers extend all the way to the **minimum** and **maximum** values of the dataset.
    - The left whisker extends to the **minimum** value: 508.
    - The right whisker extends to the **maximum** value: 14,138.

![[Pasted image 20250917214129.png]]

##### Sample Covariance
Data Set:
$x_{i}: 4, 6, 11, 3, 16$
$y_{i}: 50, 50, 40, 70, 20$

***Shows the direction (+ or - ) of the relationship between variables***

To find the sample covariance $s_{xy}$, you need to follow a step-by-step process. Covariance is a measure that shows how two variables, in this case, $x$ and $y$, change together.
$$
s_{xy} = \frac{\sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})}{n - 1}
$$
1. Find the Mean of Each Variable
2. Find the Deviation from the Mean for Each Observation
3. Multiply the Deviations and Find the Sum
4. Divide by n−1

$s_{xy} = \frac{-350}{5-1} = \frac{-350}{4} = -87.5$

A negative covariance such as this indicates that as the values for one variable tend to increase, the values for the other variable tend to decrease, which is a linear relationship. 

Breakdown: https://gemini.google.com/u/1/app/6be5903e021bcadd


##### Sample Correlation Coefficient
Data Set:
$x_{i}: 4, 6, 11, 3, 16$
$y_{i}: 50, 50, 40, 70, 20$

***Shows both the direction (+ or - ) and the strength of the relationship between variables (Sometimes it's easier for comparison)***
The sample correlation coefficient, often called Pearson's r, is a value between -1 and 1 that measures the **strength** and **direction** of a linear relationship between two variables.

The formula for the sample correlation coefficient is:
$r = \frac{s_{xy}}{s_xs_y}$

1. Identify the Necessary Components
2. Calculate the Sample Standard Deviation for x
3. Calculate the Sample Standard Deviation for y
4. Calculate the Sample Correlation Coefficient

$r = \frac{s_{xy}}{s_xs_{y}} = \frac{-87.5}{(5.4314)(18.1659)} = \frac{-87.5}{98.6318} \approx -0.88713$

Strong negative linear relationship, meaning as x increases, y tends to decrease in a predictable pattern.

Breakdown = https://gemini.google.com/u/1/app/6be5903e021bcadd


## Chapter 4
Section 4.1
Section 4.2
Section 4.3 
Section 4.4. (conditional probability) is very important.
Section 4.5 Bayes' Theorem

## Chapter 5
Section – 5.1 Random Variable.
Section – 5.2 Developing Discrete Probability Distribution
Section – 5.3 Expected Value and Variance.
- ***Skip 5.4***
Section – 5.5 Binomial Probability Distribution.
- ***Skip the rest.***

##### Random Variable 
A numerical description of the outcome of an experiment is called a **random variable**
A random variable is a variable whose possible values are numerical outcomes of a random phenomenon. It's a function that assigns a real number to each outcome in the sample space of a random experiment. For example, if you flip a coin twice, the number of heads that appear is a random variable. The possible outcomes are 0, 1, or 2. While the outcome of any single trial is random, the variable itself, which represents a numerical value, is what we call a random variable.

##### Continuous Variable
An experiment consists of determining the speed of automobiles on a highway by the use of radar equipment. The random variable in this experiment is a **Continuous*** random variable. 
A **continuous random variable** is a variable that can take on any value within a given interval. This type of variable is typically used to represent measurements, such as height, weight, temperature, or, in this case, speed. The speed of a car can be any value within a range (`e.g., 60.5 mph, 60.51 mph, 60.512 mph, etc.`), not just a specific set of whole numbers.

##### Discrete Random Variable
The number of customers that enter a store during one day is an example of **a discrete random variable***

A **discrete random variable** is a variable that can only take on a specific, countable number of values. These values are often integers. The image shows the number of heads in a coin toss, which can only be 0, 1, or 2. This is a classic example of a discrete random variable because you can't have 1.5 heads or any other fractional value. Other examples of discrete random variables include the number of children in a family or the number of cars that pass an intersection in an hour.

##### Probability Distribution
A description of the distribution of the values of a random variable and their associated probabilities is called a **Probability Distribution***
A description of the distribution of the values of a random variable and their associated probabilities is called a **probability distribution**. This is the correct term for a function that describes the likelihood of obtaining the possible values that a random variable can assume.

##### Discrete probability function
$\sum{p}{(x)} = 1$

The two fundamental conditions for a **discrete probability distribution** are:

1. Each probability must be between 0 and 1, inclusive. Mathematically, this is represented as 0≤P(x)≤1.
2. The sum of all the probabilities for all possible outcomes must equal 1. This can be expressed as ∑P(x)=1.

These two rules ensure that the distribution is mathematically valid. The first rule ensures that no probability is negative or greater than 100%, and the second rule ensures that all possible outcomes are accounted for, with their total probability adding up to 100%.

##### Probability distribution
![[Pasted image 20250920093149.png]]
![[Pasted image 20250920093205.png]]

##### Expected Value 

A measure of the average value of a random variable is called a(n) **Expected Value***. 
The correct answer is **expected value**. The expected value is the average value of a random variable over a very large number of experiments or observations. It is calculated by summing the products of each possible value of the variable and its corresponding probability.

##### Expected Value Calculation 
https://gemini.google.com/u/1/app/05580d3e803af436 (revisit)


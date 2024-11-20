**Central Tendency**
- Mean 
- Median
- Mode
 
**Range**:
- Max
- Min
- Quantiles
- Outlier

**Dispersion**
- Variance
- Standard Deviation

**Skew**
![[Pasted image 20241114205759.png]]



### Mean
Population Mean - $\bar{x} = \frac{1}{n}\sum\limits^{n}_{i=1}{x_i}$
Sample Mean -  $\mu = \dfrac{\sum{x}}{N}$
 Weighted Mean - $\bar{x} = \dfrac{\sum_{i=1}^{n}{w_i x_i}}{\sum_{i=1}^{n}{w_i}}$
 Trimmed Mean - mean after removing outliers

### Median
Suitable for skewed data
Expensive to compute for large dataset, solution = approximate for grouped data
![[Pasted image 20241114205319.png]]

### Mode
Most occurring value in dataset
**Unimodal** - moderately skewed data:
$mean - mode = 3 \cdot (mean - median)$
Under [[Normal Distribution]] : $mean = mode = median$
#### Multi Modal
##### Bimodal
Two Peaks
Result of combining 2 different processes, eg. body mass of males and females

##### Trimodal

# Dispersion
## Variance ( $\sigma$ | s )
Population: $\sigma$
Sample: s

${\sigma}^2 = \dfrac{1}{N}\sum\limits_{i=1}^{N}{(x_i - \mu)^2}$
${s}^2 = \dfrac{1}{n-1}\sum\limits_{i=1}^{n}{(x_i - \bar{x})^2}$
Once rearranged:
Incremental and efficient computation of variance:

>[!INFO] Note:
Rearranging the formula to $\sigma^2 = \dfrac{1}{N} \cdot ({\sum{x_i^2} - N\mu^2})$ enables you to add datapoints incrementally

- This allows for incremental and efficient computation of variance, as the sum of squares (Σx_i^2) can be updated with each new data point.

>![INFO] Note
>This [video](https://www.youtube.com/watch?v=9ONRMymR2Eg) explains why we divide by $n-1$ in sample populations

## Graphical Displays
Boxplot - 5 number summary (min, $Q_1$, median, $Q_3$, max)
Histogram - x-axis are values, y-axis represent frequencies
Quantile plot - each value $x_i$ is paired with $𝑓_i$ indicating that approximately 100$f_i\%$ of data are $\leq x_i$
Quantile-quantile plot: graphs quantiles of univariant distribution against quantiles of another
Scatter Plot: pair of values plotted as points on a plane


### Boxplot
![[Pasted image 20241115083126.png|200]]
$Q_1$ = 25th percentile
$Q_2$ = 75th percentile

IQR $= Q_1 - Q_3$ 

**Outlier** - usually, a value higher/lower than $1.5×$ IQR $from Q_3/Q_1$

### Bar Chart
Plots categorical quantitative data
![[Pasted image 20241115083840.png|300]]
### Histogram
Shows distributions of variables represented by area
Plot binned quantitative data
![[Pasted image 20241115083829.png|300]]
### Quantile Plot
Plots quantile information for all data
![[Pasted image 20241115084106.png|400]]
### Quantile-quantile plot
Graphs quantiles of one univariate distribution against the corresponding quantiles of another

If the data distribution is close to normal, the plotted points will lie close to a sloped straight line

![[Pasted image 20241115084310.png|300]]
![[Pasted image 20241115084315.png|300]]
![[Pasted image 20241115084346.png|400]]

### Scatter Plot
![[Pasted image 20241115090559.png|600]]
![[Pasted image 20241115090627.png|400]]
![[Pasted image 20241115090646.png|500]]
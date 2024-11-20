![[Pasted image 20241114160628.png]]

![[Pasted image 20241114160634.png]]

More classes as compared to [[Logistic Regression]], classified by statistical properties of your data. Assumes [[Gaussian Distribution]] (have to remove outliers from data beforehand)
![[Pasted image 20241114145722.png]]

Linear Discriminant Analysis or LDA is an algorithm that provides an indirect approach to solve a [classification machine learning](https://www.projectpro.io/article/machine-learning-classification-projects-ideas/500 "classification machine learning") problem. To predict the probability, Pn(X) that a given feature, X belongs to a given class Yn or not, it assumes a density function of all the features that belong to that class. It then uses this density function, fn(X) to predict the probability Pn(X) using

![](https://dezyre.gumlet.io/images/blog/common-machine-learning-algorithms-for-beginners/image_757630234111657018213726.png?w=700&dpr=2.0)

where πn is the overall or prior probability that a randomly picked observation belongs to nth class.

Let the dataset have only feature variable, then the LDA assumes a Gaussian distribution function for fn(X) having a class-specific mean vector (ðÂœ‡n) and a covariance matrix that is applicable for all N classes. After that to assign a class to an observation from the testing data set, it evaluates the discriminant function

![](https://dezyre.gumlet.io/images/blog/common-machine-learning-algorithms-for-beginners/image_142754147151657018213742.png?w=700&dpr=2.0)

The  LDA classifier then predicts the class of the test variable for which the value of the discriminant function is the largest. We call this algorithm as “linear” discriminant analysis because, in the discriminant function, the component functions are all linear functions of x. 

**Note:** In the case of more than one variable, LDA assumes a  multivariate gaussian function and the discriminant function is scaled accordingly.
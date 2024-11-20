Calculates two probabilities:
- Probability of each class
- Conditional probabiliyu for each class given each $x$ value

Called Naive because it assumes all variables are independent

![[Pasted image 20241114150525.png]]
The formula is given by:  P(A|B) = P(B|A) * P(A) / P(B)
Where P(A|B) is the posterior probability of A given B, P(A) is the prior probability, P(B|A) is the likelihood which is the probability of B given A, and P(B) is the prior probability of B.

### **Advantages of the Naive Bayes Classifier Algorithm**

1. The Naive Bayes Classifier algorithm performs well when the input variables are categorical.
    
2. A Naïve Bayes classifier converges faster, requiring relatively little training data set than other discriminative models like logistic regression when the Naïve Bayes conditional independence assumption holds.
    
3. With the Naive Bayes Classifier algorithm, predicting the class of the testing data set is more effortless. A good bet for multi-class predictions as well.
    
4. Though it requires conditional independence assumption, Naïve Bayes Classifier has performed well in various application domains.
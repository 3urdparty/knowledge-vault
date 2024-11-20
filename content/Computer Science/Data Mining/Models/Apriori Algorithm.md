Apriori algorithm is an unsupervised ML algorithm that generates association rules from a given data set. The Association rule implies that if item A occurs, then item B also occurs with a certain probability. Most of the association rules generated are in the IF_THEN format. For example, IF people buy an iPad, they also buy an iPad Case to protect it. For the algorithm to derive such conclusions, it first observes the number of people who bought an iPad case while purchasing an iPad. This way a ratio is derived like out of the 100 people who purchased an iPad, 85 people also purchased an iPad case.

### **Principle on which Apriori Algorithm works**

1. If an item set frequently occurs, then all the subsets of the item set also happen often.
    
2. If an item set occurs infrequently, then all the supersets of the item set have infrequent occurrences.
### **Advantages of Apriori Algorithm**

1. It is easy to implement and can be parallelized easily.
    
2. Apriori implementation makes use of large item set properties.
K-means is a popularly used unsupervised ML algorithm for cluster analysis. K-Means is a non-deterministic and iterative method. The algorithm operates on a given data set through a pre-defined number of clusters, k. The output of the K Means algorithm is k clusters with input data partitioned among the clusters. For instance, let’s consider K-Means Clustering for Wikipedia Search results. The search term “Jaguar” on Wikipedia will return all pages containing the word Jaguar which can refer to Jaguar as a Car, Jaguar as Mac OS version, and Jaguar as an Animal. K Means clustering algorithm can be applied to group the web pages that talk about similar concepts. So, the algorithm will group all the web pages that refer to Jaguar as an Animal into one cluster, Jaguar as a Car into another cluster, and so on.

For any new incoming data point, the data point is classified according to its proximity to the nearby classes. Datapoints inside a cluster will exhibit similar characteristics while the other clusters will have different properties. The primary example of clustering would be grouping the same customers in a particular class for any marketing campaign, and it is also a practical algorithm for document clustering. 

The steps followed in the k means algorithm are as follows - 

1. Specify the number of clusters as k
    
2. Randomly select k data points and assign them to the clusters
    
3. Cluster centroids will be calculated subsequently
    
4. Keep iterating from 1-3 steps until you find the optimal centroid, after which values won’t change. 
    

i) The sum of the squared distance between the centroid and the data point is computed.

ii) Assign each data point to the cluster that is closer to the other cluster

iii) Compute the centroid for the cluster by taking the average of all the data points in the cluster

We can find the optimal number of clusters k by plotting the value of the sum squared distance which decreases gradually to reach an optimal number of k.

### **Advantages of using K-Means Clustering**

1. In the case of globular clusters, K-Means produce tighter clusters than hierarchical clustering.
    
2. Given a smaller value of K, K-Means clustering computes faster than hierarchical clustering for many variables.
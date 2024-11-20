**Similarity Measure** - function that quantifies similarity
**Dissimilarity Measure** - numerical measure of how different two objects are ($[0,1]$ or $[0, \infty)$ )

## Data Matrix
Characteristics in [[Data Characteristics]] describe single attributes, dissimilarity matrix uses multiple attributes
Data Matrix 
![[Pasted image 20241115091101.png|300]]

## Dissimilarity Matrix
Object by Object structure
Stores dissimilarity for **all pairs of objects**
Dissimilarity is distance $d(i,j)$
Usually symmetric (thus a triangular matrix)
Distance function are different for real, boolean, categorical, ordinal, ratio and vector
![[Pasted image 20241115091443.png|300]]

![[Pasted image 20241115091833.png|500]]

**Distance Functions**:
Quantitative:
- [[Minkowski Distance Function]]

Nominal:
- [[Simple Matching]]
- [[Large number of binary attributes]]

Ordinal:
![[Pasted image 20241115101157.png]]
![[Pasted image 20241115101213.png]]

Ratio-Scaled:
![[Pasted image 20241115101242.png]]
![[Pasted image 20241115101249.png]]
## Clustering 

**Title:** The Elements of Statistical Learning

**Authors:** Trevor Hastie, Robert Tibshirani, Jerome Friedman

page 520 - 

--- 

**Title:** Effect of Different Distance Measures on the Performance of K-Means Algorithm: An Experimental Study in Matlab [https://arxiv.org/pdf/1405.7471]

**Authors:** Dibya Jyoti Bora, Dr. Anil Kumar Gupta

Distance measures investigated:
- City Block (Manhattan)
- Euclidean distance
- Cosine distance
- Correlation distance


Results:
Cityblock is best computationally. Cosine takes more computation time in comparison.
While choosing distance, consider the number of attributes involved in the dataset.


## Clustering Stability

---

**Title:** Silhouettes: a graphical aid to the interpretation and validation of cluster analysis 

**Authors:** Peter J. ROUSSEEUW

--- 

**Title:** : Clustering Stability: An Overview

**Authors:** von Luxburg (2010)

Measures for 'distances' between clusterings:
- Rand index, Jaccard index, Hamming distance, minimal matching distance, Variation of Information distance
-  All these distances count, in some way or the other, points or pairs of points on which the two clusterings agree or disagre

If two clusterings are defined on different data sets one has two choices.
If the two data sets have a big overlap one can use a restriction operator
to restrict the clusterings to the points that are contained in both
data sets. On this restricted set one can then compute a standard
distance between the two clusterings. The other possibility is to use
an extension operator to extend both clusterings from their domain to
the domain of the other clustering. Then one can compute a standard
distance between the two clusterings as they are now both defined
on the joint domain. For center-based clusterings, as constructed by
the K-means algorithm, a natural extension operator exists. Namely,
to a new data point we simply assign the label of the closest cluster
center. A more general scheme to extend an existing clustering to new
data points is to train a classifier on the old data points and use its
predictions as labels on the new data points. However, in the context
of clustering stability it is not obvious what kind of bias we introduce
with this approach.


--- 

**Title:** : Stability estimation for unsupervised clustering: A review

**Authors:** Tianmou Liu, Han Yu, | Rachael Hageman Blair,


Unsupervised clustering requires subjective decisions to be made by the investigator in the selection
of measures that would define how similar items are. Often this decision is guided by the type of data that is being clustered, for example, continuous, binary, categorical, or a mixture thereof, and convenience of default built-in dissimilarity measures in clustering routine implementations. Choi et al. (2010) put this issue into perspective when they
examined 76 measures for similarity of binary data alone. Arguably, there are at least as many for continuous data.
Another point of uncertainty is with the investigator's selection of the clustering algorithm. Different clustering algorithms have different optimization functions and therefore differ in how they establish similarity within a grouping (Rand, 1971; Rokach & Maimon, 2005). Estivill-Castro (2002) attribute a large number of clustering algorithms as a
reflection of the fact that a cluster cannot be precisely defined.


--- 

**Title:** CLOSE — parameter-free temporal stability evaluation

**Authors:** - Klassen et al. (2022) Applied Intelligence 


- Most methods focus on tracking individual times series, not the entire database
- Evolutionary clustering is a research field proposed to improve time series clustering
- It states :  each clustering should be similar to the clustering of its predecessor, while accurately reflecting the properties of its own data
- uses an extended definition of evolutionary clustering instead of targeting the similarity of two successive clusterings they demand the similarity of a clustering to all
previous clusterings, they call this the over-time stability




--- 

**Title:** 

**Authors:** 

--- 

- Spiliopoulou et al. (2006) KDDMONIC — cluster event taxonomy (survive/split/merge/die)


2003). 

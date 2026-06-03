**21st May**
Want to apply different metrics and methods of visualising the clusters to obtain a robust idea of what occurs during clustering, so we can aim to evaluate the performance of the clusters more comprehensively. This gives interpretability and here we can link back to the original SOC motivation, this interpretability can help with understanding.

Variations in the metric will result in different clusters, both in terms of the number and the size. Failure to normalise data results in data with high numerical values being weighted more heavily than others --> poor measurements --> poor clustering. [K-Means]

**27th May**

How to choose the distance measure in k-means, for example (i.e euclidean or cosine, or others).
What features should you choose to help model normal behaviour?


Need to consider, when i aggregate and take features such as number of authentications, are we still taking raw counts or counts per minute.
Sparse windows can skew the failure ratio for example.

With these considerations above, am I trying to just see how the clustering changes/ the stability of clustering changes? If we just keep raw auth counts and raw failure ratio then this is part of the model, and we are seeing how things change.

- Consider *log* transforming the counts.


**28th May**
Tried 1-hour bins for 1 day and 10 days with k = 3 clusters.

For 10 days I computed silhouette metric but stopped running after 1 hour, silhoutte scales like o(n^2) its computationally expensive, can think of maybe using other metrics or scaling down the size of the dataset.

**29th May**
- go through clustering anomaly detection literature & see what algorithms/metrics they use - what is the goal of their choices
- can use multiple clustering algorithms and see if they give similar results - this is a talking point
- When making choices or discarding things, always justify why
- For the clustering algorithm, state what we need e.g (scalable, other properties),
- What clustering algorithms could we have used if scalability or other things were not a problem [for example algorithms that handle mixed types - continuous and discrete]
- Colinearity of features is not as much of a problem can just uplift things


**3rd June**


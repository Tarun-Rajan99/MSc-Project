---------------------------------------------------------------------
`Sanchez2022` [https://www.mdpi.com/2227-7390/10/21/4043]

**Title:** Design and Evaluation of Unsupervised Machine Learning Models for Anomaly Detection in Streaming Cybersecurity Logs
**Authors:** Carmen Sánchez-Zas*, Xavier Larriva-Novo , Víctor A. Villagrá , Mario Sanz Rodrigo
and José Ignacio Moreno

**Key words:** machine learning; clustering; real-time; data pre-processing; threshold; Spark; cybersecurity; K-means; anomaly detection; logs

In this paper, Sachez et al (2022) propose three unsupervised machine learning models based on clustering techniques (K-Means, Bisecting K-Means, and GMM) and threshold definitions to detect anomalies from heterogeneous streaming cybersecurity logs. They compared WSSSE, Silhouette, and training time metrics for all models, where K-Means was defined as the optimal algorithm for anomaly detection in streaming data processing.

After comparing and selecting clustering algorithms, they developed a thresholding system to classify anomalous data.

Tips:
- Pre-processing is vital to ensure correct inputs to the system
- WSSSE and Silhouette used to select hyperparameters
- The section on what clustering is and the maths behind it is useful
- Need to normalise the data before running it through the models (K-Means uses distances to generate clusters)
- Within Set Sum of Squared Error (WSSSE) - want to reduce this without overfitting (elbow plot)
- Hyperparameter optimisation may be computationally too expensive in some cases

---------------------------------------------------------------------
`Trittenbach2019`

**Title:** Understanding the effects of temporal energy-data aggregation on clustering quality{Journal, YYYY} (NN pages)._

**Authors:** Holger Trittenbach*, Jakob Bach, and Klemens Böhm (optional affiliations)_



- They identified spurious improvement of clustering validity indices, i. e., data aggregation may boost index values without real improvement in clustering quality
- A consequence is that our guidelines strongly advise to validate clustering results against randomly generated sequences
- Some clusters prefer a spherical shape, (Connectivity as a neighborhood-based index) connectivity works well for clusters of arbitrary shape
- Can use 'base level' and 'current level' for validaiton


---------------------------------------------------------------------


# Template for new entries 

---------------------------------------------------------------------
`firstauthorYYYYword`

**Title:** _Title goes here. {Journal, YYYY} (NN pages)._

**Authors:** _Author One, Author Two and Author Three. (optional affiliations)_

**Key words:** _key word 1_, _key word 2_, _key work 3_. 

1. _What_ is the document and _what_ does it say? 
2. _How_ do they do / show this?
3. _Why_ are they bothering to do this in the first place?
4. _Who_ is the intended audience for this work?

In this DOC_TYPE, AUTHOUR VERB that THESIS\_STATEMENT.
They DO/SHOW this by ACTIONS. 
This is important to PEOPLE because REASONS. 
This work would be useful when PEOPLE are doing ACTIVITY.

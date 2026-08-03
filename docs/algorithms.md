# Clustering Algorithms

> **Estimated reading time:** 8 min<br>
> **Prerequisites:** Clustering Approaches<br>
> **Related topics:** Model Selection, Cluster Evaluation

---

## Overview

Clustering algorithms group observations according to different definitions of similarity. This section examines four representative methods: K-Means, Agglomerative Clustering, DBSCAN and Gaussian Mixture Models.

Each algorithm makes assumptions about cluster geometry, density and membership. Understanding those assumptions is essential when selecting a method for a specific dataset.

---

## Algorithm Comparison

| Algorithm | Approach | Cluster Shape | Noise Handling | Membership |
|---|---|---|---|---|
| K-Means | Centroid-based | Compact and approximately spherical | No explicit handling | Hard |
| Agglomerative | Hierarchical | Depends on linkage and distance | No explicit handling | Hard |
| DBSCAN | Density-based | Arbitrary shapes | Explicitly identifies noise | Hard |
| GMM | Probabilistic | Elliptical | No explicit handling | Soft |

---

## K-Means

K-Means partitions observations into a predefined number of clusters, represented by their centroids. Its objective is to minimize the distance between each observation and the centroid of its assigned cluster.

### Mechanism

1. Select the number of clusters, **K**.
2. Initialize K centroids.
3. Assign each observation to its nearest centroid.
4. Recalculate each centroid using the mean of its assigned observations.
5. Repeat assignment and update steps until the solution stabilizes.

The algorithm minimizes the **Within-Cluster Sum of Squares (WCSS)**: the total squared distance between every observation and the centroid of its assigned cluster.

### Main Hyperparameters

| Hyperparameter | Purpose |
|---|---|
| `n_clusters` | Defines the number of clusters. |
| `init` | Controls centroid initialization. |
| `n_init` | Sets the number of independent initializations. |
| `max_iter` | Limits the iterations for each run. |

### Advantages

- Fast and scalable for large numerical datasets.
- Straightforward to implement and interpret.
- Produces stable results when clusters are compact and well separated.

### Limitations

- Requires the number of clusters in advance.
- Sensitive to feature scale, initialization and outliers.
- Performs poorly with irregular shapes or clusters of very different sizes.

### Typical Applications

- Customer segmentation
- Document grouping
- Image compression
- Exploratory market analysis

---

## Agglomerative Clustering

Agglomerative Clustering builds a hierarchy from individual observations. It begins with every observation in its own cluster and repeatedly merges the two closest clusters until the requested number remains.

### Mechanism

1. Treat each observation as an independent cluster.
2. Calculate distances between clusters.
3. Merge the closest pair.
4. Recalculate inter-cluster distances according to the selected linkage rule.
5. Continue until the stopping condition is reached.

The resulting hierarchy can be represented with a **dendrogram**, which shows both the sequence of merges and the distances at which they occur.

### Linkage Strategies

| Linkage | Definition | Practical Effect |
|---|---|---|
| Single | Minimum pairwise distance | Can recover elongated groups but may create chains. |
| Complete | Maximum pairwise distance | Encourages compact, well-separated clusters. |
| Average | Mean pairwise distance | Provides a balance between single and complete linkage. |
| Ward | Increase in within-cluster variance | Favors compact clusters and commonly uses Euclidean distance. |

### Advantages

- Reveals hierarchical relationships in the data.
- Does not require random centroid initialization.
- Supports several distance metrics and linkage strategies.

### Limitations

- Computational and memory costs increase rapidly with dataset size.
- Early merges cannot be reversed.
- Results may change substantially with the distance and linkage choices.

### Typical Applications

- Taxonomy construction
- Gene expression analysis
- Document organization
- Exploratory segmentation

---

## DBSCAN

DBSCAN, or **Density-Based Spatial Clustering of Applications with Noise**, identifies connected regions of high observation density. Sparse observations are classified as noise instead of being forced into a cluster.

### Core Concepts

| Concept | Definition |
|---|---|
| Core point | Has at least `min_samples` observations within its `eps` neighborhood. |
| Border point | Is reachable from a core point but does not satisfy the core-point condition. |
| Noise point | Is not density-reachable from a core point. |

### Mechanism

1. Select an unvisited observation.
2. Find all observations within radius `eps`.
3. Create or expand a cluster when the neighborhood contains at least `min_samples`.
4. Continue through density-reachable observations.
5. Mark observations outside dense regions as noise.

### Main Hyperparameters

| Hyperparameter | Purpose |
|---|---|
| `eps` | Defines the maximum neighborhood radius. |
| `min_samples` | Defines the minimum density required to form a core point. |
| `metric` | Determines how distances are calculated. |

### Advantages

- Discovers clusters with irregular shapes.
- Does not require the number of clusters in advance.
- Identifies potential outliers explicitly.

### Limitations

- Sensitive to the scale of the input features.
- Parameter selection can be difficult.
- Struggles when clusters have substantially different densities.
- Distance measures become less informative in high-dimensional spaces.

### Typical Applications

- Spatial analysis
- Anomaly detection
- Geographic event grouping
- Pattern discovery with noise

---

## Gaussian Mixture Models

A Gaussian Mixture Model represents the data as a weighted combination of Gaussian distributions. Unlike hard clustering methods, GMM estimates the probability that each observation belongs to every component.

### Mechanism

GMM is commonly fitted with the **Expectation-Maximization (EM)** algorithm:

1. Initialize component means, covariance matrices and weights.
2. **Expectation step:** estimate membership probabilities for every observation.
3. **Maximization step:** update model parameters using those probabilities.
4. Repeat until the likelihood converges.

The estimated probability density is the weighted sum of the component distributions. Each component is defined by a weight, a mean and a covariance matrix.

### Main Hyperparameters

| Hyperparameter | Purpose |
|---|---|
| `n_components` | Defines the number of Gaussian components. |
| `covariance_type` | Controls the shape and flexibility of component covariance. |
| `n_init` | Sets the number of initializations. |
| `reg_covar` | Adds numerical stability to covariance estimates. |

### Advantages

- Provides probabilistic membership scores.
- Models overlapping and elliptical clusters.
- Supports flexible covariance structures.

### Limitations

- Requires the number of components in advance.
- Sensitive to initialization and distributional assumptions.
- More computationally complex than K-Means.
- May converge to a local optimum.

### Typical Applications

- Probabilistic segmentation
- Density estimation
- Speaker recognition
- Population modeling

---

## Selecting an Algorithm

| Data Characteristic | Suitable Starting Point |
|---|---|
| Large dataset with compact groups | K-Means |
| Meaningful nested structure | Agglomerative Clustering |
| Irregular shapes with noise | DBSCAN |
| Overlap or uncertain membership | Gaussian Mixture Models |

Algorithm selection should remain an empirical process. Feature scaling, exploratory visualization, hyperparameter tuning and evaluation metrics should be considered together rather than treating the algorithm name as a guarantee of quality.

---

## Key Takeaways

- K-Means is efficient but assumes compact clusters and requires K.
- Agglomerative Clustering provides a hierarchy but can be expensive at scale.
- DBSCAN discovers irregular shapes and noise but is sensitive to density parameters.
- GMM models uncertainty through soft probabilistic assignments.
- The most appropriate method depends on the structure, scale and purpose of the analysis.

---

## Previous

Return to [Clustering Approaches](clustering-approaches.md).

## Next

Continue with [Clustering Evaluation](evaluation.md).

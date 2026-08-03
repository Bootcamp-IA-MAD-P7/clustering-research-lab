# Clustering Research Lab

Research, experiments, and technical documentation on clustering algorithms.

**Machine Learning Bootcamp · Task 5**<br>
**Author: Gaby Granja**

## Project Overview

Clustering Research Lab is an academic Machine Learning project focused on the foundations and practical application of unsupervised learning. It combines structured technical documentation with a reproducible Jupyter Notebook that compares four representative clustering algorithms on synthetic data and explores a three-dimensional projection of the Iris dataset.

The project is documented with Material for MkDocs and includes generated visual outputs for algorithm behavior, model selection, and cluster evaluation.

## Learning Objectives

- Explain the role of clustering within unsupervised learning.
- Distinguish centroid-based, hierarchical, density-based, and probabilistic approaches.
- Understand the mechanisms, strengths, and limitations of four clustering algorithms.
- Apply the Elbow Method and Silhouette Analysis to cluster evaluation.
- Compare algorithm behavior on a consistent synthetic dataset.
- Interpret clustering results through two-dimensional and three-dimensional visualizations.

## Repository Structure

```text
.
├── docs/
│   ├── stylesheets/
│   │   └── extra.css
│   ├── algorithms.md
│   ├── clustering-approaches.md
│   ├── conclusions.md
│   ├── evaluation.md
│   ├── fundamentals.md
│   └── index.md
├── images/
│   ├── agglomerative_clusters.png
│   ├── dbscan_clusters.png
│   ├── elbow_method.png
│   ├── gmm_clusters.png
│   ├── iris_kmeans_3d.png
│   ├── kmeans_clusters.png
│   ├── silhouette_scores.png
│   └── unlabeled_dataset.png
├── notebooks/
│   └── clustering_experiments.ipynb
├── .gitignore
├── LICENSE
├── README.md
├── mkdocs.yml
└── requirements.txt
```

Generated directories such as `.venv/` and `site/` are intentionally excluded from version control.

## Technologies Used

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- MkDocs
- Material for MkDocs
- Markdown
- Mermaid
- Git and GitHub

## Documentation Overview

The MkDocs site organizes the theoretical research into five sections:

| Section | Scope |
|---|---|
| [Fundamentals](docs/fundamentals.md) | Unsupervised learning and core clustering concepts |
| [Clustering Approaches](docs/clustering-approaches.md) | Centroid-based, hierarchical, density-based, and probabilistic methods |
| [Algorithms](docs/algorithms.md) | Mechanisms, hyperparameters, advantages, limitations, and applications |
| [Evaluation](docs/evaluation.md) | Elbow Method, Silhouette Score, and hyperparameter selection |
| [Conclusions](docs/conclusions.md) | Comparative findings and practical recommendations |

## Experimental Notebook

The notebook at [`notebooks/clustering_experiments.ipynb`](notebooks/clustering_experiments.ipynb) provides a reproducible comparison of:

- Synthetic datasets
- K-Means
- Agglomerative Clustering
- DBSCAN
- Gaussian Mixture Models
- Elbow Method
- Silhouette Analysis
- 3D Iris visualization

The experiments use a shared synthetic dataset where appropriate, making the visual differences between clustering strategies easier to evaluate.

## Algorithms Covered

| Algorithm | Approach | Main Characteristic |
|---|---|---|
| K-Means | Centroid-based | Efficient partitioning around cluster centroids |
| Agglomerative Clustering | Hierarchical | Bottom-up construction of a cluster hierarchy |
| DBSCAN | Density-based | Detection of irregular clusters and noise |
| Gaussian Mixture Models | Probabilistic | Soft assignments based on Gaussian components |

## Visual Experiments

The repository includes generated figures for:

- The original unlabeled synthetic dataset
- K-Means cluster assignments
- Agglomerative cluster assignments
- DBSCAN clusters and detected noise
- Gaussian Mixture Model assignments
- Elbow Method results
- Silhouette score comparison
- Three-dimensional K-Means visualization of the Iris dataset after PCA

All exported figures are stored in the [`images/`](images/) directory.

## Installation

Clone the repository:

```bash
git clone https://github.com/Bootcamp-IA-MAD-P7/clustering-research-lab.git
cd clustering-research-lab
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on macOS or Linux:

```bash
source .venv/bin/activate
```

On Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Install the project dependencies:

```bash
pip install -r requirements.txt
```

## Running MkDocs

Start the local documentation server on port `8080`:

```bash
python -m mkdocs serve -a 127.0.0.1:8080
```

Then open [http://127.0.0.1:8080/clustering-research-lab/](http://127.0.0.1:8080/clustering-research-lab/) in a browser.

## Running the Notebook

With the virtual environment active, launch the notebook:

```bash
python -m jupyter notebook notebooks/clustering_experiments.ipynb
```

Run the cells in order to reproduce the analysis and generated visualizations.

## Future Improvements

- Extend the comparison to datasets with different shapes, densities, and noise levels.
- Add systematic sensitivity analysis for algorithm hyperparameters.
- Compare additional internal clustering evaluation metrics.
- Expand the discussion of computational performance on larger datasets.

## Project Soundtrack

Some projects deserve a soundtrack.

If you'd like to experience the same atmosphere that accompanied the research, documentation and experiments, you can listen to the project's playlist:

🎧 **git push, don't panic**

https://open.spotify.com/playlist/2YD1yp1PxdlyK4xFc0HF07

> Built during the AI Bootcamp, one commit at a time.

## Author

**Gaby Granja**<br>
Machine Learning Bootcamp · 2026

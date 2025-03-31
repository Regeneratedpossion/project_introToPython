# Gaussian Mixture Model (GMM) Toolkit

![License](https://img.shields.io/badge/License-MIT-blue.svg)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)

A Python package for generating, analyzing, and visualizing Gaussian Mixture Models. Perfect for clustering tasks and EM algorithm demonstrations.

## 1. Introduction

This repository provides a complete toolkit for working with 2D Gaussian Mixture Models, featuring:
- Synthetic data generation with configurable parameters
- Expectation-Maximization (EM) algorithm implementation
- Interactive visualization of components and convergence
- Cluster analysis with covariance ellipses

**Key Features:**
- 🎯 Generate synthetic 2D GMM datasets with ground truth labels
- 🔍 EM implementation with K-means or random initialization
- 📈 Track log-likelihood convergence during training
- 🎨 Visualize components with covariance ellipses and mean markers
- 🧪 Built-in examples for quick experimentation

## 2. Installation

### Requirements
- Python 3.8+
- `numpy`
- `scipy`
- `matplotlib`
- `seaborn`
- `scikit-learn`

### Install via pip
```bash
pip install git+https://github.com/your-username/gmm-toolkit.git

from gmm_toolkit import generate_gmm_2d, plot_gmm_2d, gmm_em, plot_em_results

# 1. Generate synthetic data
X, y = generate_gmm_2d(
    K=3,
    n_samples=1000,
    means=[[1,1], [5,5], [9,1]],
    covariances=[
        [[1,0], [0,1]],
        [[2,0.5], [0.5,1]],
        [[1,-0.7], [-0.7,2]]
    ],
    weights=[0.3, 0.4, 0.3]
)

# 2. Visualize ground truth
plot_gmm_2d(X, y, means, covariances)

# 3. Run EM algorithm
params = gmm_em(X, K=3, init_method='kmeans')

# 4. Analyze results
plot_em_results(X, params)

# Initialize with specific means
params = gmm_em(
    X, 
    K=3,
    init_method='random',  # Try 'kmeans' for smarter init
    max_iter=200,
    tol=1e-8
)

# Access estimated parameters
print(f"Mixing weights: {params['weights']}")
print(f"Component means:\n{params['means']}")

# Initialize with specific means
params = gmm_em(
    X, 
    K=3,
    init_method='random',  # Try 'kmeans' for smarter init
    max_iter=200,
    tol=1e-8
)

# Access estimated parameters
print(f"Mixing weights: {params['weights']}")
print(f"Component means:\n{params['means']}")

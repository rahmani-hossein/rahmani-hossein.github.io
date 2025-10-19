---
title: "Manifold Sampling for Data Synthesis"
collection: portfolio
permalink: /portfolio/manifold-sampling
excerpt: "Implementation of the SUGAR Algorithm for data generation in Multi-Manifold Clustering, including a comprehensive benchmark of clustering algorithms."
date: 2022-12-01
link: "https://github.com/rahmani-hossein/Data-Synthesis"
---

A comprehensive implementation of the **SUGAR (Synthetic Uniform Generator for Additive noise from Random manifolds)** algorithm for synthetic data generation on manifolds, developed for the OPTIMIZER competition at Sharif University of Technology's SOAL laboratory.

## Project Overview

This project tackles the challenging problem of multi-manifold clustering by implementing state-of-the-art data synthesis techniques and benchmarking multiple clustering algorithms. The SUGAR algorithm generates realistic synthetic data lying on lower-dimensional manifolds embedded in high-dimensional spaces, providing controlled test cases for evaluating clustering methods.

## Technical Implementation

### Data Synthesis
- **SUGAR Algorithm**: Generates data points uniformly distributed on user-defined manifolds with additive Gaussian noise
- **Manifold Specification**: Supports arbitrary smooth manifolds defined by parameterizations
- **Noise Control**: Configurable noise levels to test algorithm robustness

### Clustering Algorithms Benchmarked
- **Hierarchical Clustering**: Agglomerative methods with various linkage criteria
- **Spectral Clustering**: Graph-based methods leveraging eigenvectors of similarity matrices
- **K-Means**: Classic centroid-based partitioning
- **Gaussian Mixture Models (GMM)**: Probabilistic clustering with EM algorithm
- **Density-Based Methods**: DBSCAN and variants for arbitrary-shaped clusters

### Dimensionality Reduction & Visualization
- **PCA (Principal Component Analysis)**: Linear dimensionality reduction for initial data exploration
- **t-SNE (t-Distributed Stochastic Neighbor Embedding)**: Non-linear manifold learning for high-quality 2D/3D visualizations
- **Cluster Comparison Metrics**: Adjusted Rand Index, Normalized Mutual Information, Silhouette scores

## Competition Context

Developed for the **OPTIMIZER competition** featuring 30+ teams, this benchmark system enabled rigorous evaluation of clustering algorithms on synthetic manifolds with ground-truth labels. The controlled experimental setup allowed for systematic comparison of algorithm performance across varying manifold geometries, dimensions, and noise levels.

## Key Contributions

- Modular implementation of SUGAR allowing easy manifold definition
- Comprehensive clustering algorithm benchmark suite
- Visualization pipeline for qualitative assessment of clustering quality
- Quantitative evaluation framework with multiple clustering metrics

This project demonstrates expertise in unsupervised learning, manifold theory, and rigorous algorithm evaluation methodologies.

[View on GitHub](https://github.com/rahmani-hossein/Data-Synthesis) · [Competition Details](https://github.com/rahmani-hossein/Data-Synthesis#optimizer-competition)

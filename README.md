# Merlin - Milvus Integration with Milvus Performance Benchmarks

This repo describes how to use Milvus vector database indexing and search framework in combination with [NVIDIA Merlin](https://github.com/NVIDIA-Merlin),
an open-source framework for developing recommenders systems at any scale.

There are two notebooks provided for guidance. [Notebook 01](https://github.com/bbozkaya/merlin-milvus/blob/main/notebooks/01-Build-RecSys-with-Merlin-Milvus.ipynb)
demonstrates how to use Merlin Models library to train a model and export embeddings vectors for users and items based on interaction data from an
e-commerce system. [Notebook 02](https://github.com/bbozkaya/merlin-milvus/blob/main/notebooks/02-Deploy-Multi-Stage-RecSys-with-Merlin-Systems-Milvus.ipynb)
shows how to use a customer Merlin Systems operator as an interface between Milvus server and NVIDIA Triton Inference Server, for making inference
queries on user-item similarity.

The results folder provides information on several performance benchmark conducted with Milvus framework using the user and item embeddings
calculated in Notebook 01. Milvus is GPU-accelerated and shows improved and much needed performance for real-life RecSys usecases and datasets,
so be sure to take a look at the benchmark performance results.

A blog post about all the work conducted is available here once published.

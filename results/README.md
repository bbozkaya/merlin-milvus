# Detailed Benchmark Results

To demonstrate the case for using a fast and efficient vector indexing/search library such as Milvus, and reporting on its performance, we have designed two sets of benchmarks.

- Using Milvus to build vector indexes with the two sets of embeddings we generated with Merlin: 1) user embeddings for 7.3M unique users, split as 85% train set (for indexing) and 15% test set (for querying), and 2) item embeddings for 49K products (with a 50-50 train-test split). This benchmark is done independently for each vector dataset and results are reported separately.
- Using Milvus to build a vector index for the 49K item embeddings dataset, and querying the 7.3M unique users against this index to retrieve most similar/relevant top k items.



There are two notebooks provided for guidance. [Notebook 01](https://github.com/bbozkaya/merlin-milvus/blob/main/notebooks/01-Build-RecSys-with-Merlin-Milvus.ipynb)
demonstrates how to use Merlin Models library to train a model and export embeddings vectors for users and items based on interaction data from an
e-commerce system. [Notebook 02](https://github.com/bbozkaya/merlin-milvus/blob/main/notebooks/02-Deploy-Multi-Stage-RecSys-with-Merlin-Systems-Milvus.ipynb)
shows how to use a customer Merlin Systems operator as an interface between Milvus server and NVIDIA Triton Inference Server, for making inference
queries on user-item similarity.


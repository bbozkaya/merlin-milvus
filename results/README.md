# Detailed Benchmark Results

To demonstrate the case for using a fast and efficient vector indexing/search library such as Milvus, and reporting on its performance, we have designed two sets of benchmarks.

- Using Milvus to build vector indexes with the two sets of embeddings we generated with Merlin: 1) user embeddings for 7.3M unique users, split as 85% train set (for indexing) and 15% test set (for querying), and 2) item embeddings for 49K products (with a 50-50 train-test split). This benchmark is done independently for each vector dataset and results are reported separately.
- Using Milvus to build a vector index for the 49K item embeddings dataset, and querying the 7.3M unique users against this index to retrieve most similar/relevant top k items.

We considered the following settings and variations of parameters in these benchmarks:
- Vector dataset: item embeddings (49K), user embeddings (7.3M)
- Top-k (k most similar items): 100
- Index type: HNSW, IVFPQ
- Insert parameters:
  + batch: 100
- Index hyperparameters:
  + HNSW:
    - m: 4, 8, 12, 16, 24, 36, 48, 64
    - efConstruction: 500
  + IVFPQ:
    - nList: 100, 200, 400
    - m: 64   (where embedding size Mod m = 0) 
    - nbits: 12
- Query hyperparameters:
  + HNSW:
    - nq: 1000
    - ef: 10, 20, 40, 80, 120, 200, 400, 600, 800
  + IVFPQ:
    - nq: 1000
    - nprobe: 5, 10, 20
- CPU vs. GPU
  + CPU: IntelⓇ Epyc 7642 / 2.3 Ghz with 2x48 CPU cores and 1 TB memory
  + GPU: NVIDIA A100 single GPU with 80 GB memory

Overall, we report recall vs. QPS (queries per second) tradeoff as well as well CPU times and GPU speedup factors.

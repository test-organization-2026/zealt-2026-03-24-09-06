Data-parallel workloads, such as processing large datasets for machine learning, require efficient horizontal scaling and external storage integration.

You need to implement a data ingestion script that utilizes Modal's `.map()` primitive to concurrently read and process a simulated batch of 1,000 Parquet files. The application must access these files by mounting an external Amazon S3 or Cloudflare R2 bucket directly into the container's file system using `modal.CloudBucketMount`.

**Constraints:**
- Must strictly utilize `.map()` or `.starmap()` to distribute the workload across multiple dynamically spun-up containers.
- Must use `modal.CloudBucketMount` for data access; do not download files sequentially to local disk.
- Must configure an explicit timeout limit to prevent runaway execution costs.
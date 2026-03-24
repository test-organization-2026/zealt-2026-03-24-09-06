Efficiently serving Large Language Models (LLMs) requires mitigating GPU cold starts and minimizing perceived user latency through real-time output.

You need to deploy an LLM inference endpoint that explicitly requests an H100 GPU (`gpu="H100"`) and leverages a generator function (using the `yield` keyword) to stream generated tokens back to the client. The setup must be configured to utilize Modal's GPU memory snapshotting to demonstrate sub-second cold boot times.

**Constraints:**
- Must use the `yield` keyword to stream responses; do not wait for the entire generation sequence to complete before returning data.
- Must explicitly define hardware requirements using the `@app.function` decorator parameters.
- Must configure the app to scale to zero (`min_containers=0`) to accurately trigger and test cold start snapshot restoration.
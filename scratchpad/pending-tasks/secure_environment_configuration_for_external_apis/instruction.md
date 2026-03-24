Handling sensitive API keys securely is a critical developer pain point for AI workflows that rely on external foundational models or proprietary datasets.

You need to provision a complex container environment starting from the specific NVIDIA CUDA registry base (`nvidia/cuda:12.8.0-devel-ubuntu22.04`). The application must securely authenticate and inject an external API key (e.g., Hugging Face or OpenAI) into the container environment at runtime to download a restricted asset.

**Constraints:**
- Do NOT hardcode any API keys or sensitive credentials within the Python code or the `modal.Image` definition chain.
- Must strictly utilize `modal.Secret` to inject the necessary environment variables at runtime.
- Must successfully build the container using the exact specified NVIDIA CUDA base image.
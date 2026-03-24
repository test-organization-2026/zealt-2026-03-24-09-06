Modal has recently evolved its architectural primitives, deprecating the traditional `Stub` object in favor of the `App` object for deployment orchestration. 

You need to write a Python script that initializes a `modal.App`, builds a custom container environment from a Debian slim base using `.pip_install()` for basic dependencies, and synchronously executes a "Hello World" function via `.remote()`.

**Constraints:**
- Do NOT use or reference the deprecated `Stub` object (it must use `modal.App`).
- The `modal.Image` must be constructed programmatically within the Python code.
- Do NOT attach GPUs or complex hardware requests for this baseline initialization task.
Serverless applications are inherently ephemeral, making cross-container state synchronization critical for handling concurrent web requests.

You need to deploy a FastAPI application on Modal that acts as a web webhook or REST API using the `@modal.asgi_app` decorator. The endpoint must implement a simple hit counter or request tracker that stores and updates its state securely in a distributed `modal.Dict`. 

**Constraints:**
- Must use `modal.Dict` to track state across concurrent function replicas.
- Must expose a valid HTTPS endpoint using Modal's ASGI or Web Server decorators.
- Do NOT use external databases (e.g., PostgreSQL, Redis) for state tracking.
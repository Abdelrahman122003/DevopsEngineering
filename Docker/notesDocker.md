## Default Network

1. Bridge Network:
   - Default: The default network driver for containers if no network is specified.
   - Purpose: Allows containers to communicate with each other on the same host.
   - Use Case: Suitable for standalone applications or microservices that run on a single host.
2. Host Network:
   - Behavior: The container shares the host's networking namespace, meaning it directly uses the host's IP address and ports.
   - Use Case: Useful for high-performance scenarios where you want to avoid the overhead of network isolation.
3. None Network:
   - Behavior: Completely disables networking for the container.
   - Use Case: Useful for containers that do not require network access.

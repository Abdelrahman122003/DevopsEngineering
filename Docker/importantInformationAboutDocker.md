> ## Docker Daemon

The Docker daemon (dockerd) is a background service that manages Docker containers on a host system. It listens for Docker API requests and performs various tasks related to container management, such as building, running, and distributing Docker containers. The daemon communicates with other Docker daemons to manage Docker services and is essential for the operation of Docker. The Docker client (docker) is used to interact with the Docker daemon, sending commands that the daemon executes.

> ## Docker Engine Overview

Docker Engine is the core software that enables the creation, management, and orchestration of containers. It includes both the Docker daemon and the Docker client, providing the fundamental tools for containerized application development and deployment.

**Key Components**

1. Docker Daemon (dockerd):

   - A background service that manages Docker containers on a host.
   - Listens for Docker API requests and performs actions like building, running, and monitoring containers.

2. Docker Client (docker):

   - A command-line interface (CLI) tool that allows users to interact with the Docker daemon.
   - Sends commands to the Docker daemon to perform tasks like creating and managing containers.

3. Docker API:

   - Provides an interface for the Docker client and other tools to communicate with the Docker daemon.
   - Enables automation and integration with other software and systems.

4. Container Runtime:

   - The environment in which Docker containers run.
   - Docker Engine uses container runtimes like runc to execute containers according to the OCI (Open Container Initiative) specifications.

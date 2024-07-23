How to install docker

https://docs.docker.com/engine/install

## Command for Containers(`container`)

1. List containers

   ```bash
   # This command lists all containers, including running, stopped, and exited containers.
   docker ps -a
   # it shows containers that are currently active and running.
   docker container ls
   docker ps
   ```

2. Start a new container

   ```bash
    # to run a new container
    docker run --name name-of-your-container image-name
    # -i (interactive): Keeps the standard input (stdin) open for the container, allowing you to interact with it.
    # -t (tty): Allocates a pseudo-TTY, which gives you a terminal interface. This is what makes the interactive shell possible.
    docker run -it ubuntu bash
   ```

3. Start a container that was started before

   ```bash
   docker start name-of-your-container

   # To open an interactive bash session for a specific container, use this command:
   docker start -ai name-of-your-container
   ```

4. Stop a container

   ```bash
   # to stop container
   docker stop {Container ID} or {name}
   ```

5. Remove a container

   ```bash
   docker container rm {Container ID} or {name}
   ```

6. Execute a command for a running container

   ```bash
    # to run command in specific container use this command:
    docker exec {CONTAINER ID, NAMES} your_command_that_you_want
    #  to open a bash shell inside the container:
    docker exec -it {CONTAINER ID, NAMES
    docker exec -it name-of-your-container /bin/bash
   ```

7. To show

   ```bash
   # The docker inspect command is used to retrieve detailed information about Docker objects, such as containers, images, networks, and volumes. It provides a JSON output that contains configuration and status details for the specified object.
   docker inspect ubuntu
   ```

8. Remove all stopped containers

   ```bash
   docker container prune
   ```

9. `attach` Command

   The attach command in Linux, particularly in the context of Docker, is used to connect your terminal to a running container. This allows you to view the output and interact with the container directly.
   ![alt text](image-1.png)

   ```bash
   docker attach {CONTAINER ID, NAME}
   ```

10. Port Mapping

    Port mapping is a process that allows network traffic to be redirected from one port on a host machine to a different port on a container or virtual machine.

    ```bash
    docker run -p <host_port>:<container_port> <image_name>
    ```

    - Purpose: It allows services running inside containers to be accessible from the outside world.
    - Mechanism: It maps a port on the host to a port on the container.
    - Example: If you map port 3000 on the host to port 80 on a container, accessing http://localhost:3000 on the host will redirect traffic to port 80 on the container, where a service (like a web server) is running.

    ```bash
    docker run -p 3000:80 nginx
    ```

- The `-p` flag in the docker run command is used to publish a container's port or a range of ports to the host. It essentially maps the specified port(s) on the host to the specified port(s) on the container.

11. Important flags

- `-d` flag:<br>
  Run containers in the background to allow multiple containers to run simultaneously without keeping the terminal session busy, ensuring your terminal remains free for other commands and operations while still allowing access to the container's logs using docker logs <container_id_or_name> to see what’s happening inside the container.

## Command for images(`image`)

1. Run image

   ```bash
   # creates and starts a new container from the specified image and downloads the image from Docker Hub if it does not already exist locally.
   docker run image-name
   ```

2. Pull Image

   ```bash
   # to get image without run it use this command
   docker pull author_name/image_name:version(by default-> latest)
   ```

3. List images

   ```bash
   docker images
   docker image ls
   ```

4. Remove image
   ```bash
   docker image rm {REPOSITORY} or {IMAGE ID}
   docker rmi {REPOSITORY} or {IMAGE ID}
   ```

## Network Command:

## Storage Command:

`curl`

curl is a command-line tool in Linux used for transferring data to or from a server using various protocols such as HTTP, HTTPS, FTP, and more. It is widely used for interacting with web APIs, downloading files, and testing server endpoints.

```bash
docker exec hardcore_perlman curl localhost:80
```

## to override environment variables use this command in :

```bash
-e variable_name=value
```

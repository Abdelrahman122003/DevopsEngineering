## Registry in docker

A Docker registry is a centralized repository where Docker images are stored, managed, and distributed. It serves as a hub for Docker images, allowing users to share, deploy, and manage containers efficiently. Docker registries are essential for containerized application development and deployment, enabling easy access to pre-built images and fostering collaboration among teams.

- to create an registry

```bash
# The container runs in detached mode.
# Port 5000 on the host is mapped to port 5000 in the container, allowing access to the registry service.
# Port 8000 on the host is mapped to port 80 in the container, potentially for accessing another service running in the container.
# The container is named "registry" and will always restart if it stops.
docker run -d -p 5000:5000 -p 8000:80  --restart always --name registry registry:2
```

- to push image into registry

```bash
docker push localhost:port/image_name

# for example:
# localhost:5000/hello-world
```

- to pull image into registry

```bash
docker push localhost:port/image_name
```

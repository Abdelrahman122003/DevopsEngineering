## Task_1

**problem statement:**
make a apache httpd container, run it in the background, map host port 82 to the running container, view container logs after it runs.

```bash
# 1- run image httpd
docker run httpd
# 2- use`-d` to run it in the background, map host port 82 to the running container(80)
docker run -p -d --name myApacheHttpd  82:80 httpd
# 3- docker ps to see all containers that are running
```

![alt text](image.png)

```bash
# 4- When I talk to localhost:80
```

![alt text](image-1.png)

## Task_2

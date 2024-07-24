## How to create my own image

1.  Choose a Base Image: Select a base image from Docker Hub or other repositories. Common choices include ubuntu, alpine, node, python, etc.

2.  Create a Dockerfile: Create a file named Dockerfile in your project directory.

3.  Write Instructions: Add the necessary instructions to the Dockerfile. Basic instructions include:

        - FROM: Specifies the base image.
        - COPY or ADD: Copies files from your host to the container.
        - RUN: Executes commands inside the container (e.g., installing packages).
        - CMD or ENTRYPOINT: Defines the command to run when the container starts.
        - EXPOSE: Opens a port on the container.

4.  Build the Docker Image: Run the docker build command to create the image from the Dockerfile.

Here's an example Dockerfile for a simple Node.js application:

```bash
# Use the official Node.js image as the base image
FROM node:14
# Set the working directory inside the container
WORKDIR /app
# Copy package.json and package-lock.json to the container
COPY package\*.json ./
# Install dependencies
RUN npm install
# Copy the rest of the application code to the container
COPY . .
# Expose the application port
EXPOSE 3000
# Define the command to run the application
CMD ["node", "app.js"]
```

## what is a difference between CMD and ENTRYPOINT

### CMD:

- Specifies the default command to run when the container starts.
- Can be overridden by providing a different command when running the container (e.g., docker run <image> <command>).
- Used for providing defaults that can be overridden easily.

**Example for `CMD`**

```bash
# this lines in dockerFile
FROM ubuntu
CMD ["echo", "Hello, World!"]

# The command docker run my-cmd-image echo "Overridden CMD" runs a Docker container using the image my-cmd-image and overrides the default command specified by CMD in the Dockerfile.
docker run my-cmd-image echo "Overridden CMD"
# output: Overridden CMD
```

### ENTRYPOINT:

- Defines the executable that will always run when the container starts.
- Typically used to set a fixed command that should not be overridden.
- Any arguments passed in docker run will be appended to the ENTRYPOINT.

**Example for `ENTRYPOINT`**

```bash
# this lines in dockerFile
FROM ubuntu
ENTRYPOINT ["echo", "Hello, World!"]

# The command docker run my-cmd-image echo "Overridden CMD" runs a Docker container using the image my-cmd-image and overrides the default command specified by ENTRYPOINT in the Dockerfile.
docker run my-entrypoint-image "Overridden ENTRYPOINT"
# output: Hello, World! Overridden ENTRYPOINT
```

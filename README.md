# Docker_Multistage

<h1> Application </h1>
The calculator.go file contains the code for a simple calculator application written in Go. 
It performs basic arithmetic operations and is used as an example for building a Docker image using multistage builds.

<h1>Docker</h1>
Docker is an open-source platform that allows developers to automate the deployment, scaling, and management of applications in lightweight, portable containers.
Containers are isolated environments that package an application and its dependencies, ensuring consistent behavior across different environments.

<h1>Docker Multistage</h1>
Docker Multistage builds are a feature that allows developers to create more efficient and smaller Docker images. 
It involves using multiple stages in a Dockerfile, each with its own base image and set of commands. 
In each stage, you can build and compile your application, and then copy the necessary files from one stage to another. 
This allows you to discard unnecessary build dependencies and intermediate files, resulting in a smaller final image.

<h1>Distroless</h1>
Distroless is a set of base images provided by Google that are optimized for security and reduced attack surface. 
These base images are minimal and do not include any package manager or shell, reducing the risk of vulnerabilities and making the container lightweight. 
Using a distroless base image is a good practice for production deployments, as it only includes the necessary runtime and libraries for the application to run.

With multistage builds, the first stage (builder) compiles the Go binary, and the second stage uses a distroless base image to create a minimal image containing only the compiled binary. 
As a result, the final Docker image size is significantly smaller compared to the image without multistage builds.

Steps for running the file : https://hashnode.com/post/clkkuw5wn00140aljgt7v23pc

Please note that the actual image sizes may vary depending on the size of the Go application and its dependencies. 
Multistage builds are particularly beneficial for applications with complex build dependencies and large binary files, as they help reduce the final Docker image size.

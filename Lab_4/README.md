### Lab 3: Deploying the Algonquin Pet Store on Azure

1. #### Please find below the YouTube video link:

- https://youtu.be/ZF_TVTji1hU


2. #### Reflection Questions:

i. **What are the main differences between a Docker image and a Docker container?**
    Docker Image is a static, read-only template or blueprint used to create a running environment. It is a lightweight, standalone, executable software package that includes everything needed to run a piece of software, including the code, runtime, system tools, libraries, and settings. Images are built from a simple text file called a Dockerfile

ii. **Explain how Docker's layered architecture improves efficiency.**
    Docker images are composed of a series of layers, and this layered architecture promotes reusability and minimizes storage.
    - Structure: Each layer represents a set of filesystem differences or modifications—essentially a file system "diff". These layers are stacked on top of each other to form the final image.
    - Reusability: Layers are shared across containers. If multiple images are based on the same base image (like Ubuntu or Python), they all share those common, read-only base layers.
    - Efficiency: Sharing these layers saves significant disk space and speeds up deployments because only the new or changed layers need to be pulled when updating an image.

iii. **Why does each container get its own writable layer?**
    - Isolation and Immutability: The underlying image layers are read-only and immutable. This means the original image is never modified, ensuring consistency and integrity.
    - Run-time Changes: Changes made inside the running container (e.g., creating files, deleting files, or modifying configuration) happen only in this top writable layer.
    - Separate State: When multiple containers are created from the same image, each container gets its own separate writable layer while sharing the same read-only image layers. This isolation allows each running container to have its own unique state without affecting the others or the base image, which optimizes both storage and performance.

iv. **What are the benefits of using Docker Compose over running containers individually?**
    - Single-Command Management: Compose allows you to define multiple services (containers), networks, and volumes in a single docker-compose.yml file and manage them all together with a few simple commands (e.g., docker compose up).
    - Declarative Configuration: By defining the entire application stack in a YAML file, the setup is easily repeatable, portable, and allows for managing complex relationships and dependencies between services.
    - Application Orchestration: It is specifically designed to orchestrate multiple containers together, making it easy to stand up a complex application like a web service, a database, and a caching service simultaneously. This streamlines the development and testing of applications built using the microservices architectural style
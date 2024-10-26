# 🐋Learning-Docker

Learning Docker in order to become more proficient in Kubernetes to then confidently get Kubernetes deployment running for tutor.

Source: LinkedIn Learning— Docker for Developers 

**1. Build an Image:**

- **Command:** `docker build -t <image_name> .`
    - **Explanation:** Creates a Docker image from the Dockerfile in the current directory. The `t` flag names the image.

**2. List Images:**

- **Command:** `docker images`
    - **Explanation:** Lists all Docker images on your system.

**3. Remove an Image:**

- **Command:** `docker rmi <image_id>`
    - **Explanation:** Deletes a Docker image. You can use the first few characters of the image ID.

**4. Run a Container:**

- **Command:** `docker run -p <host_port>:<container_port> <image_name>`
    - **Explanation:** Starts a container efrom a specified image, mapping the container's port to the host's port.

**5. List Running Containers:**

- **Command:** `docker ps`
    - **Explanation:** Lists all currently running Docker containers.

**6. Stop a Container:**

- **Command:** `docker stop <container_id>`
    - **Explanation:** Stops a running Docker container.

**7. Force Stop a Container:**

- **Command:** `docker kill <container_id>`
    - **Explanation:** Forces a container to stop if it doesn't respond to the `stop` command.

**8. Push an Image to Docker Hub:**

- **Command:** `docker push <image_name>`
    - **Explanation:** Uploads a Docker image to Docker Hub.

**9. Pull an Image from Docker Hub:**

- **Command:** `docker pull <image_name>`
    - **Explanation:** Downloads a Docker image from Docker Hub.

> Essentially, dynamic data that goes back and forth between the frontend and backend exists in a volume.
> 

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/cab37465-12db-4026-ab8b-cf3b33e3dd1e/42e429a7-9918-4342-8fa8-d5c01859946e/image.png)

### Docker Compose

- `docker-compose build`: Builds all the images and instructions set in the Docker Compose file.
- `docker-compose up -d mongo`: Starts the MongoDB service.
- `docker-compose up -d app`: Starts the application service.
- `docker ps`: Lists all running containers.
- `docker logs [container_id]`: Displays the logs for a specific container.
- `docker-compose stop`: Stops all running containers.

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/cab37465-12db-4026-ab8b-cf3b33e3dd1e/77256c79-2627-4aba-b709-6e55ead398cb/image.png)

### Swarms

Functions:

- Initialize a swarm on the host computer.
- Add virtual machines as workers to the swarm.
- Verify the swarm setup and view the list of nodes.

Commands Used in the Video:

1. **Initialize Swarm Manager:**
bash
docker swarm init
This command initializes a swarm on the host machine, making it the manager.
2. **Add Worker to Swarm:**
bash
docker swarm join --token :
After SSH-ing into the worker machine, use this command to add it to the swarm. Replace `<token>`, `<manager-IP>`, and `<port>` with the appropriate values provided by the `docker swarm init` command.
3. **View Docker Info:**
bash
docker info
This command displays detailed information about the Docker installation, including the swarm status and node details.
4. **List Nodes in Swarm:**
bash
docker node ls
This command lists all nodes in the swarm, showing their roles (manager or worker) and status.

### Kubernetes:

Commands Used

1. **Create a Deployment:**
bash
kubectl create deployment nodeapplication --image=node
    - This command creates a new deployment named `nodeapplication` using the Node.js image from Docker Hub.
2. **Specify a Custom Image:**
bash
kubectl create deployment nodeapplication --image=<full_image_url>
    - This command allows you to specify a custom image URL if the image is not on Docker Hub.
3. **Check Deployments:**
bash
kubectl get deployments
    - This command lists all the deployments in your cluster, showing the status of each deployment.
    
    ### Creating Cluster:
    
    - **Create a Deployment:**
    bash
    kubectl create deployment nodeapplication --image=node
        - This command creates a new deployment named `nodeapplication` using the Node.js image from Docker Hub.
    - **Specify a Custom Image:**
    bash
    kubectl create deployment nodeapplication --image=<full_image_url>
        - This command allows you to specify a custom image URL if the image is not on Docker Hub.
    - **Check Deployments:**
    bash
    kubectl get deployments
        - This command lists all the deployments in your cluster, showing the status of each deployment.

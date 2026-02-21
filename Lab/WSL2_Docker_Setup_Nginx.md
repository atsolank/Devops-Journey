🧪 Labs Completed
✅ Lab 1 – WSL2 + Docker Setup & Nginx Deployment

Install the Ubuntu WSL and docker desktop on windows

Docker daemon permissions (docker.sock)
Issue Faced
Permission denied while accessing Docker daemon socket.
```bash
atul@Atul:~$ docker run hello-world docker: permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Head "http://%2Fvar%2Frun%2Fdocker.sock/_ping": dial unix /var/run/docker.sock: connect: permission denied Run 'docker run --help' for more information atul@Atul:~$
```

Resolution
# Added user to docker group:
sudo usermod -aG docker $USER

# Restarted WSL using:
wsl --shutdown



🌐 What is Nginx?
Nginx is:
Web server
Reverse proxy
Load balancer




# Commands Used – Lab 01

## Run Nginx Container
docker run -d -p 8080:80 --name mynginx nginx

## List Running Containers
docker ps

## Stop Container
docker stop mynginx

## Remove Container
docker rm mynginx


```bash
atul@Atul:/mnt/c/Users/lenovo$ docker run -d -p 8080:80 --name mynginx nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
46bf3a120c8e: Pull complete
f73400a233fd: Pull complete
0c8d55a45c0d: Pull complete
47cd406a84ef: Pull complete
bae5a1799a80: Pull complete
4f4efe02d542: Pull complete
7b6cb8ccac7b: Pull complete
Digest: sha256:341bf0f3ce6c5277d6002cf6e1fb0319fa4252add24ab6a0e262e0056d313208
Status: Downloaded newer image for nginx:latest
6768fb6c683d786c7120853c8fe798f5bcd17e9bc67db2c20d7c88fd09a10991
atul@Atul:/mnt/c/Users/lenovo$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                                     NAMES
6768fb6c683d   nginx     "/docker-entrypoint.…"   7 seconds ago   Up 5 seconds   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   mynginx
atul@Atul:/mnt/c/Users/lenovo$ cd
atul@Atul:~$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                                     NAMES
6768fb6c683d   nginx     "/docker-entrypoint.…"   7 minutes ago   Up 7 minutes   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   mynginx
atul@Atul:~$ docker stop mynginx
mynginx
atul@Atul:~$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
atul@Atul:~$ docker rm mynginx
mynginx
atul@Atul:~$ 
```
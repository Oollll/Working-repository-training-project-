# Docker 

## Requirements

# Tasks: 
#### 1. Start web on container from registry.

```
docker pull nginx:latest
docker run -d -p 8080:80 --name ngin_test nginx:latest 
```
#### 2. Writing your Dockerfile and building a docker image.
```
touch Dockerfile 
touch nginx.conf
docker build -t webapp .
```
- Run a docker container with limits. 
 ```
 docker run --memory 512m --cpu-quota 50000 webapp
 ```
#### 3. Attach the volume to the container and enter the container.
```
docker volume create webvolume

docker run -v webvolume:/myapp webapp

docker volume ls

docker exec -it сontainerid /bin/bash
```

#### 4. Run any docker compose file from any github.
```
docker-compose up
```
#### 5. Start a SQL database based on your own docker-compose with a web application from 1st ticket.

```
docker-compose up
-------------------
[+] Running 2/0
 ✔ Container sqlite_db   Created    
 ✔ Container django_app  Created      
Attaching to django_app, sqlite_db
sqlite_db exited with code 0
django_app  | Watching for file changes with StatReloader
django_app  | Performing system checks...
django_app  | 
django_app  | System check identified no issues (0 silenced).
django_app  | June 05, 2024 - 22:45:51
django_app  | Django version 5.0.6, using settings 'myproject.settings'
django_app  | Starting development server at http://0.0.0.0:8000/
django_app  | Quit the server with CONTROL-C.
django_app  | 

```




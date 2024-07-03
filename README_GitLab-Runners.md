# How to launch Git Lab runners

#### Step 1 (Create a docker compose file )

```
touch docker-compose.yml
```

### Step 2 (Creation of configuration directories and files)

```
sudo mkdir -p /srv/gitlab-runner/config/test1
sudo mkdir -p /srv/gitlab-runner/config/test2

cd test1 
touch config.toml

cd test2 
touch config.toml
```
- Make the appropriate configuration in the created files 


#### Step 3 (Running a container docker in the background )
```
docker-compose up -d
```
- Container skylining 
```
docker-compose up -d --scale web=3
```

#### Step 4 (Registering runners on GitLab)

```
docker exec -it your_container_name gitlab-runner register

```

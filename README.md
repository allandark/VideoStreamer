# Video Streamer

### Tech Stack





## Build


**Clone Repo**  
```
git clone <REPO_URL>
git submodule update --init --recursive
```

**Configure** 


**Build**  

**Ceate shared docker network between frontend and backend**
```
docker network create backend
```

**Build backend**
```
docker-compose -f VideoStreamerBackend/docker-compose.yaml build --no-cache
```
**Build frontend**
```
docker-compose -f VideoStreamerFrontend/docker-compose.yaml build --no-cache
```
**Run containers**
```
docker-compose up --build -d
```

```
docker network inspect backend
```

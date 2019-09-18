### Docker-CLI process for development.
### Execute the development docker files
### Create the docker container for the client (React app)

Inside the client folder execute

```
docker build -f Dockerfile.dev .
```
```
docker run <imageId>
```

### Create the docker container for the server (Node apps)

Inside the server folder execute

```
docker build -f Dockerfile.dev .
```
```
docker run <imageId>
```

This will show an error because the database is not running yet.
Postgres and Redis are not running yet.

### Create the docker container for the worker (Node apps)

Inside the worker folder execute

```
docker build -f Dockerfile.dev .
```
```
docker run <imageId>
```

### Docker-Compose process for development

In the root folder execute

```
docker-compose up
```

### Production Multiple-Container deployments flow

1. Push code to github
2. Travis automatically pulls repo
3. Travis builds a test image, tests code
4. Travis builds prod images
5. travis pushes built prod images to Docker Hub
6. Travis pushes project to AWS EB
7. EB pulls images from Docker Hub and deploys

### Travis flow

1. Specify docker as a dependency
2. Build test version of React project(use the development docker file because only this file has all the source code required for running the tests)
3. Run tests
4. Build prod versions of all projects
5. Push all to Docker Hub
6. Tell EB to update
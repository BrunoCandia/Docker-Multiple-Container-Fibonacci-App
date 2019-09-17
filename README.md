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
Posgres and Redis are not running yet.

### Create the docker container for the worker (Node apps)

Inside the worker folder execute

```
docker build -f Dockerfile.dev .
```
```
docker run <imageId>
```
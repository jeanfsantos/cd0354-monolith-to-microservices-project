# Microservices application

Set up each microservice to be run in its own Docker container

Once you refactor the Udagram application, it will have the following services running internally:

- Backend /user/ service - allows users to register and log into a web client.
- Backend /feed/ service - allows users to post photos, and process photos using image filtering.
- Frontend - It is a basic Ionic client web application that acts as an interface between the user and the backend services.
- Nginx as a reverse proxy server - for resolving multiple services running on the same port in separate containers. When different backend services are running on the same port, then a reverse proxy server directs client requests to the appropriate backend server and retrieves resources on behalf of the client.

# Use Docker compose to build and run multiple Docker containers

Once you have created the Dockerfile in each of the following services directories, you can use the docker-compose command to build and run multiple Docker containers at once.

- /project/udagram-api-feed/
- /project/udagram-api-feed/
- /project/udagram-frontend/
- /project/udagram-reverseproxy/

The docker-compose command uses a YAML file to configure your application’s services in one go. Meaning, you create and start all the services from your configuration file, with a single command. Otherwise, you will have to individually build containers one-by-one for each of your services.

### Remove unused and dangling images:

docker image prune --all

### Create images locally:

docker compose -f docker-compose-build.yaml build --parallel

### Run the container:

docker compose up

### to build & push images to dockerhub:

run jobs in Circle CI to push images to dockerhub

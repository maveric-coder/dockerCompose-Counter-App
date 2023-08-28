# dockerCompose-Counter-App

This Compose file defines two services: web and redis.

The web service uses an image that's built from the Dockerfile in the current directory. It then binds the container and the host machine to the exposed port, 8000. This example service uses the default port for the Flask web server, 5000.

The redis service uses a public Redisopen_in_new image pulled from the Docker Hub registry.

```bash
docker compose up
```
Compose pulls a Redis image, builds an image for your code, and starts the services you defined. In this case, the code is statically copied into the image at build time.
Open web browser and hit <PublicIP>:8000 to see the webpage. The count will increase each time we will refresh the page.

The above command will populate the shell screen with all the process execution and outputs, to avoid that we can use `-d` while bringing our docker compose up.
```bash
docker compose up
```
To stop the application use the command
```bash
docker compose down
```

We can bring everything down, removing the containers entirely, with the down command. Pass --volumes to also remove the data volume used by the Redis container:
```bash
docker compose down --volumes
```

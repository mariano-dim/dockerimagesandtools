# git-actions-runner

```sh
## start a runner on your server

$ docker run -d \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v /tmp:/tmp \
    -e GH_REPOSITORY=xxxxxxxxxxxx \
    -e GH_RUNNER_TOKEN=xxxxxxxxxxxxx \
    -e GH_RUNNER_LABELS=label1,label2 \
    marianodim/dockerimagesandtools:latest
```


```bash
docker build -f Dockerfile --rm -t marianodim/dockerimagesandtools:latest  -t marianodim/dockerimagesandtools:0.0.1 .
docker build -f Dockerfile --rm -t marianodim/dockerimagesandtools:latest  -t marianodim/dockerimagesandtools:0.0.1 .

docker build -f Dockerfile.node --rm -t marianodim/dockerimagesandtools:node    -t marianodim/dockerimagesandtools:node-0.0.1 .
docker build -f Dockerfile.golang --rm -t marianodim/dockerimagesandtools:golang  -t marianodim/dockerimagesandtools:golang-0.0.1 .
docker build -f Dockerfile.python --rm -t marianodim/dockerimagesandtools:python  -t marianodim/dockerimagesandtools:python-0.0.1 .
docker build -f Dockerfile.java --rm -t marianodim/dockerimagesandtools:java    -t marianodim/dockerimagesandtools:java-0.0.1 .
docker build -f Dockerfile.php --rm -t marianodim/dockerimagesandtools:php     -t marianodim/dockerimagesandtools:php-0.0.1 .

docker push marianodim/dockerimagesandtools:latest
docker push marianodim/dockerimagesandtools:0.0.1

docker push marianodim/dockerimagesandtools:node
docker push marianodim/dockerimagesandtools:node-0.0.1

docker push marianodim/dockerimagesandtools:golang
docker push marianodim/dockerimagesandtools:golang-0.0.1

docker push marianodim/dockerimagesandtools:python
docker push marianodim/dockerimagesandtools:python-0.0.1

docker push marianodim/dockerimagesandtools:java
docker push marianodim/dockerimagesandtools:java-0.0.1

docker push marianodim/dockerimagesandtools:php
docker push marianodim/dockerimagesandtools:php-0.0.1
```


## Para tener en cuenta

Para que funcione el login a Docker Hub dentro de docker (si es que no funciona), se debe dar permisos al socket de docker
Como este socket esta compartido como volumen, se puede modificar desde dentro del container

```
sudo chmod 666 /var/run/docker.sock
```

Solucion propuesta desde

https://stackoverflow.com/questions/48957195/how-to-fix-docker-got-permission-denied-issue
https://docs.docker.com/engine/install/linux-postinstall/

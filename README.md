# Voting App 

Voting app

# Scripts

### Launch Docker

```shell
docker compose up
```

App running at <http://localhost:5000>, and the results will be at <http://localhost:5001>.

```shell
docker swarm init
```

Deploy

```shell
docker stack deploy --compose-file docker-stack.yml vote
```

## Run the app in Kubernetes

```shell
kubectl create -f k8s-specifications/
```

Remove :

```shell
kubectl delete -f k8s-specifications/
```

![Architecture diagram](architecture.png)

* A front-end web app in [Python](/vote) which lets you vote between two options
* A [Redis](https://hub.docker.com/_/redis/) which collects new votes
* A [.NET](/worker/) worker which consumes votes and stores them in…
* A [Postgres](https://hub.docker.com/_/postgres/) database backed by a Docker volume
* A [Node.js](/result) web app which shows the results of the voting in real time

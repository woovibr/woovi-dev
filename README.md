# Woovi-Dev

A repository with some files, configurations and scripts to create the best Woovi DX for Woovers

## Docker Compose

Start coping the `.env.local` to `.env`

```bash
cp .env.local .env
```

these environments are used to customize docker compose services

We only run services using docker compose, we don't run our backend inside docker

To start all services, run:

```bash
docker compose up
```

To get a list of all docker services

```bash
docker compose config | yq '.services[]|key'
```

To run only a few of these services

```bash
docker compose up mongo1 mongo2
```

To run docker compose in detached mode

```jsx
docker compose up -d
```

## List of services inside our docker compose file

- mongo1 - for mongodb minimal replicaset
- mongo2 - for mongodb minimal replicaset
- mongo-hidden - to test hidden node in replicaset
- mosquitto - mqtt server
- redis - for cache and bull jbos
- setup - to setup elastic search - generate certificates
- es - elastic search
- filebeat - es file beat
- kibana - elastic kibana
- fleet-server - es fleet-server
- logstash - es logstash
- metricbeat - es metric beat
# chainlog-ui

UI and API for GSU Protocol’s chainlog contract

- [chainlog.gsuprotocol.io](https://chainlog.gsuprotocol.io)
- [chainlog.gsuprotocol.io/api.html](https://chainlog.gsuprotocol.io/api.html)
- chainlog.gsuprotocol.io/checksum/\<address\>

## Test locally with Docker

1. Make sure that older Docker images are removed, and containers are stopped, if you want to test new code:

```
docker rmi chainlog-ui
docker rmi chainlog-logger
docker rmi chainlog-checksum
```

2. Build the Docker images and start the 3 containers:

```
docker-compose up -d
```

3. Look at the logs:

```
docker logs -f chainlog-ui
docker logs -f chainlog-logger
docker logs -f chainlog-checksum
```

4. Stop the containers:

```
docker-compose down
```

**Note:** nginx.conf.template is being customized with the path `/checksum` and copied into the `chainlog-ui` container, for sending traffic to the container running the `checksum.py` script.

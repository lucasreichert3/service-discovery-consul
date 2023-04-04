# Initialize docker-compose

```shell
docker-compose up -d
```

# Command to run Consul Server Agent

```shell
consul agent -server -bootstrap-expect=3 -node=consulserver01 -bind=172.21.0.3 -data-dir=/var/lib/consul -config-dir=/etc/consul.d
```

- `-bootstrap-expect=3`: Notify Consul that will start 3 servers
- `-data-dir=/var/lib/consul`: Directory to save Consul files
- `-config-dir=/etc/consul.d`: Directory that contains consul config file

## When you have a config file, just run:

```shell
consul agent -config-dir=/etc/consul.d
```

# Command to join Servers:

```shell
consul join <ip>
```

# Command to run an agent:

```shell
consul agent -bind=172.22.0.5 -data-dir=/var/lib/consul -config-dir=/etc/consul.d -retry-join=<ip_server_consul>
```

`-retry-join`: When starts the Client try to join the server.

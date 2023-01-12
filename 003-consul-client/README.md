
## Docker



## Docker-Compose

[Instalação](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-pt)

sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose --version

## Consul

```
docker-compose up -d
```

```
docker-compose ps
```

## Consul Server

### ConsulServer 01

```
docker exec -it consul-01 sh
```

```
consul members
```

```
mkdir /etc/consul.d
mkdir /var/lib/consul
```

```
ifconfig
```

```
consul agent -server -bootstrap-expect=3 -node=consulserver01 -bind=172.22.0.4 -data-dir=/var/lib/consul -config-dir=/etc/consul.d
```

```
consul members
```

### ConsulServer 02

```
docker exec -it consul-02 sh
```

```
consul members
```

```
mkdir /etc/consul.d
mkdir /var/lib/consul
```

```
ifconfig
```

```
consul agent -server -bootstrap-expect=3 -node=consulserver02 -bind=172.22.0.3 -data-dir=/var/lib/consul -config-dir=/etc/consul.d
```

```
consul join 172.22.0.4
``` 

```
consul members
```

### ConsulServer 03

```
docker exec -it consul-03 sh
```

```
consul members
```

```
mkdir /etc/consul.d
mkdir /var/lib/consul
```

```
ifconfig
```

```
consul agent -server -bootstrap-expect=3 -node=consulserver03 -bind=172.22.0.2 -data-dir=/var/lib/consul -config-dir=/etc/consul.d
```

```
consul join 172.22.0.3
``` 

```
consul members
```

## Consul Client

## ConsulClient01

```
docker exec -it consulclient01 sh
```

```
consul members
```

```
mkdir /etc/consul.d
mkdir /var/lib/consul
```

```
ifconfig
```

```
consul agent -bind=172... -data-dir=/var/lib/consul config-dir=/etc/consul.d
```

```
consul join
```

```
consul members
``` 
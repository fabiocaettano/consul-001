# consul-001

Aula do Curso FullCycle sobre comunicação entre sistemas.

``` bash
$ docker-compose up -d
$ docker exec -it consul01 sh
```

```
# consul agent -dev
```

```
# consul members
```

```
# apk -U add bind-tools
```

```
# dig @localhost -p 8600 consul01.node.consul
```

```
# dig @localhost -p 8600 consul01.node.consul +short
```

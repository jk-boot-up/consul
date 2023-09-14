# consul commands

### see the list of containers
    docker ps -a
    
    CONTAINER ID   IMAGE              COMMAND                  CREATED             STATUS             PORTS                                                                                    NAMES
    26de47c6b7e1   hashicorp/consul   "docker-entrypoint.s…"   19 minutes ago      Up 19 minutes      8300-8302/tcp, 8500/tcp, 8301-8302/udp, 8600/tcp, 8600/udp                               consul-client-container-1
    31afc90ee59a   hashicorp/consul   "docker-entrypoint.s…"   About an hour ago   Up About an hour   8300-8302/tcp, 8600/tcp, 8301-8302/udp, 0.0.0.0:8500->8500/tcp, 0.0.0.0:8600->8600/udp   consul-server-container-1


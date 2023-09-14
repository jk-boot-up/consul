# docker commands

## samples for consul

### pull docker image
    
    docker pull hashicorp/consul;

### check the presence of docker image
    
    docker images -f "reference=hashicorp/consul"
    # -f or –filter: It filters the images as per conditions specified

### run consul server
    
    docker run -d -p 8500:8500 -p 8600:8600/udp --name=consul-server-container-1 hashicorp/consul agent \
    -server -ui -node=consul-server-1 -bootstrap-expect=1 -client=0.0.0.0

### check the consul members and  Discover the server IP address
    
    docker exec consul-server-container-1 consul members

    Node             Address          Status  Type    Build   Protocol  DC   Partition  Segment
    consul-server-1  172.17.0.2:8301  alive   server  1.16.1  2         dc1  default    <all>

### Configure and run a Consul client

    docker run --name=consul-client-container-1 hashicorp/consul agent -node=consul-client-1 -retry-join=172.17.0.2 

### see the running containers
    docker ps -a

    CONTAINER ID   IMAGE              COMMAND                  CREATED             STATUS             PORTS                                                                                    NAMES
    26de47c6b7e1   hashicorp/consul   "docker-entrypoint.s…"   19 minutes ago      Up 19 minutes      8300-8302/tcp, 8500/tcp, 8301-8302/udp, 8600/tcp, 8600/udp                               consul-client-container-1
    31afc90ee59a   hashicorp/consul   "docker-entrypoint.s…"   About an hour ago   Up About an hour   8300-8302/tcp, 8600/tcp, 8301-8302/udp, 0.0.0.0:8500->8500/tcp, 0.0.0.0:8600->8600/udp   consul-server-container-1

### See the consul members - both client and server

    docker exec consul-server-container-1 consul members

    Node             Address          Status  Type    Build   Protocol  DC   Partition  Segment
    consul-server-1  172.17.0.2:8301  alive   server  1.16.1  2         dc1  default    <all>
    consul-client-1  172.17.0.3:8301  alive   client  1.16.1  2         dc1  default    <default>





    



    





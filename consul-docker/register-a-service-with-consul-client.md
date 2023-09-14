# Register a service with consul client

### pull a sample service docker image

    docker pull hashicorp/counting-service:0.0.2
### Run the container with port forwarding so that you can access it from your web browser by visiting http://localhost:9001.

    docker run -d -p 9001:9002 --name=counting-service-container-1 hashicorp/counting-service:0.0.2
    
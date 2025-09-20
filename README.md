# Using docker

If you don't have RabbitMQ installed, you can run it in a Docker container:

```sh
docker run -it --rm --name rabbitmq -p 5552:5552 -p 15672:15672 -p 5672:5672  \
    -e RABBITMQ_SERVER_ADDITIONAL_ERL_ARGS='-rabbitmq_stream advertised_host localhost' \
    rabbitmq:4-management
```

wait for the server to start and then enable the stream and stream management plugins:

```sh
docker exec rabbitmq rabbitmq-plugins enable rabbitmq_stream rabbitmq_stream_management
```

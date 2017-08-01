# jaeger-nginx
Reverse proxy for Jaeger

# Deploy
Create .htpasswd

```sh
docker build -t reverseproxy .
```

Create ECS repository for jaeger and reverseproxy, then replace the `image` fields in docker-compose.yml

```sh
ecs-cli up --keypair <keypair> --capability-iam --size 1 --port 8080 --instance-type t2.micro --force
ecs-cli compose -file docker-compose.yml service up
```

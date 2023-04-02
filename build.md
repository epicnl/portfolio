
## build, push and deploy image
tag=latest
service=cloudconsultant
registry=registry.digitalocean.com/agilenav
docker build -f Dockerfile -t $service .

docker tag $service $registry/$service:$tag
docker push $registry/$service:$tag




docker run -d -p 80:80 $service

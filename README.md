# docker-nginx-static

Docker container for serving static content using nginx


## Executing

    docker run --name "my-nginx" -P -v $(pwd)/example-content:/var/www jojomi/nginx-static

Find your container:

    docker ps | grep "my-nginx"
    CONTAINER ID        IMAGE                           COMMAND                CREATED             STATUS              PORTS                   NAMES
    ba00b5c238fc        jojomi/nginx-static:latest   "nginx -D -f /etc   1 second ago        Up 1 second         0.0.0.0:49153->80/tcp   my-nginx

Check if it works:

    curl localhost:49153
    This is your content.


## Building The Image Yourself (optional)

    docker build -t jojomi/nginx-static .

The image is conveniently small at **below 7 MB** thanks to [alpine](http://gliderlabs.viewdocs.io/docker-alpine):

    docker images | grep nginx
    jojomi/nginx-static   latest              b2e7a8364baa        1 second ago      6.498 MB

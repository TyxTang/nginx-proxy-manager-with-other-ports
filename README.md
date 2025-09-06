# nginx-proxy-manager-with-other-ports

build NginxProxyManager with other default http and https ports,

and the default port here is:
- 8181 for the admin web
- 8080 for the public http 
- 4443 for the public https

you can change the default ports in these ways:
- change the ports when you build the image(see the example below)
- change the `.env` and use docker compose to start the demo quickly `docker-compose up -d`

# usage of this image

## just use the image

if you use the same ports with me, you can import the image from docker hub:
```
docker pull popozhu/nginx-proxy-manager-with-other-ports:2
```

## build the image with different ports by yourself

change the ports when you build the image:

```
docker build \
    --build-arg DEFAULT_PORT_PRODUCTTION=8181 \
    --build-arg DEFAULT_PORT_HTTP=8080 \
    --build-arg DEFAULT_PORT_HTTPS=4443 \
    -t nginx-proxy-manager-with-other-ports:2 \
    .
```
you can also checkout the `Dockerfile` here for more different info


## or start the container in your local

checkout the `.env` to modify the ports and data dir, and then:
```
git clone
docker-compose up -d
```

access the http://localhost:8181 with default account: 
```
Email:    admin@example.com
Password: changeme
```

# usage of nginx proxy manager 

the same with https://github.com/NginxProxyManager/nginx-proxy-manager, except the ports.
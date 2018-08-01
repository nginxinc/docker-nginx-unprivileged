# NGINX Unprivileged Docker Image

This Dockerfile creates an NGINX Docker image that runs NGINX as a non root, unprivileged user. Notable differences with respect to the official NGINX Docker image include:
* The default NGINX listen port is now `8080` instead of `80`
* The default NGINX user directive in `/etc/nginx/nginx.conf` has been removed
* The default NGINX PID has been moved from `/var/run/nginx.pid` to `/var/cache/nginx/nginx.pid`
* Change `*_temp_path` variables to `/var/cache/nginx/*`

Dockerhub images can be found at https://hub.docker.com/r/nginxinc/nginx-unprivileged

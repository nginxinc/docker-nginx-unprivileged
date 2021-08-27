# NGINX Unprivileged Docker Image

This Dockerfile creates an NGINX Docker image that runs NGINX as a non root, unprivileged user. Notable differences with respect to the official NGINX Docker image include:
*   The default NGINX listen port is now `8080` instead of `80`.
*   The default NGINX user directive in `/etc/nginx/nginx.conf` has been removed.
*   The default NGINX PID has been moved from `/var/run/nginx.pid` to `/tmp/nginx.pid`.
*   Change `*_temp_path` variables to `/tmp/*`.

Docker Hub images are built for the `amd64`, `arm32v5` (for Debian), `arm32v6` (for Alpine), `arm32v7`, `arm64v8`, `i386`, `mips64le` (for Debian), `ppc64le` and `s390x` architectures and can be found at <https://hub.docker.com/r/nginxinc/nginx-unprivileged>.

Warning: The latest mainline release, `1.21.1`, does not have an Alpine `i386` arch image due to an upstream `mercurial` bug.

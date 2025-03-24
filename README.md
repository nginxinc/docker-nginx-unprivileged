[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/nginx/template-repository/badge)](https://securityscorecards.dev/viewer/?uri=github.com/nginx/template-repository)
[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![Community Support](https://badgen.net/badge/support/community/cyan?icon=awesome)](/SUPPORT.md)
[![Community Forum](https://img.shields.io/badge/community-forum-009639?logo=discourse&link=https%3A%2F%2Fcommunity.nginx.org)](https://community.nginx.org)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/license/apache-2-0)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](/CODE_OF_CONDUCT.md)

# NGINX Unprivileged Docker Image

This repo contains a series of Dockerfiles to create an NGINX Docker image that runs NGINX as a non root, unprivileged user. Notable differences with respect to the official [NGINX Docker](https://github.com/nginxinc/docker-nginx) image include:

- The default NGINX listen port is now `8080` instead of `80` (this is no longer necessary as of Docker `20.03` but it's still required in other container runtimes)
- The default NGINX user directive in `/etc/nginx/nginx.conf` has been removed
- The default NGINX PID has been moved from `/var/run/nginx.pid` to `/tmp/nginx.pid`
- Change `*_temp_path` variables to `/tmp/*`

New images are built and pushed to on a weekly basis (every Monday night).

Check out the [docs](https://hub.docker.com/_/nginx) for the upstream Docker NGINX image for a detailed explanation on how to use this image.

## Supported Image Registries and Platforms

### Image Registries

You can find pre-built images in each of the following registries:

- Amazon ECR - <https://gallery.ecr.aws/nginx/nginx-unprivileged>
- Docker Hub - <https://hub.docker.com/r/nginxinc/nginx-unprivileged>
- GitHub Container Registry - <https://github.com/nginxinc/docker-nginx-unprivileged/pkgs/container/nginx-unprivileged>
- Quay - <https://quay.io/repository/nginx/nginx-unprivileged>

### Architectures

Most images are built for the `amd64`, `arm32v5` (for Debian), `arm32v6` (for Alpine), `arm32v7`, `arm64v8`, `i386`, `mips64le` (for Debian), `ppc64le` and `s390x` architectures.

## Troubleshooting Tips

- If you wish to use a different user ID and/or group ID when running the Docker Unprivileged image, rebuild the image using the following Docker build arguments:

  ```bash
  docker build --build-arg UID=<UID> --build-arg GID=<GID> -t nginx-unprivileged .
  ```

- If you override the default `nginx.conf` file you may encounter various types of error messages:
  - To fix `nginx: [emerg] open() "/var/run/nginx.pid" failed (13: Permission denied)`, you have to specify a valid `pid` location by adding the line `pid /tmp/nginx.pid;` at the top level of your config.
  - To fix `nginx: [emerg] mkdir() "/var/cache/nginx/client_temp" failed (30: Read-only file system)`, you have to specify a valid location for the various NGINX temporary paths by adding these lines within the `http` context:

    ```nginx
    http {
        client_body_temp_path /tmp/client_temp;
        proxy_temp_path       /tmp/proxy_temp_path;
        fastcgi_temp_path     /tmp/fastcgi_temp;
        uwsgi_temp_path       /tmp/uwsgi_temp;
        scgi_temp_path        /tmp/scgi_temp;
    ...
    }
    ```

## On Reporting Issues

Whilst issues and PRs are welcome, please do note that:

1. Issues related to security vulnerabilities will be promptly closed unless they are accompanied by a solid reasoning as to why the vulnerability poses a real security threat to this image. Check out the [`SECURITY`](https://github.com/nginxinc/docker-nginx-unprivileged/blob/main/SECURITY.md) doc for more details.
2. These images are unprivileged ports of the upstream [Docker NGINX](https://github.com/nginxinc/docker-nginx) images. Any changes that do not specifically involve the changes made to run NGINX on an unprivileged system should be reported in the [Docker NGINX](https://github.com/nginxinc/docker-nginx) upstream repo. They will not get addressed here.
3. Following from 2., base images (e.g. Alpine x.x or Debian x) in the [Docker NGINX](https://github.com/nginxinc/docker-nginx) upstream repo get updated when a new version of NGINX is released, never within the same release version. Similarly, new NGINX releases usually make their way to the [Docker NGINX](https://github.com/nginxinc/docker-nginx) image a couple days after their standard release. Please refrain from opening an issue or PR here if the upstream repo hasn't been updated -- it will be closed.

## Contributing

Please see the [contributing guide](/CONTRIBUTING.md) for guidelines on how to best contribute to this project.

## License

[Apache License, Version 2.0](/LICENSE)

&copy; [F5, Inc.](https://www.f5.com/) 2018-2025

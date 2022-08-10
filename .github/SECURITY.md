# Security Policy

## Reporting a Vulnerability

If you find a security vulnerability that directly affects the Docker NGINX Unprivileged image we encourage you open an issue detailing the security vulnerability. **Do note that only vulnerabilities related to direct NGINX library dependencies will be considered. Other security vulnerabilities should be addressed by the weekly Monday night build and as such will be promptly closed.** For reference, the direct NGINX library dependencies are:

* For Debian:
  * `libc6`
  * `libcrypt1`
  * `libpcre2`
  * `libssl`
  * `zlib1g`

* For Alpine Linux:
  * `libc`
  * `libcrypto`
  * `libpcre2`
  * `libssl`
  * `libz`

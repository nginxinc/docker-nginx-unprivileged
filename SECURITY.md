# Security Policy

## Latest Versions

We advise users to run or update to the most recent release of the NGINX Docker Unprivileged image. Older versions of the NGINX Docker Unprivileged image may not have all enhancements and/or bug fixes applied to them.

## Reporting a Vulnerability

### Docker NGINX Unprivileged Image

If you find a security vulnerability that directly affects a direct NGINX library dependency we encourage you open an issue detailing the security vulnerability.

For reference, the direct NGINX library dependencies are:

- For Debian:
  - `libc6`
  - `libcrypt1`
  - `libpcre2`
  - `libssl`
  - `zlib1g`

- For Alpine Linux:
  - `libc`
  - `libcrypto`
  - `libpcre2`
  - `libssl`
  - `libz`

***Note: Only vulnerabilities related to direct NGINX library dependencies will be considered. Other security vulnerabilities should be addressed by the weekly Monday night build and as such will be promptly closed.***

### Codebase

If you find a security vulnerability that affects the codebase, we encourage you to report it to the F5 Security Incident Response Team (F5 SIRT):

- If you’re an F5 customer with an active support contract, please contact [F5 Technical Support](https://www.f5.com/services/support).
- If you aren’t an F5 customer, please report any potential or current instances of security vulnerabilities with any F5 product to the F5 Security Incident Response Team at <F5SIRT@f5.com>.

For more information visit [https://www.f5.com/services/support/report-a-vulnerability](https://www.f5.com/services/support/report-a-vulnerability).

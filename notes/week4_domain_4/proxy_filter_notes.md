# Proxy and Content Filter Notes

## Anchor
A proxy server intermediates client requests to external services and can enforce policies, cache responses, and log traffic. Forward proxies handle outbound requests from clients to the internet. Reverse proxies sit in front of servers and handle incoming requests, offering load balancing, TLS termination, and request filtering. Transparent proxies intercept traffic without client configuration and are commonly used in corporate networks.

Common tools include Squid for HTTP proxying, NGINX or HAProxy for reverse proxy and load balancing, and cloud services that offer web filtering. An example deployment is a forward proxy that applies URL filtering and malware scanning for employee web traffic while a reverse proxy terminates TLS for public web services and forwards sanitized requests to application servers.

## Reverse
Proxies that perform deep inspection can introduce latency and raise privacy concerns when decrypting TLS traffic. Misconfigured proxies can leak headers or expose internal details. Transparent proxies can break applications that expect direct connections or rely on client IP addresses. Proxy policies must balance security, privacy, and performance. When implementing TLS inspection, protect the proxy platform, maintain certificate hygiene, and communicate changes to end users and stakeholders.

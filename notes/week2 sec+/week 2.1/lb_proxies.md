- **L4 Load Balancer (Transport):**
  - Operates on **TCP/UDP** (OSI L4).
  - Routes by **IP + port** (no payload inspection).
  - Use when needing high throughput, low latency, and TLS pass-through.
  - Example: AWS **NLB**, HAProxy in TCP mode.

- **L7 Load Balancer (Application):**
  - Operates on **HTTP/HTTPS** (OSI L7).
  - Routes by **URL path, Host header, cookies, query**.
  - Supports rewrites, WAF, auth, content-based routing.
  - Example: AWS **ALB**, NGINX (HTTP mode).

- **Forward Proxy:**
  - Placed **near clients** (outbound control).
  - Hides internal clients, enforces outbound policies (filtering, DLP).
  - Example: Squid, corporate web proxies, Zscaler.

- **Reverse Proxy:**
  - Placed **near servers** (inbound control).
  - Hides backend topology; performs SSL termination, caching, WAFing.
  - Example: NGINX, CloudFront + ALB, AWS CloudFront (edge).

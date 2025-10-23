# Proxy and Content Filter Notes

A proxy sits between users and the internet. It checks traffic, filters it, and logs it.
A forward proxy handles client requests going out to the internet.
A reverse proxy protects servers by handling incoming requests.
A transparent proxy intercepts traffic automatically without setup on each device.

The proxy is like a customs officer checking what enters or leaves a country.

Flow:
1. A client sends a web request.
2. The proxy receives it and checks the policy.
3. It decides to allow, block, or modify the request.
4. The decision is logged for review later.

Proxies give control and visibility but can add delay or privacy issues if overused.

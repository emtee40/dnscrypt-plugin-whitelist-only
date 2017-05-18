Whitelist plugin for DNSCrypt
=============================

This is a [dnscrypt-proxy](https://github.com/jedisct1/dnscrypt-proxy/wiki)
plugin to return a `REFUSED` response code to DNS queries not in a set of
whitelisted zones and not resolving to a given set of whiteslisted IPs.

Dependencies
------------

- cmake
- ldns

Installation
------------

```bash
$ mkdir build && cd build && cmake .. && make
```

The resulting plugin can be copied anywhere on the system.

Example usage
-------------

In the dnscrypt-proxy configuration file:

```
Plugin /path/to/libwhitelist.so,--domains=/etc/whitelisted-domains.txt,--ips=/etc/whitelisted-ips.txt
```

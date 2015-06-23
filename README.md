# awsome-haproxy
A friend of mine created this repo https://github.com/phanan/htaccess. How Haproxy achieve the same things? Let's see


## Table of Contents
- [Security](#security)
  - [Prevent Framing the Site](#prevent-framing-the-site)

## Security
### Prevent Framing the Site
This prevents the website to be framed (i.e. put into an `iframe` tag).
To configure HAProxy to send the X-Frame-Options header, add this to your frontend, listen, or backend configuration.
See others (https://sathian.wordpress.com/2015/04/30/x-frame-options/)
``` haproxy.cfg
rspadd X-Frame-Options:\ SAMEORIGIN
```
  



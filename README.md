# awsome-haproxy
A friend of mine created this repo https://github.com/phanan/htaccess. How Haproxy achieve the same things? Let's see


## Table of Contents
- [Rewrite and Redirection](#rewrite-and-redirection)
    - [Force www](#force-www)
    - [Force non-www](#force-non-www)
- [Security](#security)
  - [Prevent Framing the Site](#prevent-framing-the-site)


### Force www
``` www.cfg
	redirect prefix http://www.haproxy.local code 301 if { hdr(host) -i haproxy.local }    
```
### Force non-www
It's [still](http://www.sitepoint.com/domain-www-or-no-www/) [open](https://devcenter.heroku.com/articles/apex-domains) [for](http://yes-www.org/) [debate](http://no-www.org/) whether www or non-www is the way to go, so if you happen to be a fan of bare domains, here you go:
``` non-www.cfg
	redirect prefix http://haproxy.local code 301 if { hdr(host) -i www.haproxy.local }    

```
## Security
### Prevent Framing the Site
This prevents the website to be framed (i.e. put into an `iframe` tag).
To configure HAProxy to send the X-Frame-Options header, add this to your frontend, listen, or backend configuration.
See others (https://sathian.wordpress.com/2015/04/30/x-frame-options/)
``` haproxy.cfg
rspadd X-Frame-Options:\ SAMEORIGIN
```
  



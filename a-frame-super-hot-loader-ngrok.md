# Using hot reload over ngrok/HTTPS

1. Run webpack-dev-server with port 443
2. Run ngrok 


- No local TLS certs needed
- webpack does not have to run in HTTPS mode

## Investigation

### Hot reload does not work with HTTPS

When using hot reload with HTTPS via ngrok tunnelling to local webpack-dev-server, getting the following errors:

```
sockjs.js:1609          GET https://a277-77-139-218-14.ngrok.io:80/sockjs-node/info?t=1645640508106 net::ERR_SSL_PROTOCOL_ERROR
```

`--disable-host-check` did not help

May require to use `--https` option to WP and/or add local SSL certificate.

https://www.binarycarpenter.com/create-ssl-site-at-your-localhost-with-mamp-nodejs-in-5-minutes/
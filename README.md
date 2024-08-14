# mitm-proxy

## Requirements

1. [Docker Desktop](https://www.docker.com/products/docker-desktop/)
2. Web browser
3. curl

## Getting started

1. Run the mitmproxy container

```bash
docker run --name mitmproxy --rm -d -p 8888:8080 -p 127.0.0.1:8889:8081 -v ./certificates:/home/mitmproxy/.mitmproxy  mitmproxy/mitmproxy:10 mitmweb --web-host 0.0.0.0 --web-port 8081
```

2. Go to the mitmproxy dashboard in the URL `http://localhost:8889`
3. Execute `curl --cacert certificates/mitmproxy-ca-cert.pem --proxy localhost:8888 -X GET https://mitm.it`

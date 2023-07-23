# nginx-grpc-health-sample
Sample repository of HTTP/2 healthcheck endpoint for gRPC server.

## Getting started

```bash
# create a self-signed certificate
openssl genrsa -out envoy-self-cert.key 2048
openssl req -new -key envoy-self-cert.key -out envoy-self-cert.csr
openssl x509 -req -days 3650 -in envoy-self-cert.csr -signkey envoy-self-cert.key -out envoy-self-cert.crt

docker compose up
while true; curl --head -k https://localhost:8080/healthz; sleep 1; end;
```

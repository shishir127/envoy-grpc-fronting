Sets up a fronting envoy for [a grpc service](https://github.com/shishir127/golang-grpc-server). Copied a lot of code from the [envoy fronting example](https://github.com/envoyproxy/envoy/tree/master/examples/front-proxy).

### To generate a TLS cert for testing
* `openssl genrsa 2048 > private.pem` generates a private key.
* `openssl req -x509 -days 1000 -new -key private.pem -out public.pem` generate public cert.
More at (stack overflow)[https://stackoverflow.com/questions/14267010/how-to-create-self-signed-ssl-certificate-for-test-purposes].

### Build
* `docker-compose build`

### Run
* `docker-compose up` runs it in the foreground.
* `docker-compose up -d` runs it in the background & `docker-compose stop` stops services.

### Testing the setup
* Clone and build https://github.com/shishir127/golang-grpc-client.
* Run `PORT=443 TOKEN=test grpc-client`

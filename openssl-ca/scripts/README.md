# PKI and HTTPS Scripts/Commands
This folder contains all the command used to Configure PKI and HTTPS server
## Intermediate CA
openssl x509 -req \
-in intermediate-ca.csr \
-CA root-ca.crt \
-CAkey root-ca.key \
-CAcreateserial \
-out intermediate-ca.crt \
-days 1825 \
-sha256

### HTTPS Server Certificate
openssl req -new -newkey rsa:2048 -nodes \
-keyout https-server.key \
-out https-server.csr \
-subj "/C=AU/O=CQU/CN=HTTPS-Server"

openssl x509 -req \
-in https-server.csr \
-CA intermediate-ca.crt \
-CAkey intermediate-ca.key \
-CAcreateserial \
-out https-server.crt \
-days 825 \
-sha256

#### Certification Verification
openssl verify \
-CAfile root-ca.crt \
-untrusted intermediate-ca.crt \
https-server.crt

##### HTTPS Testing
nginx -t

ss -lntp | grep :443

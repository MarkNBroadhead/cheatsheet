# Certs

## SSL
Fetch SSL certificate information from server 

* `nmap -p 443 --script ssl-cert <url>/32`
or
* `openssl s_client -connect <URL HERE>:443`
* Copy and paste the text starting with `-----BEGIN CERTIFICATE-----` and ending in `-----END CERTIFICATE-----`, inclusive, into a file xyz.pem
* `openssl x509 -in xyz.pem -text`

## Java JKS
Open jks truststore
`keytool -list -v -keystore <certname.jks>`

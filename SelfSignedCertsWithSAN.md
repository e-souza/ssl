# Self Signed Certs With SAN
> Use at your own risk:

## Creating the key
```sh
openssl genrsa -out domain.key 2048
```

## Generating the CSR
```sh
openssl req -new -nodes -sha256 -keyout domain.key -out domain.csr -subj "/CN=your_domain" -addext "subjectAltName = IP:your_ip_address"
```

## Generating and Signing the Certificate
```sh
openssl x509 -signkey domain.key -in domain.csr -req -days 365 -out domain.crt
```
## Verify the Certificate
```sh
openssl x509 -noout -text -in domain.crt
```

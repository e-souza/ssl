# Build a CA and a SAN Certificate with Easy-RSA
```
easyrsa init-pki
easyrsa --batch build-ca nopass
easyrsa --batch --req-cn=domain.com gen-req domain.com nopass
easyrsa --batch --subject-alt-name='DNS:domain.com,DNS:www.domain.com'  \
    sign-req server domain.com
```
or
```
./easyrsa --subject-alt-name="DNS:www.domain.com,DNS:secure.domain.com" build-server-full  alttest nopass
```

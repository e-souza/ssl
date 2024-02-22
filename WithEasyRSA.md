# Build a CA and a SAN Certificate with Easy-RSA
```
easyrsa init-pki
easyrsa --batch build-ca nopass
easyrsa --batch --req-cn=example.org gen-req example.org nopass
easyrsa --batch --subject-alt-name='DNS:example.org,DNS:www.example.org'  \
    sign-req server example.org
```
or
```
./easyrsa --subject-alt-name="DNS:www.example.net,DNS:secure.example.net" build-server-full  alttest nopass
```

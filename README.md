## envoy hello validation context

Make sure the cert and key paths inside the envoy.yaml are right (use absolute
path if you're not sure).

Run envoy with the provided config.

```
$ envoy -c envoy.yaml
```

Call envoy using curl

To route to Google, with http/1.1:

```
curl -I --http1.1 --cacert ca-crt.pem --key client1-key.pem --cert client1-crt.pem https://localhost:10000
```

To route to Cloudflare, with http/2:

```
curl -I --http1.1 --cacert ca-crt.pem --key client1-key.pem --cert client1-crt.pem https://localhost:10000
```

Enjoy!

### To generate the `verify_certificate_hash` hash

E.g. for client1-crt.pem.

```
$ openssl x509 -in path/to/client1-crt.pem -outform DER | openssl dgst -sha256 | cut -d" " -f2
```
### license

MIT

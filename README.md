## envoy hello validation context

Make sure the cert and key paths inside the envoy.yaml are right (use absolute
path if you're not sure).

Run envoy with the provided config.

```
$ envoy -c envoy.yaml
```

Call envoy using curl

```
curl --cacert ca-crt.pem --key client1-key.pem --cert client1-crt.pem https://localhost:10000
```

Enjoy!

### license

MIT

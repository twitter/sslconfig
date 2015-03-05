sslconfig
=========

Twitter's OpenSSL configuration

Twitter currently uses OpenSSL 1.0.2a (+ patches).

Twitter enables the following ciphers (using the server's preference):

```
ECDHE-RSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-SHA:ECDHE-RSA-AES256-SHA:AES128-GCM-SHA256:AES128-SHA:AES256-SHA:DES-CBC3-SHA:RC4-SHA
```

## RC4 Patch

Twitter uses a [patch](patches/openssl_disable_rc4.patch) for OpenSSL that
disables the use of RC4 in TLS v1.1+.

## Session Ticket Patch

Twitter uses a [patch](patches/openssl_session_ticket.patch) for OpenSSL that
enables session ticket key rotation via a new API call, SSL_CTX_set_tlsext_ticket_key_list.

## Advertised Ciphers Callback Patch

Twitter uses a [patch](patches/openssl_set_advertised_ciphers_cb.patch) for OpenSSL that
registers a callback to introspect the client's advertised ciphers.

## License
Copyright 2015 Twitter, Inc.

Licensed under the Apache License, Version 2.0: http://www.apache.org/licenses/LICENSE-2.0

sslconfig
=========

Twitter's OpenSSL configuration. The goal of this project is to share our work with upstream and any other interested parties. We intend to open source any future work we do that improves the security of Twitter and the internet as a whole.

At the time of this writing, Twitter currently uses OpenSSL 1.0.2a (+ patches).

Twitter enables the following ciphers (using the server's preference):

```
ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:ECDHE-ECDSA-AES128-SHA:ECDHE-RSA-AES128-SHA:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES256-SHA:ECDHE-RSA-AES256-SHA:AES128-GCM-SHA256:AES128-SHA256:AES128-SHA:AES256-GCM-SHA384:AES256-SHA256:AES256-SHA:ECDHE-ECDSA-DES-CBC3-SHA:ECDHE-RSA-DES-CBC3-SHA:DES-CBC3-SHA
```

## Session Ticket Patch

Twitter uses a [patch](patches/openssl_session_ticket.patch) for OpenSSL that
enables session ticket key rotation via a new API call, SSL_CTX_set_tlsext_ticket_key_list.

## Advertised Ciphers Callback Patch

Twitter uses a [patch](patches/openssl_set_advertised_ciphers_cb.patch) for OpenSSL that
registers a callback to introspect the client's advertised ciphers.

## License
Copyright 2015 Twitter, Inc.

Licensed under the Apache License, Version 2.0: http://www.apache.org/licenses/LICENSE-2.0

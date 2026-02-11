# php-reverse-shell
## Encrypted Connection (TLS)

This fork uses `tls://` in `fsockopen()`, meaning the reverse connection is encrypted using TLS.

The listener must support SSL/TLS.

### Example listener (ncat)


`ncat --ssl -lvnp 1234`

### Example listener (openssl)

- 2.Generate self-signed certificate
  - `openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365 -nodes`
- 2.Listen
  - `openssl s_server -quiet -accept 1234 -cert cert.pem -key key.pem`

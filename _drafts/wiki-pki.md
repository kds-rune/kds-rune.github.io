---
layout: post
title: Wiki | Public Key Infrastructure (pki)
categories: ['wiki']
published: false
---
# Desctiption
...only a draft...

# Public Key Infrastructure (PKI)
1) Basic components
2) Asymetric encryption
3) Aquire signed certificate

## Basic components
...todo

#### Certificate Authority
- ca.key  -- private key (secret!)
- ca.pub  -- public key (from private key)
- ca.crt  -- self-signed public key (certificate)
- ca.srl  -- list of signed certificates by this ca

#### Your server/domain (e.g. acme)
- acme.key -- private key (secret!)
- acme.pub -- public (unsigned) key
- acme.csr -- certificate signing request (with public certificate & info)
- acme.crt -- ca-signed public key (certificate)

#### Keystore
Store your keys here.. TODO
Requires:
- private key which requested (csr) the certificate
- signed certificate

## Asymetric Encryption
Video links:
- [Public key cryptography - Diffie-Hellman Key Exchange (full version)](https://www.youtube.com/watch?v=YEBfamv-_do) (2:45)
- [Asymmetric encryption - Simply explained](https://www.youtube.com/watch?v=AQDCe585Lnc)
- [Demystifying Encryption, SSL TLS, and IBM's GSKit](https://www.youtube.com/watch?v=fhibQMB71cc)

Encryption:
- clear text > cipher (with public key/rsa) > encrypted message

Decryption:
- encrypted message > cipher (with your private key) > clear text

Signing:
- ..todo

#### Handshake
- Communication starts out asynchronous
- Client (e.g. browser) sends "hello" to server (e.g. www)
- Server replies with its signed public key (certificate)
- Client verifies certificate is signed by ca authority (LetsEncrypt, DigiCert, etc)
- Cipher suite/protocol is agreed upon
- Client sends message encrypted with servers public key
- Server verifies message
- Symmetric keys are exchanged, and synchronous (faster) communication starts

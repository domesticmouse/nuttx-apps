# `crypto/openssl_mbedtls_wrapper/include/openssl`

## Overview
Implements `crypto/openssl_mbedtls_wrapper/include/openssl` source and header components (`aes.h`, `asn1.h`, `base.h`, `bio.h` and 36 more files) in the NuttX application tree.

## Interface
- [aes.h:struct aes_key_st]
- [aes.h:AES_KEY]
- [aes.h:AES_set_encrypt_key]
- [aes.h:AES_encrypt]
- [aes.h:AES_set_decrypt_key]
- [aes.h:AES_decrypt]
- [aes.h:AES_cbc_encrypt]
- [aes.h:AES_ENCRYPT]
- [aes.h:AES_DECRYPT]
- [aes.h:AES_BLOCK_SIZE]
- [aes.h:AES_MAXNR]
- [asn1.h:ASN1_BIT_STRING_free]
- [asn1.h:ASN1_INTEGER_free]
- [asn1.h:ASN1_OBJECT_free]
- [asn1.h:ASN1_OCTET_STRING_free]
- [asn1.h:ASN1_TIME_free]
- [asn1.h:ASN1_BIT_STRING_new]
- [asn1.h:ASN1_BIT_STRING_set_bit]

## Invariants
- [ssl_dbg.h:CONFIG_OPENSSL_DEBUG_LEVEL]: Conditional compilation gated by `CONFIG_OPENSSL_DEBUG_LEVEL`.
- [ssl_dbg.h:CONFIG_OPENSSL_DEBUG]: Conditional compilation gated by `CONFIG_OPENSSL_DEBUG`.
- [ssl_dbg.h:CONFIG_OPENSSL_ASSERT_DEBUG]: Conditional compilation gated by `CONFIG_OPENSSL_ASSERT_DEBUG`.

## Side Effects
- None

## Verification
- Run: `make test`

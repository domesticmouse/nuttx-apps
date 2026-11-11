# `crypto/controlse`

## Overview
NXP SE05x Secure Element keystore management library and CLI tool (`controlse`) providing key generation, ECDSA signing/verification, X.509 certificate/CSR handling, and Mbed TLS PK integration.

## Interface
- [controlse_main.cxx:main]
- [csecure_element.cxx:Controlse::CSecureElement::CSecureElement]
- [csecure_element.cxx:Controlse::CSecureElement::GenerateKey]
- [csecure_element.cxx:Controlse::CSecureElement::SetKey]
- [csecure_element.cxx:Controlse::CSecureElement::GetKey]
- [csecure_element.cxx:Controlse::CSecureElement::DeleteKey]
- [csecure_element.cxx:Controlse::CSecureElement::CreateSignature]
- [csecure_element.cxx:Controlse::CSecureElement::Verify]
- [ccertificate.cxx:Controlse::CCertificate::CCertificate]
- [ccsr.cxx:Controlse::CCsr::CCsr]
- [cpublic_key.cxx:Controlse::CPublicKey::CPublicKey]
- [cmbedtls_se05x_extension.hxx:Controlse::MbedtlsSe05xExtension::mbedtls_pk_setup_key_se05x]
- [Kconfig:CONFIG_CRYPTO_CONTROLSE]

## Invariants
- [Kconfig:CRYPTO_CONTROLSE]: Requires `DEV_SE05X`, `CRYPTO_MBEDTLS`, and `MBEDTLS_VERSION = "3.6.2"`.
- [controlse_main.cxx:setOperation]: Enforces a single keystore operation per CLI invocation (`settings->operation == KEYSTORE_NO_ACTION`), returning `-EPERM` otherwise.
- [ccertificate.cxx:Controlse::CCertificate::GetSerialNumber]: Requires certificate serial number length `crt.serial.len == CSerialNumber::SERIAL_NUMBER_SIZE` (`20` bytes).

## Side Effects
- [csecure_element.cxx:Controlse::CSecureElement]: Opens `/dev/se05x` (`O_RDONLY`) and issues `SEIOC_GENERATE_KEYPAIR`, `SEIOC_SET_KEY`, `SEIOC_GET_KEY`, `SEIOC_DELETE_KEY`, `SEIOC_SET_DATA`, `SEIOC_GET_DATA`, `SEIOC_CREATE_SIGNATURE`, `SEIOC_VERIFY_SIGNATURE`, `SEIOC_DERIVE_SYMM_KEY`, `SEIOC_GET_UID`, and `SEIOC_GET_INFO` `ioctl` commands.
- [controlse_main.cxx:readFromFile]: Reads input files or `stdin` via `fopen` and writes output/diagnostics to `stdout`/`stderr`.

## Verification
- Run: `make test`

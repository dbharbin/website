---
author: shebu-kuriakose
title: MBed TLS v3.3.0 Release!
date: 2023-01-09 10:00:00

image: "../../assets/images/blog/musca_tf_crop_1500x1500.png"
---

## Introduction

The Mbed TLS project has released v3.3.0 and v2.28.2 LTS in December 2021. Being the development release since July 2021, v3.3.0 includes several enhancements, bug fixes and security fixes. v2.28.2 released from the Mbed TLS 2.28 Long Term Support (LTS) branch includes the latest bug fixes and security fixes.

Refer to the [release notes](https://github.com/Mbed-TLS/mbedtls/releases/tag/v3.3.0) for a complete list of changes in the release. Here are some of the highlights of v3.2.1:

## Highlights

1. **DTLS Connection ID** is supported as per RFC 9146 and is enabled by default.

2. **EC J-PAKE** functionality including key exchange is supported using PSA Crypto APIs. More enhancements will be available in future releases. Earlier only a limited subset of crypto operations in TLS, X.509 and PK used PSA Crypto APIs using the MBEDTLS_USE_PSA_CRYPTO config option. In Mbed TLS 3.2.1, most of the crypto operations are done using PSA Crypto APIs with a few exceptions. Refer [here](https://github.com/Mbed-TLS/mbedtls/blob/development/docs/use-psa-crypto.md) for list of exceptions

3. **PSA Crypto Drivers:** Work is ongoing in the project to build the library without certain software implementations when accelerators are present for the same. Some modules can now use PSA drivers for hashes in certain configurations, with no built-in software implementation present.

   The initial version of the PSA driver wrapper generator, generate_driver_wrappers.py, is available in the release.

   From Mbed TLS 3.2.1 onwards, when using the MBEDTLS_USE_PSA_CRYPTO config option, most of the crypto operations in TLS, X.509 and PK are done using PSA Crypto APIs with a few exceptions.

   Refer [here](https://github.com/Mbed-TLS/mbedtls/blob/development/docs/use-psa-crypto.md) for list of exceptions.

4. **TLS 1.3 Enhancements:** Key establishment via pre-shared keys, support for opaque keys as the private keys associated to certificates for authentication and several bug fixes are included. Details about TLS1.3 support can be found [here](https://github.com/Mbed-TLS/mbedtls/blob/development/docs/architecture/tls13-support.md).

5. **LMS post-quantum-safe stateful-hash asymmetric signature scheme** has been added. It is not intended for use in TLS, but instead for verification of assets transmitted over an insecure channel, such as firmware images.

## What’s Next?

During H1’2023, focus will remain on some of the remaining areas of TLS and X.509 using PSA Crypto such as TLS and X.509 working when the library is built without software implementations of crypto operations (if crypto hardware supports those operations). TLS 1.3 enhancements such as [early data](https://github.com/orgs/Mbed-TLS/projects/1) support, PBKDF2 PSA API implementation are also areas the project plans to spend time on. Look at the project [roadmap](https://mbed-tls.readthedocs.io/en/latest/roadmap/) for further details.

We welcome community participation in ongoing and future work items in the project that can be found [here](https://github.com/orgs/Mbed-TLS/projects/1). Subscribe to the [mailing list](https://lists.trustedfirmware.org/mailman3/lists/mbed-tls.lists.trustedfirmware.org/) to start participating in the design and development of the project. The bi-weekly Mbed TLS [Technical Forums](/meetings/mbed-tls-technical-forum/) are also an opportunity to understand major developments in the project.

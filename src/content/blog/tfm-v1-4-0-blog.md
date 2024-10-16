---
author: shebu-kuriakose
title: Trusted Firmware-M v1.4.0 Release
date: 2021-08-04 10:00:00

image: "../../assets/images/blog/musca_tf_crop_1500x1500.png"
---

# **Trusted Firmware-M: v1.4.0 Release**

## Introduction

Trusted Firmware-M (TF-M) [v1.4.0](https://git.trustedfirmware.org/TF-M/trusted-firmware-m.git/tree/docs/releases/1.4.0.rst) was released on 04 th August 2021. The release includes integration of
Mbed TLS3.0.0, implementation of features in PSA Firmware Framework-M v1.1 and improved
documentation since the last release v1.3.0. This release was tested using the Trustedfirmware projects’
[Open Continuous Integration (CI) System](https://ci.trustedfirmware.org/).

## Highlights of the TF-M v1.4.0

While there have been around 250 commits in TF-M master branch since TF-Mv1.3.0, here are some of
the highlights included in TF-Mv1.4.0.

- Mbed TLS3.0.0: PSA Crypto service is updated to Mbed TLS3.0. Mbed TLS3.0.0 was a major [release](/blog/mbed-tls-30/)
  with numerous changes and support for new PSA Crypto APIs one-shot cipher functions,
  psa_cipher_encrypt and psa_cipher_decrypt, according to the PSA Crypto API 1.0.0 specification.

- [Firmware Framework for M v1.1](https://developer.arm.com/documentation/aes0039/latest) initial set of changes to align with the v1.1 was included in TF-Mv1.3. Further enhancements to static handle, stateless service, and initial implementation of first level interrupt handling are included. Further changes to fully align with the Specification will continue.

- There has been continuous improvement in [TF-M documentation](https://tf-m-user-guide.trustedfirmware.org/) over the past few releases. There has been extensive clean up and restructuring of the documentation structure in this release for improved navigation and readability. An updated guide on porting to new hardware is also available.

- [Squad dashboard](https://qa-reports.linaro.org/tf/tf-m/metrics/?environment=AN521_ARMCLANG_1_Minsizerel_BL2&metric=:summary:) to track TF-M metrics. As of now, the dashboard shows the TF-M’s memory footprint measurements.

- Laird Connectivity BL5340 DVK is the newly added platform. This adds to already [supported platforms](https://tf-m-user-guide.trustedfirmware.org/platform/index.html) - NUCLEO-L552ZE-Q, STM32L562E-DK, LPCXpresso55S69, PSoC(R) 64, nRF5340 DK, nRF5340 PDK, M2354, M2351 and Cortex-M55 plus Ethos-U55 Corstone-300 AN547 FPGA. Enhancements and fixes have been made to some of these platform ports.

- [PSA Firmware Update API](https://tf-m-user-guide.trustedfirmware.org/platform/index.html) defines a standard set of firmware update interfaces that can be used by update applications and cloud connector clients. In this tag, Trusted Firmware-M has implemented these interfaces as a new runtime Secure Service in TF-Mv1.3. Further enhancements have been made to support image update with dependencies.

- MCUboot enhancements has been included by integrating latest tag 'TF-Mv1.4-integ'

More details can be found [here](https://tf-m-user-guide.trustedfirmware.org/releases/1.4.0.html). Since TF-Mv1.3.0 release, FreeRTOS OTA and TF-M integration is available in otal_pal_psa in [Amazon FreeRTOS github](https://github.com/aws/amazon-freertos/tree/main/libraries/abstractions). A [pull request](https://github.com/azure-rtos/getting-started/pull/264) has also been raised showcasing integration of Azure RTOS and TF-M on Arm MPS3 AN534 platform.

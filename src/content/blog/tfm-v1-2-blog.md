---
author: shebu-kuriakose
title: Trusted Firmware-M v1.2.0
date: 2020-11-30 10:00:00

image: "../../assets/images/blog/musca_tf_crop_1500x1500.png"
---

# **Trusted Firmware-M: v1.2.0**

## Introduction

Trusted Firmware-M (TF-M)
[v1.2.0](https://git.trustedfirmware.org/TF-M/trusted-firmware-m.git/tag/?h=TF-Mv1.2.0)
is the TF-M release tag made on 25th of November 2020. This tag has a
new set of features, enhancements, and platforms since TF-Mv1.1 tag.

## Highlights of TF-M v1.2.0

While there have been around 370 commits in TF-M master branch since TF-Mv1.1, here are some of
the highlights included in TF-Mv1.2.0:

- nRF9160 DK, nRF5340 DK, nRF5340 PDK, M2351, Corstone-300 Ethos-U55 FVP (Cortex-M55 plus
  Ethos-U55 SSE-300 MPS3) are newly enabled platforms. STM32 Nucleo-144, LPCXpresso55S69,
  PSoC(R) 64 were already supported.

- A more modular build system based on Modern CMake. This has reduced the complexity of the
  build system, making it easier to add and enhance TF-M components and platform ports. The
  enhancements have made the TF-M builds faster and allowed easier integration with other CMake
  build systems.

- PSA Isolation Level3 support on Arm reference platforms MuscaB1 and AN521. This highest isolation
  level defined by [Firmware Framework-M](https://developer.arm.com/-/media/Files/pdf/PlatformSecurityArchitecture/Architect/DEN0063-PSA_Firmware_Framework-1.0.0-2.pdf?revision=2d1429fa-4b5b-461a-a60e-4ef3d8f7f4b4&la=en&hash=BE8C59DBC98212591E1F935C2312D497011CD8C7) provides isolation of Secure Partition from Non-Secure
  Processing Environment (NSPE) and other Secure Partitions. The PSA Root of Trust (RoT) domain is
  also isolated from NSPE and all Secure Partitions. PSA Isolation Level3 is expected to be enabled on
  other platform as well in the near future.

- Modified Secure Partition Manager (SPM) Hardware Abstraction Layer (HAL) making the
  abstractions easier for different device architecture.

- TF-M MCUBoot fork has been removed from the project and uses MCUBoot upstream (1.7.0-rc1) as
  the 2 nd stage bootloader. MCUBoot now also includes generic software counter measures to
  mitigate against fault injection attacks.

- Profile [Medium](https://tf-m-user-guide.trustedfirmware.org/configuration/profiles/tfm_profile_medium.html) – TF-M Profile aligning with PSA Certified Level 2 Root of Trust (RoT) Protection
  Profile requirements. TF-Mv1.1 enabled Profile [Small](https://tf-m-user-guide.trustedfirmware.org/configuration/profiles/tfm_profile_small.html).

- PSA Crypto updated to use Mbed TLS v2.24.

In addition to this latest release, the TF-M [mini-website](/projects/tf-m/) as part of the new Trusted Firmware [website](/)
was launched recently. The [Open Test System](https://ci.trustedfirmware.org/) has also started testing more build configurations for
multiple platforms. Mbed OS, Free RTOS, TF-M CMSIS Pack and Zephyr upstream integration of Trusted
Firmware-M are expected to be updated to TF-M v1.2.0 soon.

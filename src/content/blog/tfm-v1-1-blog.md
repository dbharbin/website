---
author: shebu-kuriakose
title: Trusted Firmware-M v1.1 and Ecosystem Enablement
date: 2020-07-22 10:00:00

image: "../../assets/images/blog/musca_tf_crop_1500x1500.png"
---

# **Trusted Firmware-M: v1.1 and Ecosystem Enablement**

## Introduction

Trusted Firmware-M (TF-M)
[v1.1](https://git.trustedfirmware.org/TF-M/trusted-firmware-m.git/tag/?h=TF-Mv1.1)
is the TF-M release tag made on 09th July 2020. This tag has a new set
of features, platforms and improved documentation since TF-Mv1.0 tag
that was made end of March 2020. TF-M has also been enabled in various
ecosystems over the last few months easing the route to security for IoT
developers.

## Highlights of the TF-M v1.1

While there have been around 200 commits in TF-M master branch since
TF-Mv1.0, here are some of the highlights included in TF-Mv1.1

- mcuboot upstream is used by default as the Stage2 bootloader instead
  of the TF-M mcuboot that was derived from mcuboot at the start of
  TF-M project. All the mcuboot features developed in TF-M have been
  merged to mcuboot project.

- STM32L562E-DK, STM32 Nucleo-144, LPCXpresso55S69, Corstone-300
  (Cortex-M55 based) are newly enabled platforms. PSoC(R) 64, Arm
  reference platform were already supported in TF-Mv1.0

- Profile Small -- Reduced memory footprint TF-M meeting [PSA
  Certified Level
  1](https://www.psacertified.org/getting-certified/silicon-vendor/overview/level-1/)
  Root of Trust (RoT) requirements

- IAR Compiler Support

- Initial Fuzzer Tool Support

## Release Cadence

The previous TF-M tags were made whenever the project had a reasonable
number of new capabilities and was not following a regular cadence. TF-M
has recently published the [release cadence and
process](https://ci-builds.trustedfirmware.org/static-files/ELVnWBhwKZva5dUxJAdMBum0BjVQuSXHC-mDrge5xc4xNjUxNjg0NDk3MTgwOjk6YW5vbnltb3VzOmpvYi90Zi1tLWJ1aWxkLWRvY3MtbmlnaHRseS9sYXN0U3RhYmxlQnVpbGQvYXJ0aWZhY3Q=/trusted-firmware-m/build/docs/user_guide/html/releases/release_process.html#release-cadence-and-process)
with an aim to make releases every four months.

## Memory Usage and Profile Small

TF-M provides Secure Processing Environment for Cortex-M devices where
the capabilities and resources hugely vary. Certain devices come with
very limited memory resources. The IoT use cases that utilize these
devices will also have different levels of security requirements.
Therefore, it is important for TF-M to provide different configurations
to satisfy security requirements of these different classes of IoT
devices.

TF-M wants to provide different Profiles with increasing level of
security functionality allowing device manufacturers to choose (and
further customize if required) a profile based on Threat Model and
Security Analysis of their use case.

TF-M v1.1 includes support for Profile Small aimed at memory constrained
devices meeting requirements for PSA Certified Level 1. Profile Medium
is in the works.

## Documentation Improvements

An improved HTML rendering of all the in-source TF-M documentation is
available in [trustedfirmware.org-\> Documentation-\> Docs -\>
TF-M](https://ci.trustedfirmware.org/job/tf-m-build-docs-nightly/lastStableBuild/artifact/trusted-firmware-m/build/docs/user_guide/html/index.html).
This allows people new to TF-M project to easily navigate through the
documentation resources. The documentation includes

- How to Build and Start Using TF-M and Contributing

- User Guides on Secure Services

- Designs

- PSA

# Ecosystem Enablement

Ecosystem support is increasing, giving IoT application developers
different routes to access TF-M and improve security.

- TF-M till recently supported Arm Compiler and GCC. With TF-M v1.1,
  IAR compiler is also supported. Information about IAR support can be
  found
  [here](https://ci-builds.trustedfirmware.org/static-files/nklUEgoRNcp0GIE1rAXknNmE89kDy9wQdW1nf0eKS6AxNjU3MDMxOTg1NzQxOjk6YW5vbnltb3VzOmpvYi90Zi1tLWJ1aWxkLWRvY3MtbmlnaHRseS9sYXN0U3RhYmxlQnVpbGQvYXJ0aWZhY3Q=/trusted-firmware-m/build/docs/user_guide/html/building/tfm_build_instruction_iar.html)

- TF-M CMSIS Pack based on TF-M v1.0 is
  [available](https://www.keil.com/dd2/Pack/#/ARM.TFM.2.0.0.pack).
  This pack works with various device family packs and AWS MQTT
  examples -
  [NUCLEO-STM32L552ZE](https://www.keil.com/download/files/AWS_MQTT_Demo_NUCLEO-L552ZE-Q_TZ.zip),
  [LPCXpresso55S69-EVK](https://www.keil.com/download/files/AWS_MQTT_Demo_LPCXpresso55S69_TZ.zip),
  [STM32L562E-DK](https://www.keil.com/download/files/AWS_MQTT_Demo_STM32L562E-DK_TZ.zip),
  and [Arm
  Musca-S1](https://www2.keil.com/docs/default-source/default-document-library/AWS_MQTT_Demo_Musca-S1.zip)

- [MCUXpresso
  SDK](https://www.nxp.com/design/software/development-software/mcuxpresso-software-and-tools/mcuxpresso-software-development-kit-sdk:MCUXpresso-SDK)
  includes TF-M support for LPC55S69

- [STM32CubeL5 MCU
  Package](https://www.st.com/en/embedded-software/stm32cubel5.html)
  includes TF-M support and provides an [application
  note](https://www.st.com/content/ccc/resource/technical/document/user_manual/group1/fb/57/0a/1c/6a/e1/44/fa/DM00678763/files/DM00678763.pdf/jcr:content/translations/en.DM00678763.pdf)
  for users to get started.

- MbedOS had initial TF-M support from MbedOS5.12. A more complete
  integration of TF-M as Secure Processing Environment is becoming
  available for various platforms from
  [MbedOS6.1](https://github.com/ARMmbed/mbed-os/releases/tag/mbed-os-6.1.0)
  onwards.

- [Zephyr
  2.3](https://docs.zephyrproject.org/latest/releases/release-notes-2.3.html)
  release has integrated Trusted Firmware-M for Musca-B1 platform with
  more platforms expected to be supported with TF-M in the coming
  releases.

- The
  [202007.00](https://github.com/aws/amazon-freertos/tree/202007.00)
  release of AWS reference integrations includes
  [TF-M](https://github.com/aws/amazon-freertos/tree/202007.00/vendors/cypress/MTB/psoc6/psoc64tfm)
  for [Cypress
  PSoC64](https://devices.amazonaws.com/detail/a3G0h0000088AgXEAU/PSoC%C2%AE-64-Standard-secure-AWS-Wi-Fi-Bluetooth-Pioneer-Kit)

- FreeRTOS now supports a [shim layer](https://github.com/aws/amazon-freertos/tree/master/libraries/abstractions/pkcs11) that converts the FreeRTOS PKCS\#11 APIs to PSA Functional APIs. See psa folder in Amazon FreeRTOS [github](https://github.com/aws/amazon-freertos/tree/master/libraries/abstractions/pkcs11). This allows platforms enabled with FreeRTOS and TF-M to make use of PSA Functional APIs supported in TF-M when PKCS\#11 APIs are invoked. A [blog](https://www.freertos.org/2020/07/security-for-arm-cortex-m-devices-with-freertos.html) has been published about the FreeRTOS/TF-M integration on Musca-B1.

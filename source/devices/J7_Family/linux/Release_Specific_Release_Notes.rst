.. _release-specific-release-notes:

************************************
Release Notes
************************************
.. http://processors.wiki.ti.com/index.php/Processor_SDK_Linux_Release_Notes

Overview
========

The **Processor Software Development Kit (Processor-SDK) for Linux**
provides a fundamental software platform for development, deployment and
execution of Linux based applications and includes the following:

-  Bootloaders, Linux Kernel & Filesystem
-  SDK installer & Prebuilt Binaries
-  Setup scripts
-  Demo applications
-  Documentation

.. ifconfig:: CONFIG_sdk in ('JACINTO')

   .. Note::
      For building some of the RTOS-based demonstrations, you should also download
      Processor SDK RTOS installer. For more information,
      refer to <PSDKRA install path>/index.html.


Licensing
=========

Please refer to the software manifest, which outlines the licensing
status for all packages included in this release. The manifest can be found on the SDK
download page or in the installed directory as indicated below. In
addition, see :ref:`Processor SDK Linux GPLv3 Disclaimer <overview-gplv3-disclaimer>`.


Documentation
=============
-  :ref:`Processor SDK Linux Software Developer's Guide <linux-index>`: Provides information on features, functions, delivery package and,
   compile tools for the Processor SDK Linux release. This also provides
   detailed information regarding software elements and software
   infrastructure to allow developers to start creating applications.
-  :ref:`Processor SDK Linux Getting Started Guide <overview-getting-started>`: Provides information on getting the software and running
   examples/demonstrations bundled in the SDK.
-  **Software Manifest**: Provides license information on software
   included in the SDK release. This document is in the release at
   ``[INSTALL-DIR]/manifest``.
-  **EVM Quick Start Guide**: Provides information on hardware setup and
   running the demonstration application that is loaded on flash. This
   document is provided as part of the EVM kit.


Supported Platforms
===================
See :ref:`here <release-specific-supported-platforms-and-versions>` for a list of supported platforms and links to more information.


Release 11.00.00
================

Released April 2025

.. rubric:: What's New
   :name: whats-new

Processor SDK 11.00 Release supports the following platforms:

  * J721E
  * J7200
  * J721S2
  * J784S4
  * AM68
  * AM69
  * J722S
  * J742S2

Processor SDK 11.00 Release has following new features:

  * First 2025 LTS (Linux 6.12 and u-boot 2025.01) Reference Release Including RT combined branch model
  * ATF v2.12.0+
  * OPTEE 4.5.0
  * Yocto Scarthgap/5.0
  * HSM firmware loading support added for J721S2 and J784S4
  * HMAC support added in crypto driver
  * MCU_1_1 in split mode support added

Build Information
=================

.. _u-boot-release-notes:

U-Boot
------
| Head Commit: 70667128cb5b2c2a7621965ba948b5a56a2e756f: FROMLIST: configs: am62px: Add UBIFS support
| Date: Wed Mar 26 18:58:27 2025 +0530
| uBoot Version: 2025.01
| uBoot Description: 11.00.10

| Repo: git://git.ti.com/ti-u-boot/ti-u-boot.git
| Branch: ti-u-boot-2025.01
| uBoot Tag: 11.00.10

| Compiler Information: arm-oe-eabi-gcc (GCC) 13.3.0, aarch64-oe-linux-gcc (GCC) 13.3.0
|

.. ifconfig:: CONFIG_image_type in ('edgeai', 'adas')

   .. note::

      meta-edgeai Yocto layer contains additional patches for U-Boot `here <https://git.ti.com/cgit/edgeai/meta-edgeai/tree/recipes-bsp/u-boot?h=11.00.00.08>`__.

.. _kernel-release-notes:

Kernel
------
.. rubric:: Linux Kernel
   :name: linux-kernel

| Head Commit: cdcaeac783e31f18edb6cb44b526228f44023b45: PENDING: arm64: dts: ti: k3-am62l-main: Fix CPTS node
| Date: Wed Mar 26 14:47:58 2025 +0530
| Kernel Version: 6.12.17
| Kernel Description: 11.00.10

| Repo: git://git.ti.com/ti-linux-kernel/ti-linux-kernel.git
| Branch: ti-linux-6.12.y
| Tag: 11.00.10
| Non-RT Kernel defconfig: defconfig + ti_arm64_prune.config
| RT Kernel defconfig: defconfig + ti_rt.config + ti_arm64_prune.config

| Compiler Information: aarch64-oe-linux-gcc (GCC) 13.3.0, GNU ld (GNU Binutils) 2.42.0
|


.. ifconfig:: CONFIG_image_type in ('edgeai', 'adas')

   .. note::

      meta-edgeai Yocto layer contains additional patches for Kernel `here <https://git.ti.com/cgit/edgeai/meta-edgeai/tree/recipes-kernel/linux?h=11.00.00.08>`__.

.. _tf-a-release-notes:

TF-A
----
| Head Commit: b11beb2b6bd30b75c4bfb0e9925c0e72f16ca53f: PENDING: feat(ti): Update DDR Configurations
| Date : Fri Nov 1 05:20:32 2024 +0100
| Version:  2.12 based - tag 11.00.09

| Repo: https://github.com/TexasInstruments/arm-trusted-firmware.git
| Branch: ti-master
|

.. _optee-release-notes:

OP-TEE
------
| Head Commit: ef1ebdc23034a804a72da2207f1a825ce96a1464: plat-k3: Add initial support for AM62Lx SoC
| Date : Tue Oct 1 10:30:11 2024 +0530
| Version: 4.5.0+

| Repo: https://github.com/OP-TEE/optee_os/
| Branch: master
| Tag: 4.5.0+
|

.. _ti-linux-fw-release-notes:

ti-linux-firmware
-----------------
| Head Commit: c3ad8113c766bee7b8ddfae222e9b8017b565ea3: ti-dm: Update firmware for Jacinto devices
| Date: Wed Apr 9 12:27:38 2025 +0530

| Repo: https://git.ti.com/cgit/processor-firmware/ti-linux-firmware
| Branch: ti-linux-firmware
| Tag: 11.00.10
|



Yocto
-----
.. rubric:: meta-ti
   :name: meta-ti

| Head Commit: a98a2e1029870b25e117d4c9410e75bfd955f35a: CI/CD Auto-Merger: cicd.scarthgap.202504090823
| Date: 2025-04-09 08:23:38 -0500

| Repo: git://git.yoctoproject.org/meta-ti
| Branch: scarthgap
| Release Tag: 11.00.10
|

.. rubric:: meta-arago
   :name: meta-arago

| Head Commit: c04e85dd207dd24387edac10526b9ec971df9496: CI/CD Auto-Merger: cicd.scarthgap.202504090823
| Date: 2025-04-09 08:23:34 -0500

| Repo: git://git.yoctoproject.org/meta-arago
| Branch: scarthgap
| Release Tag: 11.00.10
|

.. rubric:: meta-tisdk

| Head Commit: 73aae47bf953dd4cf06e448367135b1cac0869a1 meta-ti-foundational: ti-apps-launcher: Update SRCREV

| Repo: https://github.com/TexasInstruments/meta-tisdk.git
| Branch: scarthgap
| Release Tag: REL.J7.11.00-01
|

.. ifconfig:: CONFIG_image_type in ('edgeai', 'adas')

   .. rubric:: meta-edgeai

   | Head Commit: 81d1b80b2a314814c6d900e82ea2da93eee3f57d [20250519] EDGEAI Auto Update
   | Date: 2025-05-19

   | Clone: git://git.ti.com/edgeai/meta-edgeai.git
   | Branch: scarthgap
   | Release Tag: 11.00.00.08
   |

Issues Tracker
==============

Issues opened in previous releases that were closed on this release
-------------------------------------------------------------------
.. csv-table::
  :header: "Record ID", "Title", "Platform"
  :widths: 15, 70, 20

  "LCPD-42102","ALSA performance test failures ","j721s2-evm,j721s2_evm-fs"
  "LCPD-42100","IPC test failure in test farm in SDK 10.1 RC 2 ","j742s2_evm-fs,j784s4-evm"
  "LCPD-42098","OSPI failure in Farm on J742s2 device","j742s2_evm-fs"
  "LCPD-42096","eMMC boot is not working in test farm","am69_sk-fs"
  "LCPD-41113","Linux kernel boot failure when we apply ""k3-j784s4-evm-quad-port-eth-exp1.dtbo"" overly","j784s4-evm"
  "LCPD-41056","J784s4 outputs error message about AUDIO_EXT_REFCLK1 parent","am69_sk-fs,j784s4-hsevm"
  "LCPD-41036","Full feature support for DSI interface on AM6x","am68_sk-fs,am69_sk-fs,j722s_evm-fs"
  "LCPD-41002","J721E: glmark2 refract test causes hardware recovery","j721e-hsevm,j721e-idk-gw,j721e-sk"
  "LCPD-40965","IPC: Late attach in Kernel fails in race conditions","am68_sk-fs,am69_sk-fs,j7200-evm,j721e-idk-gw,j721s2-evm,j784s4-evm"
  "LCPD-40110","SK-AM68: Intermittent failure when capturing with camera on J17 header","am68_sk-fs,am69_sk-fs"
  "LCPD-40083","J784s4: U-Boot: Mismatch in OSPI NAND flashing offsets for bootloader binaries in Code Vs documentation","j784s4-evm"
  "LCPD-39087","J7200 SPI device tree has wrong clock ID","j7200-evm"
  "LCPD-38947","CICD: CPSWnG Native tests fail","am62axx_sk-fs,j721e-idk-gw"
  "LCPD-38902","AM69: MTD mount failing on 10.0 SDK","am69_sk-fs"
  "LCPD-38654","Linux NAND test case failing on J784S4 and J721S2","j721s2-evm,j784s4-evm"
  "LCPD-38601","Warning in enabling audio clock[J784s4]","j784s4-evm"
  "LCPD-38498","IPC test are failing ","am68_sk-fs,am69_sk-fs,j7200-evm,j721e-idk-gw,j721s2-evm,j784s4-evm"
  "LCPD-38369","J784S4-EVM: AUDIO: PLAYBACK: sample rates 44100 and 88200 are not working on playback","j784s4-evm"
  "LCPD-38310","optee secure storage test fails ","j722s_evm-fs"
  "LCPD-38276","MMCSD: DDR50 test failing in  j7 devices ","j7200-evm,j721e-idk-gw,j721s2-evm,j722s_evm-fs,j784s4-evm"
  "LCPD-38107","USB2.0 Not enabled in SDK","j784s4-evm"
  "LCPD-38055","Remoteproc: Loading secondary R5F firmware from Linux user space fails","j784s4-evm"
  "LCPD-38036","Ethernet MAC Address change in every boot at u-boot.","j722s_evm-fs"
  "LCPD-37995","Format of DRAM logs print is confusing","j7200-evm,j721s2-evm,j722s_evm-fs,j784s4-evm"
  "LCPD-37812","videodev2.h: headers in targetfs is not same as in ti-linux-kernel","am62axx_sk-fs,am62axx_sk-se,j721e-evm-ivi,j721e-hsevm,j721e-idk-gw,j721e-sk,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,j721s2_evm-se,j722s_evm-fs,j784s4-evm,j784s4-hsevm"
  "LCPD-37740","USB DFU cmd in U-BOOT is not working","j784s4-evm"
  "LCPD-37727","Testcase for graceful shutdown of remoteprocs","am69_sk-fs,j784s4-evm"
  "LCPD-37725","SDK 10.01 RC 5 Display test failure","am68_sk-fs,am69_sk-fs,j722s_evm-fs,j784s4-evm"
  "LCPD-37699","J722S : SPI tests are not working due to overlay","j722s_evm-fs"
  "LCPD-37605","QSPI Test failing (Boot and detection in Linux)","j721e-idk-gw,j721s2-evm,j784s4-evm"
  "LCPD-37202","[UPSTREAM]OPTEE: transition from gic_cpu_init to gic_init_per_cpu","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs,am64xx_sk-fs,am68_sk-fs,am69_sk-fs,beagleplay-gp,j7200-evm,j721e-idk-gw,j721s2_evm-fs,j722s_evm-fs,j784s4-evm"
  "LCPD-36983","[CSIRX] Abrupt stop of a context will cause hang when other contexts are started","j721e-evm-ivi"
  "LCPD-36970","J721e: tiny rootfs fails to login","j721e-evm-ivi,j721e-idk-gw"
  "LCPD-36930","Add tests uart dma","j7200-evm,j721e-idk-gw,j721s2-evm,j784s4-evm"
  "LCPD-36878","CSIRX does not stream in a particular order","j721e-evm-ivi,j721s2-evm,j784s4-evm"
  "LCPD-36872","MAC Address changing in AM68A linux boot","am68_sk-fs"
  "LCPD-36760","Customer Issue: MHDP compatibility issue","am69_sk-fs,j784s4-evm"
  "LCPD-34920","Kernel: UBIFS test failing on J721E","j721e-idk-gw"
  "LCPD-34792","UBIFS fails in OSPI NAND boot","am62xx-lp-sk,j721s2-evm"
  "LCPD-34211","k3-j721e: Add support for HBMC  - REVERTED","j721e-idk-gw"
  "LCPD-32701","J7200 : USB Client : Mass storage performance tests failure","j7200-evm"
  "LCPD-32695","J784S4 : U-boot : Mass storage tests failure","j784s4-evm"
  "LCPD-32444","AM68: Linux: OV5640 refclk is defined incorrectly in the main domain","am68_sk-fs"
  "LCPD-28118","RGBA Encode throws timeout error for 720x512 resolution","j721e-idk-gw"
  "LCPD-25535","UBoot: customized ${optargs} doesn't take affect on K3 devices","am64xx-evm,am64xx-hsevm,am64xx_sk-fs,am654x-evm,am654x-hsevm,am654x-idk,j7200-evm,j7200-hsevm,j721e-evm,j721e-hsevm,j721e-idk-gw,j721s2-evm,j721s2-hsevm,j721s2_evm-fs"
  "LCPD-24686","j721e-idk-gw: Graphics tests fail due to wrong return code","j721e-idk-gw"
  "LCPD-20526","Kernel: UBIFS test failing on J721E","j721e-idk-gw"
  "LCPD-19164","perf utility missing from upstream rootfs","j721e-evm,j721e-idk-gw"
  "LCPD-17673","No software documentation for the Timer module","am335x-evm,am43xx-gpevm,am571x-idk,am572x-idk,am574x-idk,am57xx-evm,am654x-evm,beaglebone-black,dra71x-evm,dra72x-evm,dra7xx-evm,j721e-idk-gw"
  "LCPD-16505","Wrong clock rate is reported for 157:400, 157:401 (HSDIVIDER after PLL4 and 15)","j721e-idk-gw"

|

Issues found and closed on this release that may be applicable to prior releases
--------------------------------------------------------------------------------
.. csv-table::
  :header: "Record ID", "Title", "Platform"
  :widths: 15, 70, 20

  "LCPD-43533","EGLFS not releasing buffers when using clones","am335x-evm,am43xx-gpevm,am57xx-evm,am62pxx_sk-fs,am62xx_sk-fs,am654x-evm,am68_sk-fs,am69_sk-fs,bbai,bbai64-gp,beaglebone,beagleplay-gp,j721e-idk-gw,j721s2-evm,j722s_evm-fs,j742s2_evm-fs,j784s4-evm"
  "LCPD-43467","Null dereference on fdinfo when not bound to a render task","am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am68_sk-fs,am68_sk-se,am69_sk-fs,bbai64-gp,beagleplay-gp,j721e-idk-gw,j721e-sk,j721s2-evm,j721s2_evm-fs,j721s2_evm-se,j722s_evm-fs,j742s2_evm-fs,j784s4-evm"
  "LCPD-43322","CICD-next: PIGLIT_S_BGRA_GLES_TEXTURE failure   ","am62xx_lp_sk-fs,am62xx_sk-fs,j721e-idk-gw,j742s2_evm-fs"
  "LCPD-43266","ALSA perf failure","j721s2-evm"
  "LCPD-43240","j722s/am62p: eMMC Highspeed mode test fails","am62pxx_sk-fs,am62pxx_sk-se,j722s_evm-fs,j722s_evm-se"
  "LCPD-43212","U-Boot DDR50 testcase failing","j7200-evm,j721s2-evm,j722s_evm-fs"
  "LCPD-43179","RPROC_DMABUF_ATTACH ioctl is not thread safe in ti-linux-6.12","am62axx_sk-fs,am62axx_sk-se,j721e-idk-gw,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,j722s_evm-fs,j784s4-evm,j784s4-hsevm"
  "LCPD-43034","DFU function is not working in 11.00.06 ","j742s2_evm-fs"
  "LCPD-42575","J722S: U-Boot: Nand: Read beyond 20MB gets stuck infinitely","j722s_evm-fs"
  "LCPD-42561","MMCSD: DDR50 test failing in  j7 devices ","j7200-evm,j721e-idk-gw,j721s2-evm,j722s_evm-fs,j784s4-evm"
  "LCPD-42491","Linux SDK v10.0: TI-added support for W25N01JW SPI NAND breaks other existing Flash support","am62axx_sk-fs,am62axx_sk-se,am62lxx-vlab,am62lxx-zebu,am62lxx_evm-fs,am62lxx_evm-se,am62pxx-zebu,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_p0_sk-fs,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm,am64xx-hsevm,am64xx-hssk,am64xx_evm-se,am64xx_sk-fs,am64xx_sk-se,am654x-evm,am654x-hsevm,am654x-idk,am68_sk-fs,am68_sk-se,am69_sk-fs,bbai,bbai64-gp"
  "LCPD-42309","Customer issue: D3: J722S DP bridge working","j722s_evm-fs"
  "LCPD-42296","Linux: Native CPSW: Traffic starvation causes NETDEV WATCHDOG timeout","am62axx_sk-fs,am62axx_sk-se,am62lxx_evm-fs,am62lxx_evm-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_p0_sk-fs,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm,am64xx-hsevm,am64xx-hssk,am64xx_evm-se,am64xx_sk-fs,am64xx_sk-se,am654x-evm,am654x-hsevm,am654x-idk,am68_sk-fs,am68_sk-se,am69_sk-fs,bbai,bbai64-gp,beaglebone,beaglebone-black,beagleplay-gp,j7200-evm,j7200-hsevm,j7200_evm-fs,j721e-evm-ivi,j721e-hsevm,j721e-idk-gw,j721e-sk,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,j721s2_evm-se,j722s_evm-fs,j742s2_evm-fs,j784s4-evm,j784s4-hsevm"
  "LCPD-42291","K3 IPC: Late Attach fails in race conditions again!","j7200-evm,j721e-idk-gw,j721s2-evm,j784s4-evm"
  "LCPD-42234","CSI2RX: IMX219 overlays missing for V3Link fusion second port","am69_sk-fs"
  "LCPD-42212","J722S : OSPI performance test failing in Farm","j722s_evm-fs"

|

Errata Workarounds Available in this Release
--------------------------------------------
.. csv-table::
  :header: "Record ID", "Title", "Platform"
  :widths: 15, 30, 150

  "LCPD-27886","USART: Erroneous clear/trigger of timeout interrupt","am62axx_sk-fs,am62xx-sk,am64xx-evm,j721e-idk-gw,j7200-evm,j784s4-evm,j784s4-hsevm"
  "LCPD-22905","UDMA: TR15 hangs if ICNT0 is less than 64 bytes","am654x-evm,j721e-idk-gw"
  "LCPD-22544","DDR: LPDDR4 should be configured to 2666 MT/S","j7200-evm"
  "LCPD-19965","OSPI PHY Controller Bug Affecting Read Transactions","am64xx-evm,am654x-idk,j721e-idk-gw,j7200-evm"
  "LCPD-19068","DSS: Disabling a layer connected to Overlay may result in synclost during the next frame","j721e-evm,j721e-evm-ivi, j721e-idk-gw"
  "LCPD-19047","USB: Race condition while reading TRB from system memory in device mode","j721e-evm, j721e-hsevm, j721e-evm-ivi, j721e-idk-gw"
  "LCPD-17220","U-Boot Hyperbus: Hyperflash reads limited to 125MHz max. frequency","j721e-idk-gw"
  "LCPD-16605","MMC: MMC1/2 Speed Issue","j721e-evm, j721e-evm-ivi, j721e-idk-gw"



|

U-Boot Known Issues
-------------------
.. csv-table::
  :header: "Record ID", "Title", "Platform", "Workaround"
  :widths: 15, 30, 70, 30

  "LCPD-43613","U-boot: J722s: USB MSC boot is not working","j722s_evm-fs",""
  "LCPD-43548","U-Boot: DDR: Partial inline ECC does not account for second bank","j721s2-evm,j784s4-evm",""
  "LCPD-43481","AM69 : USB is not working at U-boot prompt","am69_sk-fs",""
  "LCPD-43476","Test: Custom builds for testing USB MSC at U-boot are not getting generated","am68_sk-fs,am69_sk-fs,j721e-idk-gw,j721s2-evm,j742s2_evm-fs,j784s4-evm",""
  "LCPD-43293","Resource Table generating wrong format for rm-cfg.yaml","am64xx-evm,j721e-sk",""
  "LCPD-42572","IPC: Testscript: Sometimes U-Boot not able to find firmware from boot media after symlink update","am68_sk-fs,am69_sk-fs,j721e-idk-gw,j721s2_evm-fs,j722s_evm-fs,j742s2_evm-fs,j784s4-evm",""
  "LCPD-42341","Missing Test support to verify order of remotecores being loaded at U-Boot","j7200-evm,j721e-idk-gw,j721s2-evm,j722s_evm-fs,j784s4-evm",""
  "LCPD-42161","U-Boot/SPL: Setting higher baud rate like 921600 does not work ","j7200-evm,j7200-hsevm,j721e-evm-ivi,j721e-sk,j721s2-evm,j721s2-hsevm,j742s2_evm-fs,j784s4-evm",""
  "LCPD-42095","Hyperflash boot failling","j7200-evm,j721e-idk-gw",""
  "LCPD-42041","Upstream: j721e: Initial U-boot prints taking around 10s","j721e-idk-gw",""
  "LCPD-41069","Linux SDK v10.0: U-Boot ""go"" command needs Linux Kernel-like cache/MMU cleanup so 3rd Party OS can startup correctly","am62axx_sk-fs,am62axx_sk-se,am62lxx-vlab,am62lxx-zebu,am62lxx_evm-fs,am62lxx_evm-se,am62pxx-zebu,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_p0_sk-fs,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm,am64xx-hsevm,am64xx-hssk,am64xx_evm-se,am64xx_sk-fs,am64xx_sk-se,am654x-evm,am654x-hsevm,am654x-idk,am68_sk-fs,am68_sk-se,am69_sk-fs,bbai,bbai64-gp,j7200-evm,j7200-hsevm,j721e-idk-gw,j721s2-evm,j721s2-hsevm,j722s_evm-fs,j722s_evm-se,j784s4-evm,j784s4-hsevm",""
  "LCPD-39144","J721s2: U-Boot: I2C: ""repeated start"" (Sr) not working","j721s2-evm",""
  "LCPD-38569","j722s: Unable to communicate with MCU R5 and Main R5 when FW loaded from U-Boot","j722s_evm-fs",""
  "LCPD-37623","Board intermittently fails to acquire DHCP address","am68_sk-fs",""
  "LCPD-34106","SPL: USB DFU Boot fails on J721S2 EVM on upstream U-Boot(also ti-u-boot-2023.04)","j721s2-evm,j721s2_evm-fs",""
  "LCPD-32697","Failed to get DHCP address in U-Boot","j784s4-evm",""
  "LCPD-24108","U-Boot: TISCI config ring fail traces seen in OSPI boot mode on J721E","j721e-evm,j721e-evm-ivi,j721e-idk-gw",""
  "LCPD-22904","U-boot: Update EMIFtool for i2244:DDR: Valid stop value must be defined for write DQ VREF training","j7200-evm,j721e-idk-gw",""
  "LCPD-17789","UBOOT J7:  Could not see UFS device by scsi scan","j721e-idk-gw",""


|

Linux Known Issues
------------------
.. csv-table::
  :header: "Record ID", "Title", "Platform", "Workaround"
  :widths: 5, 10, 70, 35

  "LCPD-43625","Test: USB audio class client device tests are failing","j7200-evm",""
  "LCPD-43624","Test: USB video class client device tests are failing","j7200-evm",""
  "LCPD-43618","Test: USB mouse test is failing","j7200-evm,j722s_evm-fs",""
  "LCPD-43615","Test: DFU boot test is failing","j721e-idk-gw,j722s_evm-fs",""
  "LCPD-43611","Test: USB audio tests are failing","am68_sk-fs,am69_sk-fs,j721e-idk-gw,j742s2_evm-fs,j784s4-evm",""
  "LCPD-43606","Test : USB HUB tests are failing for am69","am69_sk-fs",""
  "LCPD-43567","Linux: PCIe NTB Test failure in Farm","j721e-evm-ivi,j721e-hsevm,j721e-idk-gw,j742s2_evm-fs,j784s4-evm,j784s4-hsevm",""
  "LCPD-43480","USB : Selective suspend to RAM test is failing","am68_sk-fs,am69_sk-fs,j7200-evm,j721e-idk-gw,j721s2_evm-fs,j722s_evm-fs,j742s2_evm-fs,j784s4-evm",""
  "LCPD-43477","Test: Test for superspeed NCM client devices is failing","j721e-idk-gw",""
  "LCPD-43475","Test: Test for test for USB MSC device enumeration is failing","j721e-idk-gw,j742s2_evm-fs,j784s4-evm",""
  "LCPD-43472","Test: Test for full-speed NCM USB devices is failing.","am62axx_sk-fs,am62xx_lp_sk-fs,j7200-evm",""
  "LCPD-43465","TIDEC_GST_filesink_rush_hour_p1920x1080_cbr_10mbps.264 test fails","j721s2-evm,j742s2_evm-fs,j784s4-evm",""
  "LCPD-43464","TIDEC_GST_filesink_pedestrian_1920x1080_vbr_10mbps.264 fails","j721s2-evm,j742s2_evm-fs,j784s4-evm",""
  "LCPD-43463","OpenCL-CTS Failures ","am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs,am68_sk-fs,am69_sk-fs,j721e-idk-gw,j721s2-evm,j722s_evm-fs,j742s2_evm-fs,j784s4-evm",""
  "LCPD-43419","DFU boot fails on J784S4","j784s4-evm",""
  "LCPD-43411","lsof: Kernel abort : Causing uart unit tests to fail","am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs,j722s_evm-fs",""
  "LCPD-43407","IPC Graceful Shutdown on C7x cores","j721e-idk-gw,j721s2-evm,j722s_evm-fs,j784s4-evm",""
  "LCPD-43304","CSI RX driver does not consider byterperline parameter in set format","am62axx_sk-fs,am62axx_sk-se,j721e-evm-ivi,j721e-sk,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,j721s2_evm-se,j722s_evm-fs,j722s_evm-se,j742s2_evm-fs,j784s4-evm,j784s4-hsevm",""
  "LCPD-43267","Incorrect capability mapping for Ov5640 on am68/am69","am68_sk-fs,am69_sk-fs",""
  "LCPD-43264","J721S2 OV5640 Module not functional","j721s2-evm",""
  "LCPD-43260","UFS tests failure","j784s4-evm",""
  "LCPD-43259","CSI failures for J722S","j722s_evm-fs",""
  "LCPD-43131","Processor SDK Linux for AM67: Section ""3.2.2.17. USB"" has incorrect information","j722s_evm-fs",""
  "LCPD-43010","Memory leak in rpmsg_char.c","j7200-evm,j721s2-evm,j784s4-evm",""
  "LCPD-42843","remoteproc/k3-dsp: PDK IPC echo test binaries fails to do IPC in remoteproc mode on second run","j7200-evm,j721e-idk-gw,j721s2-evm,j722s_evm-fs,j784s4-evm",""
  "LCPD-42694","Getting kernel panic on receiving ethernet packet greater than 1703","j7200-evm",""
  "LCPD-42557","MSMC: A53, A72 Coherent Streaming Writes have minor sub-optimal performance","am654x-idk,j7200-evm,j721e-idk-gw,j721s2-evm,j784s4-evm","See description"
  "LCPD-42488","GPIO interrupts don't support setting smp_affinity","am62xx_sk-fs,am69_sk-fs,j721e-sk",""
  "LCPD-42330","Missing Testcases for validating signed firmware boot of rprocs","am68_sk-fs,am69_sk-fs,j7200-hsevm,j721e-hsevm,j721s2-hsevm,j784s4-hsevm",""
  "LCPD-42294","[uboot-eMMC]: Incorrect OTAP Delay for J721E SR2.0","j721e-evm-ivi,j721e-hsevm,j721e-idk-gw,j721e-sk",""
  "LCPD-42183","Fix the asound configuration for J721S2 for all 7 audio jacks","j721s2-evm",""
  "LCPD-42162","ALSA performance test failures ","j722s_evm-fs",""
  "LCPD-42153","Test Automation Dev: remoteproc/k3: Provide infrastructure for graceful shutdown of remote processors ","am62xx-lp-sk,am62xx-sk,am62xx_lp_sk-fs,am62xx_sk-fs,am62xx_sk-se,am64xx-evm,am64xx-hsevm,am64xx_sk-fs,am654x-evm,am654x-idk,beagleplay-gp,j7200-evm,j721e-evm,j721e-evm-ivi,j721e-idk-gw",""
  "LCPD-42101","Debug reason for MMC performance increase ","j721s2_evm-fs,j722s_evm-fs",""
  "LCPD-42099","UFS failure in Farm on J742s2/J784s4  device","j742s2_evm-fs,j784s4-evm",""
  "LCPD-42097","Review performance numbers in RC5 of SDK 10.1","j7200-evm,j721e-idk-gw,j721s2-evm",""
  "LCPD-41066","CSI outputs black images when DMA is set to ASEL 15","am62pxx_sk-fs,j722s_evm-fs",""
  "LCPD-41018","SK-AM68 intermittently fails to boot on warm reset","am68_sk-fs",""
  "LCPD-39029","J784s4: WKUP_UART as console hangs in R5 SPL in SDK 10.0","j784s4-evm",""
  "LCPD-38981","Rare: Kernel crash when trying to stop/start remotecores without sleep","j784s4-evm",""
  "LCPD-38558","Unable to gracefully shutdown both cores in R5 Cluster","j7200-evm,j721e-idk-gw,j721s2-evm,j784s4-evm",""
  "LCPD-38311","Power off test case failing","j7200-evm,j721e-idk-gw,j721s2-evm,j784s4-evm",""
  "LCPD-38267","J722S: tiboot3.bin / R5 SPL within size limit fails to boot","j722s_evm-fs",""
  "LCPD-38070","Misbehavior of CPSW due to ALE entries overwritten by driver","j721e-hsevm",""
  "LCPD-38041","RCU Torture test results in a crash","j784s4-evm",""
  "LCPD-37954","[DSS-DP]: REG_WAKEUP_TIME register value can go out of bound","am68_sk-fs,am68_sk-se,am69_sk-fs,j721e-evm-ivi,j721e-hsevm,j721e-idk-gw,j721e-sk,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,j721s2_evm-se,j722s_evm-fs,j784s4-evm,j784s4-hsevm,J784S4_BASESIM",""
  "LCPD-37705","crypto perf failure ","am68_sk-fs,j7200-evm,j722s_evm-fs",""
  "LCPD-37704","J722S/am62p : i2c test failing ","am62pxx_sk-fs,j722s_evm-fs",""
  "LCPD-37702","J722S : Crypto perf (ipsec) test failed ","j722s_evm-fs",""
  "LCPD-37690","UFS test case failing due test setup issue","j721e-idk-gw,j784s4-evm",""
  "LCPD-37507","DSS causes a freeze of processes every 10 seconds for about 200ms","am68_sk-fs","1. When HDMI is connected the GPU benchmarks freezes every 10 seconds for 200 ms (tested for weston-simple-egl), to prevent this disable DisplayPort in device tree. or 
  2. Connect display monitor as well, when running benchmark test."
  "LCPD-37415","RGB Encode Color Format Incorrect","j721e-idk-gw",""
  "LCPD-37387","NFS failure leads to stress test failure.","am68_sk-fs,j7200-evm,j721e-idk-gw,j721s2-evm,j784s4-evm,j784s4-hsevm",""
  "LCPD-37288","J784S4: USXGMII: Add automated test case","j784s4-evm,j784s4-hsevm",""
  "LCPD-37199","TPS6594: Error IRQ trap reach ilim, overcurrent for","j721e-idk-gw,j721s2-evm",""
  "LCPD-36952","Add support for J721S2 PG 1.1 in uboot","j721s2-evm",""
  "LCPD-36863","OPTEE/ATF are not protected by c7x","am68_sk-fs,j7200-hsevm,j721e-hsevm",""
  "LCPD-36841","TDA4VM/J721e: An indirect write completion error occurred in the linux OSPI driver","j721e-evm,j721e-idk-gw",""
  "LCPD-36748","M4F clock reported incorrectly with k3conf","am68_sk-fs,am69_sk-fs",""
  "LCPD-36474","J721s2 incorrect autogen generated data","j721s2-evm",""
  "LCPD-36386","IPSEC connection failure on automated setup in testfarm","j721e-idk-gw",""
  "LCPD-35384","After repetative connect/Disconnect EVM is  not getting detected to HOST pc in device mode ","j721s2-evm",""
  "LCPD-35066","CMA Failure with 4K video Files","j721e-idk-gw",""
  "LCPD-35005","h265 file decode infinite loop","j721s2-evm",""
  "LCPD-34926","Some LTP tests are failing due to missing configurations","j7200-evm",""
  "LCPD-34902","J721E EVM PCIe switch causes kernel panic","j721e-evm-ivi",""
  "LCPD-34895","GPU: PVRCarbon not supported with EGL_LINUX_DMA_BUF_EXT","j721e-evm-ivi,j721e-sk,j721s2-evm,j784s4-evm",""
  "LCPD-34826","Crash while running gstreamer app to record camera feed","j721e-sk",""
  "LCPD-34619","k3conf reports wrong error information while setting the clock frequency","j7200-evm",""
  "LCPD-34409","test case naming ""soft boot"" should be ""reboot""","am62axx_sk-fs,am62xx_sk-fs,j721e-idk-gw,j721s2-evm,j721s2_evm-fs",""
  "LCPD-32906","OSPI: Read data mismatch(first 32 bytes) when using DMA memcpy","am68_sk-fs,am69_sk-fs,j7200-evm,j7200-hsevm,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,j784s4-evm,j784s4-hsevm",""
  "LCPD-32544","J7200: OSPI Phy calibration fails intermittently","j7200-evm",""
  "LCPD-29736","videotestsrc of pattern 0 fails bufferhandling with encoder","j721e-idk-gw",""
  "LCPD-29647","Non-fatal failure logs seen during system boot up","j7200-evm",""
  "LCPD-29409","DMIPS number should reflect all 4 cores","am62pxx_sk-fs,am62pxx_sk-se,am62xx-sk,am62xx_sk-fs,am62xx_sk-se,j721e-idk-gw,j721s2-evm",""
  "LCPD-28861","J721e/j7200: MCU/WKUP UART as console. The output gets garbled after sysfw/dm load ","j7200-evm,j721e-evm",""
  "LCPD-28250","J721S2: QSPI Write corrupted when the first operation after powerup is erase","j721s2-evm,j721s2_evm-fs",""
  "LCPD-25304","J721S2: USB: USB 3.0 devices not getting enumerated in high speed","j721s2-evm,j721s2_evm-fs",""
  "LCPD-24725","PCIE RC Link fails when linux prints are made quiet","j721e-idk-gw",""
  "LCPD-24648","Move dma-heaps-test and ion-tests to TI repositories","am335x-evm,am572x-idk,am64xx-evm,dra71x-evm,j7200-evm,j721e-evm",""
  "LCPD-24589","no new usb reported on host after g_multi ","am57xx-evm,j721e-idk-gw",""
  "LCPD-24456","Move IPC validation source from github to git.ti.com","am335x-evm,am335x-hsevm,am335x-ice,am335x-sk,am437x-idk,am437x-sk,am43xx-epos,am43xx-gpevm,am43xx-hsevm,am571x-idk,am572x-idk,am574x-hsidk,am574x-idk,am57xx-beagle-x15,am57xx-evm,am57xx-hsevm,am62axx_sk-fs,am62xx-sk,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se,am64xx-evm,am64xx-hsevm,am64xx_sk-fs,am654x-evm,am654x-hsevm,am654x-idk,bbai,beaglebone,beaglebone-black,dra71x-evm,dra71x-hsevm,dra72x-evm,dra72x-hsevm,dra76x-evm,dra76x-hsevm,dra7xx-evm,dra7xx-hsevm,j7200-evm,j7200-hsevm,j721e-hsevm,j721e-idk-gw,j721e-sk,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,omapl138-lcdk",""
  "LCPD-22339","PCI-E USBCARD, ETHCARD don't indicate 2-lane support with lspci","j7200-evm,j721e-idk-gw",""
  "LCPD-20653","ltp: kernel syscall tests fail","am335x-evm,am43xx-gpevm,am654x-idk,j721e-idk-gw,j722s_evm-fs",""
  "LCPD-19739","AM65 shutdown error","am654x-idk,j7200-evm",""
  "LCPD-19499","Kernel: OSPI write throughput is less than 1MB/s","j7200-evm,j7200-hsevm",""
  "LCPD-19497","J7200: CPSW2g: interface goes up and down sporadically","j7200-evm","Seen only on very few EVMs. No workaround. "
  "LCPD-19084","Few SD cards not enumerating in Kernel with Alpha EVM","j721e-idk-gw",""
  "LCPD-19068","DSS: Disabling a layer connected to Overlay may result in synclost during the next frame","j721e-evm,j721e-evm-ivi,j721e-idk-gw",""
  "LCPD-16640","PCIe RC: GIC ITS misbehaves when more than 4 devices use it simultaneously","j721e-idk-gw",""
  "LCPD-16531","video decode: vxd_dec warnings displayed at end of gstreamer hevc playback to kmssink for certain video","j721e-idk-gw",""
  "LCPD-16396","J721E: RC: Unsupported request in configuration completion packets results in an abort","j721e-evm,j721e-evm-ivi,j721e-idk-gw","Workaround for Multifunction: Configure all the physical functions supported by the endpoint. For configuring all the 6 functions of PCIe  controller instance '1' in J721E, the following can be used. mount -t configfs none /sys/kernel/config; cd /sys/kernel/config/pci_ep/; mkdir functions/pci_epf_test/func1; echo 0x104c > functions/pci_epf_test/func1/vendorid; echo 0xb00d > functions/pci_epf_test/func1/deviceid; echo 1 > functions/pci_epf_test/func1/msi_interrupts; echo 16 > functions/pci_epf_test/func1/msix_interrupts; ln -s functions/pci_epf_test/func1 controllers/d800000.pcie-ep/; mkdir functions/pci_epf_test/func2; echo 0x104c > functions/pci_epf_test/func2/vendorid; echo 0xb00d > functions/pci_epf_test/func2/deviceid; echo 1 > functions/pci_epf_test/func2/msi_interrupts; echo 16 > functions/pci_epf_test/func2/msix_interrupts; ln -s functions/pci_epf_test/func2 controllers/d800000.pcie-ep/; mkdir functions/pci_epf_test/func3; echo 0x104c > functions/pci_epf_test/func3/vendorid; echo 0xb00d > functions/pci_epf_test/func3/deviceid; echo 1 > functions/pci_epf_test/func3/msi_interrupts; echo 16 > functions/pci_epf_test/func3/msix_interrupts; ln -s functions/pci_epf_test/func3 controllers/d800000.pcie-ep/; mkdir functions/pci_epf_test/func4; echo 0x104c > functions/pci_epf_test/func4/vendorid; echo 0xb00d > functions/pci_epf_test/func4/deviceid; echo 1 > functions/pci_epf_test/func4/msi_interrupts; echo 16 > functions/pci_epf_test/func4/msix_interrupts; ln -s functions/pci_epf_test/func4 controllers/d800000.pcie-ep/; mkdir functions/pci_epf_test/func5; echo 0x104c > functions/pci_epf_test/func5/vendorid; echo 0xb00d > functions/pci_epf_test/func5/deviceid; echo 1 > functions/pci_epf_test/func5/msi_interrupts; echo 16 > functions/pci_epf_test/func5/msix_interrupts; ln -s functions/pci_epf_test/func5 controllers/d800000.pcie-ep/; mkdir functions/pci_epf_test/func6; echo 0x104c > functions/pci_epf_test/func6/vendorid; echo 0xb00d > functions/pci_epf_test/func6/deviceid; echo 1 > functions/pci_epf_test/func6/msi_interrupts; echo 16 > functions/pci_epf_test/func6/msix_interrupts; ln -s functions/pci_epf_test/func6 controllers/d800000.pcie-ep/; echo 1 > controllers/d800000.pcie-ep/start; echo 1 > /sys/bus/pci/devices/0000:00:00.0/remove; echo 1 > /sys/bus/pci/rescan; Workaround for switch card: No workarounds available."

|

Issues closed in system firmware in this release
-------------------------------------------------

System firmware Known Issues
------------------------------

Change Requests
===============

SDK features descoped from 11.00 release
----------------------------------------
.. csv-table::
  :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
  :widths: 20, 90, 90, 20, 20

  JACINTOREQ-3987, "Linux SDK shall support ADC: 12-bit, 4MSPS analog to digital converter", "J784S4", 11.00.00, Descoped
  JACINTOREQ-5770, "U-Boot: support remoteproc load of HSM M4F core", "J722S", 11.00.00, 11.01.00

SDK features descoped from 10.01 release
----------------------------------------
.. csv-table::
  :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
  :widths: 20, 90, 90, 20, 20

  JACINTOREQ-5776 ,Linux Driver for GPMC - FPGA connection, "J722S", 10.01.00 , Dropped
  JACINTOREQ-5138 ,"Linux SDK shall support SA2UL: HMAC using MD5, SHA1, SHA2-224, SHA2-256 and SHA2-512", "J784S4, J721E, J721S2, J7200, J722S", 10.00.00 , 11.01.00
  JACINTOREQ-5529 ,Power Management support, "J722S", 10.01.00 ,11.01.00

SDK features descoped from 10.00 release
----------------------------------------
.. csv-table::
  :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
  :widths: 20, 90, 90, 20, 20

  JACINTOREQ-7514 ,Linux SDK shall support MSMC: Security Firewall, "J784S4", 10.00.00 ,10.01.00
  JACINTOREQ-5042 ,Linux SDK shall support cpufreq [opp] DFS, "J784S4, J721E, J721S2, J7200, J722S", 10.00.00 ,Dropped
  JACINTOREQ-4121 ,Support to boot MCU R5 1_1 in split mode, "J784S4, J721E, J721S2, J7200", 10.00.00 ,10.01.00

SDK features descoped from 9.2 release
--------------------------------------
.. csv-table::
  :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
  :widths: 20, 90, 90, 20, 20

  JACINTOREQ-3970 ,Linux SDK shall support MSMC: Security Firewall, "J784S4", 09.02.00 ,10.00.00
  JACINTOREQ-5042 ,AM69/J784S4 Linux SDK shall support cpufreq [opp], "AM69, J784S4", 09.02.00 ,10.00.00

SDK features scoped in 9.1 release
----------------------------------
.. csv-table::
  :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
  :widths: 20, 90, 90, 20, 20

   JACINTOREQ-3761 ,Linux SDK shall support RTI: Watchdog support J721S2, "J721S2", 09.02.00 ,09.01.00
   JACINTOREQ-3981 ,Linux SDK shall support RTI: Watchdog support J784S4, "J784S4", 09.02.00 ,09.01.00

SDK features descoped from 9.1 release
--------------------------------------
.. csv-table::
  :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
  :widths: 20, 90, 90, 20, 20

  JACINTOREQ-3970 ,Linux SDK shall support MSMC: Security Firewall, "J784S4", 09.01.00 ,09.02.00
  JACINTOREQ-3920 ,"Linux SDK shall support SA2UL: HMAC using MD5, SHA1, SHA2-224, SHA2-256 and SHA2-512", "J784S4", 09.01.00 ,09.02.00

SDK features descoped from 9.0 release
--------------------------------------
.. csv-table::
  :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
  :widths: 20, 90, 90, 20, 20

   JACINTOREQ-3598 ,Jacinto Device firewalling support, "J7200, J721e, J721s2, J784s4", 09.00.00 ,09.01.00

SDK features descoped from 8.6 release
--------------------------------------
.. csv-table::
  :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
  :widths: 20, 90, 90, 20, 20

   JACINTOREQ-5338 ,Jacinto PSDK 8.6 AEP/AHP industrial APL pull-in impact, "J721e, J7200, J721S2 , J784S4", 08.06.00 ,09.00.00


SDK features descoped from 8.5 release
--------------------------------------
.. csv-table::
  :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
  :widths: 20, 90, 90, 20, 20

   JACINTOREQ-5060, Jacinto networking requirements - CR to 8.6, "J721S2, J784S4", 08.05.00, 08.06.00
   JACINTOREQ-4991, "Jacinto Baseport, Graphics, Multimedia CR to 8.6", "J721S2, J784S4", 08.05.00, 08.06.00
   JACINTOREQ-4934, CSI Capture Automated Testing for J7AEP, J721S2, 08.05.00, 08.06.00
   JACINTOREQ-4928, J7AEP Multimedia Scope Modify, J721S2, 08.05.00, 08.06.00
   JACINTOREQ-5001, Configurable Buffering Descope, J784S4, 08.05.00, None
   JACINTOREQ-4993, Descope GLBenchmark, J784S4, 08.05.00, None
   JACINTOREQ-4927, J7AHP Graphics Scope Modify, J784S4, 08.05.00, 08.06.00

SDK features scope change for 8.5 release
-----------------------------------------
.. csv-table::
   :header: "ID", "Head Line", "Platform"
   :widths: 40, 60, 60

   JACINTOREQ-4994 , Video Codec Memory Optimization Scope Change, J721e

SDK features descoped from 8.4 release
--------------------------------------
.. csv-table::
   :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
   :widths: 20, 90, 90, 20, 20

   JACINTOREQ-4930 ,k3conf Doc and Test Modify, J721e, 08.04.00 ,08.05.00
   JACINTOREQ-4905 ,J7AEP Graphics Scope Modify, J721s2, 08.04.00 ,08.05.00/08.06.00
   JACINTOREQ-4898 ,SERDES: PCIe + USB schedule update, J721s2, 08.04.00 ,08.05.00
   JACINTOREQ-4864 ,4k Resolution Scope change, J721s2, 08.04.00 ,08.05.00
   JACINTOREQ-4854 ,McASP Scope Change, J721s2, 08.04.00 ,08.05.00
   JACINTOREQ-4930 ,k3conf Doc and Test Modify, J721s2, 08.04.00 ,08.05.00

SDK features descoped from 8.0 release
--------------------------------------
.. csv-table::
   :header: "ID", "Head Line", "Platform", "Original Fix Version", "New Fix Version"
   :widths: 20, 90, 90, 20, 20

    JACINTOREQ-1559 ,Linux H264 decoder support, J721e, 08.00.00 ,08.01.00
    JACINTOREQ-1485 ,Linux writeback pipeline support , J721e, 08.00.00 ,None
    JACINTOREQ-1444 ,Vision apps inclusion in yocto build  , J721e, 08.00.00 ,None


SDK features present in 7.0 that were descoped in 7.1
-----------------------------------------------------
.. csv-table::
   :header: "Feature", "Comments", "Platform"
   :widths: 40, 60, 60

    HS support,Restored in 7.3, J721e
    SPL/Uboot boot modes restricted to SD card boot mode,Restored in 7.3, J721e
    1s Linux boot, , "J721e"
    Descope for support of native H264 encode/decode,Use R5F based driver with OpenVX as interface.  H.264 decoder support restored in 7.3, J721e
    GPU compression, , J712e
    SA2UL driver optimization, , J721e
    Display Sharing,Display sharing demo available in SDK v6.1, J721e
    Virtualization (Jailhouse hypervisor/IPC virtualization/CPSW9G virtualization),Does not affect 3P virtualization solutions. Basic Jailhouse demo can be seen in SDK 7.0, J721e


Installation and Usage
======================

The :ref:`Software Developer's Guide <linux-index>` provides instructions on how to setup your Linux development environment, install the SDK and start your development. It also includes User's Guides for various Example Applications.

|

Host Support
============

For the specific supported hosts for current SDK, see :ref:`this page <how-to-build-a-ubuntu-linux-host-under-vmware>`.

.. note::
   Processor SDK Installer is 64-bit, and installs only on 64-bit host machine.

.. |reg| unicode:: U+00AE .. REGISTERED SIGN

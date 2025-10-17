====================================
Building Debian Images Using Armbian
====================================

Introduction
============

Texas Instruments uses the **Armbian** build framework to generate Debian images for its platforms.
Armbian describes itself to be a "base operating system"; that is, a build framework used to build
Linux images optimized for Single-Board Computers.

|__SDK_DOWNLOAD_URL__| provides Debian images, but users can also build these, especially if users
require something custom (such as different kernel configurations or default desktop environments).

Armbian Usage
=============

This document provides high-level information about how to build Debian images for TI platforms,
using Armbian. For a full list of options available for users to configure these images at build
time, see `Armbian Documentation <https://docs.armbian.com/>`__.

Get Armbian
-----------

For the time being, `TI's fork <https://github.com/TexasInstruments/armbian-build.git>`__ of
`Armbian/build <https://github.com/armbian/build.git>`__ maintains support for TI platforms.
Therefore, the first step is to fetch TI's fork:

.. code-block:: console

   git clone https://github.com/TexasInstruments/armbian-build.git

Repository Structure
--------------------

The below files and directories are relevant to this high-level overview:

-  :file:`config/`: This directory has configurations for boards, families, kernel configurations,
   desktop or CLI environments and so on. To find configuration files relevant to TI, see:

   - :file:`config/boards/<TI EVM board>.conf`
   - :file:`config/sources/families/k3.conf`
   - :file:`config/kernel/linux-k3-current.conf`
   - :file:`config/kernel/linux-k3-rt-current.conf`

-  :file:`compile.sh`: This is the script that the user should run for building Armbian images.

-  :file:`lib/`: This directory stores the scripts that do most of the work in building Armbian images.

-  :file:`extensions/`: This directory has files that define **extension hooks**. In Armbian, extension
   hooks are function signatures, which the build framework calls in the process of building an
   image. However, the build framework does not define these in ``lib/``. Users can define these
   functions and integrate custom steps in the build process. TI has ``extensions/ti-debpkgs.sh``
   extension file. To customize the build process, create a new file in this directory, and define
   your extension hooks there. Once the file is created, be sure to add the following line to
   board/family config file:

   .. code-block:: console

      enable_extension <extension_name>

-  :file:`userpatches/`: This directory stores files that define build parameters, user patches and so on.

Building Images
---------------

Armbian supports both an interactive UI and a non-interactive build process.

-  To build interactively:

   .. code-block:: console

      ./compile.sh

   The build framework will then display dialog boxes. The user can use this to select the board, CLI
   or desktop environment, kernel configurations and so on.

-  To build non-interactively:

   .. code-block:: console

      ./compile.sh [command] [switch...] [command...]

   A full list of build switches is available at `Build Switches <https://docs.armbian.com/Developer-Guide_Build-Switches/>`__.

   .. warning::

      If build issues arise, try adding these build switches to the end of the build command:

      .. code-block:: console

         GIT_SKIP_SUBMODULES=yes SKIP_ARMBIAN_REPO=yes

   For example, the following command builds the minimal non-RT Trixie image:

   .. code-block:: console

      ./compile.sh build BOARD=<board> BRANCH=current BUILD_MINIMAL=yes KERNEL_CONFIGURE=no RELEASE=trixie GIT_SKIP_SUBMODULES=yes SKIP_ARMBIAN_REPO=yes

For a list of boards corresponding to each SoC, refer:

   .. csv-table::
      :header: "SoC", "Board", "Board Config File"

      AM62Lx,am62lxx-evm,``config/boards/am62lxx-evm.conf``
      AM62Px,am62pxx-evm,``config/boards/am62pxx-evm.conf``
      AM62x,sk-am62b,``config/boards/sk-am62b.conf``
      AM62-LP,sk-am62-lp,``config/boards/sk-am62-lp.conf``
      AM62SIP,sk-am62-sip,``config/boards/sk-am62-sip.conf``
      AM64x,sk-am64b,``config/boards/sk-am64b.conf``


``output/images/`` stores the built images. These images have a ``.img`` extension.

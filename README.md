# device/lge/mako-kernel
Nexus 4 (mako) kernel

## How to build locally?

### Download the projects

```bash
# Download the prebuilt toolchain
$ git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/arm/arm-eabi-4.6

# Download the kernel source
$ git clone -b mako-3.4-marshmallow git@git.aospa.co/AOSPA/android_kernel_msm.git kernel
```

### Build the projects

```bash
# Ensure the toolchain is available for building
$ export PATH=$(pwd)/arm-eabi-4.6/bin:$PATH

# Set the standard pre-requisite values
$ export ARCH=arm
$ export SUBARCH=arm
$ export CROSS_COMPILE=arm-eabi-

# Let the makefiles do their thing
$ cd kernel
$ make mako_defconfig
$ make
$ cd ..

# Replace the old prebuilt kernel with the newly built one
$ cp kernel/arch/arm/boot/zImage device/lge/mako-kernel/kernel
```

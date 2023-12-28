# OpenRage
- Runtime files (art)
- Many tools/libraries, etc (external)
- Currently only has opengl testing/basic tools (frameworks)
- Linux kernel for Android (kernel)
- Core Library for C library (libcore)
- More tools including gdbserver for remote debugging (prebuilts)
- SE policy including (system)
- fat32 and Gradle build config (tools) 


Open Source Code_VR-1541F_M31
1.6 GB -> 2.6 GB when extracted
V3.0
24 Oct 2018

~~~Here are instructions for building the kernel.

First, get the Android NDK from https://developer.android.com/ndk/downloads/
This is for the compiler prebuilts.
Unzip the downloaded archive into some directory. Let NDK be this directory.

Set environment variables:
export CROSS_COMPILE=aarch64-linux-android-
export ARCH=arm64
PATH=$PATH:$NDK/toolchains/aarch64-linux-android-4.9/prebuilt/linux-x86_64/bin

Make your output directory:
mkdir -p out/daydreamos-msm-vega-4.4/msm-google-dd

Build:
cd kernel/msm-google-dd
make O=../../out/daydreamos-msm-vega-4.4/msm-google-dd/ mrproper
make O=../../out/daydreamos-msm-vega-4.4/msm-google-dd/ vega_defconfig
make O=../../out/daydreamos-msm-vega-4.4/msm-google-dd/ prepare
make O=../../out/daydreamos-msm-vega-4.4/msm-google-dd/ -j32 ~~~
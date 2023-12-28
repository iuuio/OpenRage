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

_Code is from lenovo's driver support site for the Mirage Solo, info and readme is forked from NightGaunt_

The general thread for the rebuild of the Lenovo Mirage Solo OS. This project will rebuild Google's abandoned Daydream platform into a full VR Native Linux Kernel.

Project Goals: To take the fantastic piece of hardware that is the Lenovo Mirage Solo, and make it a working platform for future VR endeavors. The google implimentation was fairly limited before google dropped the Daydream VR platform entirely, and now many apps will never update, and may be otherwise discontinued. It is the goal of this project to make the settings more useful, remove restrictions arbitrarily placed on the device (such as disabling FTP over USB), update the code base to something that can be programmed for once more, and encourage others to program for this device.

Assuming we manage these goals, this project will then focus on building better infrastructure support, either by retooling the base of the Daydream project for all daydream compatable devices (and hopefully newer capable devices), or possibly branching the project into a non-android bound full Linux desktop environment that will be native to VR.

Lenovo and Google have both been less than helpful in this endeavor. Someone has reached the Google team, who stated that they can't give out Lenovo's proprietary data, and any lead into Lenovo has run dry. If anyone in either of these teams would like to assist, we would gladly accept the help. This would improve customer relations, as this project being nescessary is a stain on both companies records.

Current Status: https://bit.ly/2TDUg1R contains a list of intended repairs to the existing platform, and improvements we hope to accomplish. This list is expandable, so if you have additions, please pm me. We have a discord channel for discussing live, and several devs trying to get deep root on the device. PM for channel access.
~~~
Here are instructions for building the kernel.

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
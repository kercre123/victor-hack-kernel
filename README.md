# victor-hack-kernel

This kernel has been edited to use RX1/TX1 (BLSP1_UART1) for spine communication instead of RX2/TX2 (BLSP1_UART2) for specific edge cases where you can't use UART2.

The main files that have been edited are at /arch/arm/boot/dts/qcom/anki*.dtsi

NOTE: This will only work on a DVT (Whiskey DVT1, Victor P1-3, Victor DVT1-4) prototype bot which has an ABOOT that doesn't check for a boot signature. If you run this on a newer bot and the bot bricks, that is your problem.

Build instructions:

`docker run -it vaddio/yocto-16.04:16.04-latest /bin/bash`

`chmod 0777 . && su builduser`

`curl https://anki-vic-pubfiles.anki.com/license/prod/1.0.0/licences/OStarball.v160.tgz | tar -xz`

`rm -rf ~/opensource/kernel/msm-3.18/*`

`cd ~/opensource/kernel/msm-3.18/`

`git pull https://github.com/kercre123/victor-hack-kernel.git`

`cd opensource/poky/build && source conf/set_bb_env.sh`

`bitbake linux-quic`

The kernel will be built in ~/opensource/poky/build/tmp-glibc/deploy/images/apq8009-robot-robot/zImage-dtb-apq8009-anki.bin

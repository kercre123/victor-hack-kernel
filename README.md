# victor-hack-kernel

This kernel will be edited to use RX1/TX1 (BLSP1_UART1) for spine communication instead of RX2/TX2 (BLSP1_UART2) for specific edge cases where you can't use UART2.

The main goal is to disable the original spine serial, and put UART2 at a ttyHS*.

The main files that will need editing are at /arch/arm/boot/dts/qcom/anki*.dtsi

I hardly have any clue what I'm doing, so this will probably end up getting a lot of commits.
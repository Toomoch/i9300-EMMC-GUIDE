First of all you need to have: 

* a micro sd card (minimum 1GB) 

* a linux-based distro - debian based recommended like Ubuntu 18.04 (a VM works also if you passthrough the usb device)

Follow this instructions when you have the stuff listed above:

* Install these packages :

`sudo apt install python3 python3-libusb1 libusb-1.0-0 gcc-arm-none-eabi binutils-arm-none-eabi build-essential`

* Download this repo as zip and extract it to your home folder.

* Run this command inside it: `make -C shellcode`

Then [download](https://mega.nz/#!L0Z1EAII!Q-xYAevmKMALgI73bZeW44Fzrstbgs7A-1_5QwCf9XM) a good EMMC firmware (also refeered to as 0xf7)(bad is 0xf1) and place it in the `i9300_emmc_toolbox` folder.

You should also download the [SBOOT Bootloader version XXELLA Firmware](https://mega.nz/#!rl5QQQSY!w26-LZrzB0wSkQrDGbSYHiF36ynOF2FQCftfxjW4C_Q) (extract the sboot.bin file from the .tar and put it inside `i9300_emmc_toolbox-master/sdcard`)

Get also this file (`GT_I9300_unbrick_sdcard_head.bin`) [sd recovery image](https://mega.nz/#!LkoHkAhY!EgndxyL-tDE50RWx9Sx4io5Lu-oe7rXimk0Dt9Q_7xA)

Please follow the according guide for your type of brick:

[Type 1 Brick procedure](Type-1-Brick)

[Type 2 Brick procedure](Type-2-Brick)

[Type 3 Brick procedure](Type-3-Brick)

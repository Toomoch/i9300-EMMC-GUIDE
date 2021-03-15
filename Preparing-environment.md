First of all you need to have: 

* A micro SD card (minimum 2GB) 

* A computer with Windows 10 (7 and 8 should work, not tested through) or linux-based distro - debian based recommended like Ubuntu (a VM works also if you passthrough the usb device)

Follow this inctructions no matter what os you use:

1. [Download the lastest release (click on "i9300_emmc_toolbox.zip") and extract it.](https://github.com/Toomoch/i9300-emmc-guide/releases)

2. You should also download the [XXELLA Firmware](https://mega.nz/#!rl5QQQSY!w26-LZrzB0wSkQrDGbSYHiF36ynOF2FQCftfxjW4C_Q) [(mirror)](https://drive.google.com/file/d/1eU1JkLVOHHqa8WNxjTUY22u7_Y0wBACo/view?usp=sharing)

Follow this instructions depending on your OS:

* **For Linux** install these packages : `sudo apt install python3 python3-libusb1 libusb-1.0-0 gcc-arm-none-eabi binutils-arm-none-eabi build-essential`

* **For Windows**: [Download and install balenaEtcher](https://www.balena.io/etcher/). [Download the lastest Python3 version and install it **making sure to select add to path**](https://www.python.org/downloads/). [Download the Samsung usb drivers](https://developer.samsung.com/galaxy/others/android-usb-driver-for-windows) and install them. [Download the lastest zadig version](https://zadig.akeo.ie/) and run it. Click on "option" at the top and enable "List All Devices". Search for your phone on the device list (for me it was gadget serial, maybe it's something like samsung or android), select it, then cycle the arrows until you see libusbK (v3.0.7.0) in the text box (IMPORTANT!) and click on replace driver.
Open a command prompt and enter this: `pip install libusb1`.


**Next step: [Determining your type of brick](Determining-your-type-of-brick.md)**

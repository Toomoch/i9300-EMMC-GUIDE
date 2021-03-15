Use Odin in the Odin_3.10.0 folder to flash the XXELLA Firmware from the .tar.md5 that you downloaded. **To get Odin to list the phone again, you have to open the device-manager and under the section "libusbK devices" update the driver to the "SAMSUNG Mobile USB CDC Composite Device" one**. Open Odin3 v3.10.0.exe, then check the Re-partition option. In PIT select the **GT-I9300.pit** file in the Odin_3.10.0 folder and in AP select the XXELLA FIRMWARE file (**KIES_HOME_I9300XXELLA_I9300OXAELLA_742798_REV00_user_low_ship.tar.md5**). Afterwards, flash [TWRP](https://dl.twrp.me/i9300/) (use the lastest .tar and flash it as AP in Odin). Boot into TWRP and then go to Advanced, then Terminal, and write the following commands: 

`make_ext4fs dev/block/mmcblk0p3`

`make_ext4fs dev/block/mmcblk0p8`

`make_ext4fs dev/block/mmcblk0p10`

`make_ext4fs dev/block/mmcblk0p12`

Your phone should boot now! Sadly EFS is missing now, if you have a backup restore it with TWRP.

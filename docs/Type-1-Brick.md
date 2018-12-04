Plug your microsd card to your linux computer

Run the following commands and replace YOURMICROSD with your microsd’s mountpoint (you can view it with gparted)

`$ cd sdcard`

`$ ./create_recovery_sdcard.py -o recovery_sdcard.bin -s sboot.bin`

`$ dd if=recovery_sdcard.bin of=YOURMICROSD`

`$ sync`

Now we have to enter download mode:

1. Insert the SD card to your device, insert the battery, press power+volume down+home buttons for approx. 2-3 seconds, release all of them and press the volume up button once. You might see some funky stuff on the phone's screen -- just ignore it.

2. Connect the usb cable.

3. Run the following command in order to low-level format the eMMC and install the new firmware: `exploit/sboot_exploit.py --shellcode shellcode/write_fw.bin -e 0xf7bugfree.bin`

4. Boot again to download mode and connect the usb cable.

5. Resize the boot partition: `exploit/sboot_exploit.py --shellcode shellcode/change_boot_partition_size.bin`

6. Creating the recovery sd card

> 1) Insert SD card (Everything from it will be wiped!)
> 2) Perform on the directory of this file: _GT_I9300_unbrick_sdcard_head.bin_ `dd if=GT_I9300_unbrick_sdcard_head.bin of=/dev/path to SD card device (mountpoint on gparted)`

eMMC is functional! You can use [Odin](https://forum.xda-developers.com/attachment.php?attachmentid=2404381&d=1384962652) to flash the ROM from the .tar.md5 that you downloaded to your device (you also need to repartition, i.e. flash a [new PIT](https://forum.xda-developers.com/attachment.php?attachmentid=2404381&d=1384962652)). Afterwards, flash TWRP and format these partitions to ext4 (/cache, /data, /preload, /sdcard, /efs). Then flash some firmware and your phone is good to go (except for EFS which is missing now).
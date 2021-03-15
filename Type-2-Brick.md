Insert the micro SD card into your computer. We're going to create the **SBOOT SD card**.

**For Linux** run the following commands and replace YOURMICROSD with your SD card mountpoint:

* `cd sdcard`

* `sudo dd if=sbootsdcard.bin of=YOURMICROSD`

* `cd -`

**For Windows** double click on "OpenCommandPromptHere.cmd" then do/type the following:

* Open balenaEtcher, select "sbootsdcard.bin" as the image from the i9300_emmc_toolbox/sdcard folder, select your SD card as the drive and click flash.

**Now do the following:**

1. **DON'T** Insert the **SBOOT SD card** to your device, insert the battery, press power+volume down+home buttons for approx. 2-3 seconds, release all of them and press the volume up button once. 

2. Connect the usb cable.

3. Run the following command in order to low-level format the eMMC and install the new firmware: 
 **Linux**:`exploit/sboot_exploit.py --shellcode shellcode/write_fw.bin -e 0xf7bugfree.bin`
 **Windows**:`python exploit/sboot_exploit.py --shellcode shellcode/write_fw.bin -e 0xf7bugfree.bin`  
 **If it fails, check [here](https://theandroid02.github.io/i9300-EMMC-GUIDE/Troubleshooting)**
 


4. **INSERT THE SBOOT SD card** and boot again to download mode and connect the usb cable. You might see some funky stuff on the phone's screen -- just ignore it.

5. Resize the boot partition:  
**Linux**:`exploit/sboot_exploit.py --shellcode shellcode/change_boot_partition_size.bin`
**Windows**:`python exploit/sboot_exploit.py --shellcode shellcode/change_boot_partition_size.bin`

6. Insert the micro SD card into your computer. We're going to create the **RECOVERY SD card**:
**Windows**: Open balenaEtcher, select "RECOVERYSDCARD.bin" as the image from the "i9300_emmc_toolbox" folder, select your SD card as the drive and click flash. 
**Linux**: Perform on the directory "i9300_emmc_toolbox" `dd if=RECOVERYSDCARD.bin of=/dev/path to SD card device (mountpoint on gparted)`.

7. Put the **RECOVERY SD card** in your phone. Then boot it normally. A screen with SDCARD MODE should appear. When it's done take the battery out.

eMMC is functional! Now go to [reinstalling Android](Reinstalling-Android.md)

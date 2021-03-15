**Basic explanation of how it works:**

Samsung devices from 2012 that contained the Exynos 4412 SoC (n7100, i9300, i9305, n7105) and had a certain model of EMMC, 
had a bug in the EMMC firmware that corrupted the data on the chip. 

If the boot partition is intact, it will still show the bootloader screen (samsung logo with the model number) and will be able to boot in download mode, but, if the boot partition is corrupted, it won't boot at all.

When the Exynos 4412 boots, it first looks for the EMMC boot partition. If it isn't there it will boot from the SDcard. 

We can use that to our advantage and boot the Samsung bootloader into download mode from an SDcard (or just boot into download mode normally if the boot partition is intact).
Then we exploit the bootloader to dump the EMMC firmware and write the patched one
and finally reformat the EMMC. Finally we make another SDcard that automatically restores the boot partition and our device is fixed.

The problem is that the exploit only works in some bootloader versions. If the boot partition is gone, we can boot any version, like a vulnerable one. But if it's intact we'll still boot from EMMC and therefore boot the version that's installed. If
the bootloader is incompatible, there's still one way. We can force SD booting by shorting a resistor on the motherboard.

**Please read this so you know what you'll are doing. If you want, watch [Oranav's presentation](https://www.youtube.com/watch?v=OY7OlY0OW2Q)**

**Next step: [Preparing environment](Preparing-environment.md)**

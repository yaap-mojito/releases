# YAAP releases for mojito

#### Maintainer(s)

- cyberknight777

#### Build flavor

- YAAP HOMEMADE with updatepackage.
- YAAP GAPPS with updatepackage.

#### Instructions

- Boot to bootloader.
- Run `fastboot --skip-reboot update yaap.zip`.
- Run `fastboot getvar current-slot`.
- If it says a, run `fastboot --set-active=b`.
- If it says b, run `fastboot --set-active=a`.
- Run `fastboot reboot bootloader`
- Run `fastboot --skip-reboot update yaap.zip`
- Unzip the recommended fw.
- Open a terminal inside the firmware-update directory.
- Flash all .img files with the command syntax being `fastboot flash --slot=all partition partition.img`.
- An example of such can be `fastboot flash --slot=all abl abl.img`.
- Run `fastboot reboot recovery`.
- Format data with the recovery.
- Reboot to system.

#### FAQ

Why is the flashing process complex?

- It is simpler than you think it is and flashes in barely 3 minutes per slot.

Will YAAP be maintained officially?

- That is still undecided at the moment, if any of us gets a permanent solution to be able to consistently build YAAP, then we will apply for official.

Will we get OTA support?

- OTA support requires building the ROM as an otapackage and we don't intend to move to otapackage.

Can I change kernel?

- No. You are not allowed to change to any other kernel. Doing so has a possibility to render your phone in a soft brick or will cause problems with storage. Alternatively, you can flash a newer kernel build than what is provided.

Can I change recovery to TWRP or OFOX?

- No. Doing that effectively puts you in our ignore list if you were to face bugs.

Can I flash GAPPS in homemade build?

- No. The rom has gmscompat inbuilt. Flashing gapps effectively puts you in our ignore list if you were to face bugs.

What is gmscompat?

- https://grapheneos.org/features#sandboxed-google-play

Can you build MiCamera in the ROM?

- No. You can use custom mods out there for it. We will not build it in the ROM.

Can I flash DFE?

- No. Read [this](https://kubersharma001.com/reasons-to-stay-encrypted-on-android-and-the-risks-otherwise) to know why.

Can I make a feature request?

- No. We do not accept feature requests.

How to report bugs?

- Grab dmesg and logcat then open an issue in this repo and send it there.

Does SafetyNet pass out-of-the-box in homemade builds?

- No. It requires gapps to be privileged.

What to do if it fails to flash?

- Install proper USB drivers from [here](https://developer.android.com/studio/run/win-usb) and get platform-tools from [here](https://developer.android.com/studio/releases/platform-tools).

How to flash magisk?

- Extract the ROM zip, patch the boot.img with Magisk and flash it in fastbootd with the command `fastboot flash --slot=all boot boot.img`.

Is this a gaming ROM?

- Yes.

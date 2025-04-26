# how to install a custom rom for oneplus 7T, or other oneplus devices out there (this guide might work on other phones too, but be careful)

## unlock the bootloader first:

1): go in android, settings, about device and press on Build Number until it says that you have activated developer options
2): find developer options, and enable usb debugging
3): connect your phone to your pc using a cable
4): allow usb debugging from the prompt that appeared on your phone

### boot into bootloader:
1): install platform-tools from https://developer.android.com/tools/releases/platform-tools
2): extract the platform-tools.zip file you downloaded
3): open a command prompt/terminal in the platform tools folder
4): write in adb devices and see if your device shows up, if it does, proceed to the next step

5): reboot into bootloader:

```cmd
adb reboot bootloader
```

### unlock the bootloader:

> (optional) you can also check if your device shows up in `fastboot devices`

```cmd
fastboot flashing unlock
```

### flashing custom rom:

> the last step

find TWRP recovery for your device, drag the recovery-image-name.img file into the platform-tools folder and then run in the terminal:

> replace `recovery-image-name` to the name of the recovery image

```cmd
fastboot boot recovery-image-name.img
```

once you're in twrp, go `Advanced` --> `ADB Sideload` --> `Wipe Dalvik Cache` `Wipe Cache` --> `Swipe to Start Sideload`

> drag the custom rom (.zip) into the platform tools folder

go back to your terminal, and type:

> replace custom-rom with the name your custom rom (.zip) file is named

```cmd
adb sideload custom-rom.zip
```

### reboot to system:
after the sideload is done without any errors, you can click "Reboot"


### and your done

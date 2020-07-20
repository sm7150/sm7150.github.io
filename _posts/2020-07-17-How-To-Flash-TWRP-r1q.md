---
  layout              : article
  aside               :
    toc               : true
  title               : How to flash TWRP for r1q (Android 10)?
  tags                : 
    - Introduce
    - Newbie
  categories          : 
  author              : firemax13
  show_author_profile : true
---
![Imgur](https://i.imgur.com/s3rNVao.png)

## A. What do you need?
- Samsung Galaxy A80 device
- USB Cable
- Laptop/PC/Computer (Windows OS)
- ADB platform tool must be installed
- Internet
- Brain
- Patience and Knowledge

## B. Tools to Download
- [OdinFlashTool](https://odindownloader.com/category/download)
- [SamsungDriver](https://samsungusbdriver.com/category/download)
- [SamFirmTool](https://samfirmtool.com/category/tool)
- [ADBinstaller](https://forum.xda-developers.com/attachment.php?attachmentid=4623157&d=1540039037)
- [GoogleADBplatformTool](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)

## C. Files to Download
- [vbmeta_disabler](https://drive.google.com/file/d/1_Ws71h--Z7YBGfllsbt8qlJElXRxTB1p/view)
- [TWRPRecovery](https://drive.google.com/file/d/1FkYQY_O7daPFX6lWt66Bn-aXadRrDWez/view)
- [DM-Verity-Quota-Encryption_Disabler](https://zackptg5.com/downloads/Disable_Dm-Verity_ForceEncrypt_03.04.2020.zip)

## D. Sources
- [blackbuga_twrp-thread](https://forum.xda-developers.com/galaxy-a80/development/recovery-twrp-galaxy-a80-t4000729)
- Thanks to [blackbuga](https://forum.xda-developers.com/member.php?u=7319000) for making this working twrp
- [BK_unlocking-steps_thread](https://forum.xda-developers.com/galaxy-a80/how-to/galaxy-a80-flash-official-firmware-root-t4029833)
- Thanks to this guy [BK](https://forum.xda-developers.com/member.php?u=9402185) who provide steps to unlock device
- [DM-Verity-Quota-Encryption_Disabler(THREAD)](https://forum.xda-developers.com/android/software/universal-dm-verity-forceencrypt-t3817389)
- Thanks to this guy [Zackptg5](https://forum.xda-developers.com/member.php?u=6037748) who provided this awesome tool
- [ADBinstaller_THREAD](https://forum.xda-developers.com/showthread.php?t=2588979)
- Thanks to this guy [Snoop05](https://forum.xda-developers.com/member.php?u=4638083) who provided easy ADB installer

## First Movement
#### A. Set up (Needed to-do before go)
- Make sure your windows is already have Samsung Driver Installed, and recognize in Storage and ADB.
- Make sure you downloaded the stock firmware of your device if flashing fail.
- Back-up first!
- Make sure you are already unlocked bootloader if not refer [here](https://forum.xda-developers.com/galaxy-a80/how-to/galaxy-a80-flash-official-firmware-root-t4029833).
#### B. Flash Custom Binary
- Connect your phone into your Computer using your USB Cable then while your screen is turned on reboot into Download Mode just hold power button with volume down button
after screen turned off fastly/quickly hold the volume up button (suppose after screen turned off you need to hold all button). Volume up to proceed into download mode.
- In your computer, launch Odin Flash Tool as "Administrator", and click "ok" on warning message. In Odin Head to the tab named "option" and uncheck "Auto-Reboot" option.
- Now you need to put the custom binary named "vbmeta_disabler" into the "AP" slot/tab area. Click the "AP" option and find the file then confirm it.
- Make sure the Odin recognise your device, and make sure your device is connected to the computer. 
- Now hit "start" in the Odin to start flashing it, it will only take a few seconds.
- After you flashed it, Reboot into download mode again just hold power button with volume down button
after screen turned off fastly/quickly hold the volume up button (suppose after screen turned off you need to hold all button). Volume up to proceed into download mode.
- Don't do anything, keep your device in download mode while its connected at your computer. Proceed into the next steps.
#### C. Flash TWRP Recovery
- After you downloaded the TWRP Recovery Image in ".zip" format, you need to extract it after that you need to repack it as a ".tar" extension (eg. recovery.tar).
- There must be only one file inside of "recovery.tar" (recovery.img).
- In Odin you can find option at the below named "Reset", click that one to reset the progress. In Odin Head to the tab named "option" and uncheck "Auto-Reboot" "Re-Partition" option.
- Now you need to put the "recovery.tar" (TWRPIMAGE) in the "AP" slot/tab just click that one find the file and confirm it.
- Click "Start" option to start flashing the TWRP Recovery. It will take some few seconds to flash it.
- After you flashed it, reboot into TWRP Recovery just hold power and volume down when the screen is turned off quickly release the volume down and quickly hold volume up (Volume up and Power button must be hold after screen turned off).
- BOOM YOU SUCCESFULLY FLASHED TWRP! Stay on your TWRP Recovery screen, and follow the next instructions.
#### D. Disable any device options
(Since you can't use the device storage because of the encryption and the file is showing encryptical you need to disable those in-order to use the device storage)
(MTP is currently not working because of the kernel bug and problem. You need to ADB Sideload it)
- While in your TWRP Recovery, head into "WIPE" option and proceed to "FORMAT DATA" to decrypt the storage and the encryption.
- After you FORMAT you DATA, proceed to reboot into TWRP Recovery again to use the DATA storage. Stay on your TWRP Recovery.
- Connect your Device into your Computer using your USB Cable, make sure ADB is already installed in your WINDOWS.
- In your Windows, find the ADB folder and run the CMD in that folder as "ADMINISTRATOR".
- Now you need to recognise if your device is connected and recovery ADB is connected too. Just type the ff. in the CMD:
```
adb devices
```
- If your serial number is showed and it also showed "Authorized" then proceed to sideload the DM-VERITY-QUOTA-ENCRYPTION_DISABLER.
- While your Device is in the Recovery Mode (TWRP), head into "ADVANCED" tab, and head into "ADB SIDELOAD" option. Check the two checkboxes "Wipe" "DALVIK & CACHE". Then swipe to start ADB Sideloading.
- In CMD of your Computer you need to sideload the DM-VERITY-QUOTA-ENCRYPTION_DISABLER file. Just ff. the command:
```
adb sideload <the_location_of_the_disabler-file>
```
Example:
```
adb sideload C:/firemax13/DM-VERITY-QUOTA-ENCRYPTION_DISABLER.zip
```
- In your TWRP Recovery Terminal, follow the instruction of the disabler, Volume up for "YES" and Volume down for "NO". After of the button mapping.
- You need to "YES" all the prompt of the disabler, "YES" to disable "QUOTA", "DM-VERITY" & "ENCRYPTION".
- After you successfully disable all things, just reboot into your System (Don't wipe anything after flashed and disabled).
- Set-up your device, and BOOM! you are good! You can also flash anything now, just put it in your device storage and reboot into TWRP Recovery and flash it.









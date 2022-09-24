# How to force enable VoLTE / VoWiFi on Android

### Source: https://forum.xda-developers.com/t/guide-activate-volte-vowifi-oos-11-ob1-ob2.4223967/

## Pre-requisite

    - Download ADB from https://developer.android.com/studio/releases/platform-tools
    - Save the ADB folder in the same directory as this README.md
    - Install QUD.WIN.1.1+Installer-10037.3+Setup.exe which containes the Qualcomm drivers

## Steps below are specific for Oneplus (tested on OnePlus 7 Pro, Firdaus)

## Following steps are to be perform on device in order

1. Install EngineeringMode.apk and OEMLogKit.apk
2. Dial "*#800#" to open OnePlusLogKit
3. Click on "Function Switch"
4. Enable the following
    - VoLTE switch
    - VoWifi switch
    - VT switch
5. Dial "*#801#"
6. Open "EngineerMode" with "Just once" (This will enable USB debugging)
7. Turn on "Rndis, diag switch"
8. Turn on "Engineer Mode Toggle"

## Following steps are to be perform on computer in order

1. Open the "Mi11-UltraMBN\configs\mcfg_sw\generic" folder
2. Select the desired network provider (SEA for South East Asia)
3. Open Terminal/PowerShell/CMD from the "EfsTools-0.10-modded-1.2-win32" folder
    - Make sure the terminal indicates that you're in the EfsTools folder
    - Output will show something like below (example from PowerShell)
        - PS D:EfsTools-0.10-modded-1.2-win32>
4. Run ".\EfsTools.exe efsInfo"
    - Output will show something like,
        - Use serial port 'COM5' (Port number may change automatically)
        - Version: 1, MaxDirectories: 50, MapPathnameLength: 1024, MaxFileSize: 0, MaxFilenameLength: 768, MaxMounts: 36, MaxSymlinkDepth: 0
5. Run ".\run-efs-part-1.ps1"
    - Output should be,
        - Use serial port 'COM5'
        - Use serial port 'COM5'
6. Run ".\run-efs-part-2.ps1"
    - Output will be a stream of text with no errors
7. Restart phone (can also be done via adb with "adb reboot" command)

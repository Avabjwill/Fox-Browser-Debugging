# Fox Mobile Browser
This document describes how to debug your Fox Mobile Browser Experience. 

## TABLE OF CONTENTS

- [Connecting to your device](###connecting-to-your-device)
- [Use bmgr to Initiate Backup and Restore Operations](###use-bgmr-to-initiate-backup-and-restore-operation)
- [Enable Wi-Fi Debugging](###enable-wifi-debugging)

# Debug Your Browser Content

### Connecting to Your Device

Before debugging you must connect to your device through Wifi.

To test and debug your Fox Browser content you must use Fox Developer Hub, which has tools to setup your device.

### Use bmgr to Initiate Backup and Restore Operations
Use bmgr to initiate backup and restore operations from your PC unto your browser. During a backup operation, the service queries your app for backup data then archives the data. During a restore operation, the backup manager service retrieves the backup data and restores the data to the device.

To do that,
- open a terminal or Windows command prompt window and run the following command: 

```sh
adb shell bmgr list 
```

### Enable Wi-Fi Debugging

To set up Wi-Fi debugging:

- Make sure that your android device and your host computer are connected on the same network then you will be able to debug your browser.
- Install **[Android Platform Tools](https://developer.android.com/studio/command-line/adb)(adb)**
- Open a terminal or Windows command prompt window.
- Locate the adb tool if it is not automatically prompted. On Windows, it is typically located in C:\Users\{user}\AppData\Local\Android\sdk. 

Then, use the following -command to determine the IP address for the device:
```sh
adb shell ip route
```
*The output should look like this:*

```10.0.30.0/20 dev wlan0
kernel  scope link  
src 10.0.31.101```

The IP address of the device follows src. Using the IP address and port 8000, issue the following commands:

```sh
adb tcpip 0000
adb connect *<ipaddress>*:0000
```

The android device can now be disconnected from the USB port. 

To stop using the Wi-Fi connection, issue the following ADB command from the OS shell:
 
``` sh
adb disconnect
```

The information on this page is applicable for debugging Fox Mobile Browser.

###### This is Proprietory Information that is Protected by EULA agreement

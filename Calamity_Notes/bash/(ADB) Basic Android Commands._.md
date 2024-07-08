---
aliases:
  - "(ADB) Basic Android Commands. "
tags:
  - Keep/Label/android
---

Short Descirption: This is some basic commands you can use with android command line and ADB (Android Data Bridge) that will be useful 

//List installed packages: 
adb shell pm list packages


//stop installed packages (force) 
adb shell am force-stop {package_name}


//kill qt  and launcher 
su root
killall -9 com.dish.atv.launcher

---
aliases:
  - (Bluetooth) (Android) General Call Tree and File locations
tags:
  - Keep/Label/android
  - Keep/Label/bluetooth
---

Short Description : General Idea of where to look when debugging Bluetooth issues. 



For integrating a new Bluetooth chip with a custom HAL and ensuring compatibility with the Android Bluetooth stack, here are the key AOSP files (or types of files) you should look at, in order:

Bluetooth HAL Interface Definitions
--------------------------------------------------------------
hardware/interfaces/bluetooth/1.0/I*.hal


Your Custom HAL Implementation
------------------------------------------------------------------
hardware/interfaces/bluetooth/1.0/YourCustomHalImplementation.cpp (This is hypothetical; actual path depends on where you place your implementation.)


Bluetooth JNI Files (For bridging Java and native code)
------------------------------------------------------------------------------------------
frameworks/base/core/java/android/bluetooth/BluetoothAdapter.java
frameworks/base/core/jni/android_bluetooth_BluetoothAdapter.cpp


Native Bluetooth Stack (Fluoride) Implementation
---------------------------------------------------------------------------------
system/bt/main.cpp
system/bt/stack/* (Relevant C/C++ files for stack functionalities)


Bluetooth Framework Layer (Java API Implementation)
------------------------------------------------------------------------------------------
frameworks/base/core/java/android/bluetooth/BluetoothDevice.java
frameworks/base/services/core/java/com/android/server/bluetooth/*


Bluetooth System Service
-------------------------------------------------------------
frameworks/base/services/core/java/com/android/server/bluetooth/BluetoothManagerService.java


Application Layer Example (Using Bluetooth API)
--------------------------------------------------------------------------------
Any application source file that makes use of the Bluetooth APIs, typically found in:
packages/apps/YourBluetoothApp/src/YourActivity.java

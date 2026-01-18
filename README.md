# DG-Backup-tool
DG Backup Tool is a one-click Android backup and redundancy solution that securely backs up an Android device to a PC and later replicates only changed data to an external HDD. By maintaining synchronized copies across multiple storage locations, it ensures data safety, redundancy, and minimal manual effort.
DG Backup Tool
----------------------

DG Backup Tool is a GUI-based Android backup and redundancy application built in Python.
It provides one-click Android to PC backups using ADB and incremental PC to external HDD synchronization, ensuring data safety through local redundancy.

The tool is designed for offline, local backups with no cloud dependency and offers a simple graphical interface suitable for daily use.

Key Capabilities
--------------------
Android to PC backup using ADB

Incremental PC to external HDD synchronization

Folder exclusion support

Copies only new files (no duplication)

GUI with real-time logging

Portable configuration storage

PyInstaller-ready single executable support

System Requirements
-----------------
Required

Windows 10 or Windows 11

Python 3.9 or higher

USB cable for Android device

External HDD or SSD (recommended)

Android Requirements
---------------------

USB Debugging enabled

ADB authorization granted

Dependencies
----------------

Install required Python packages:
-------------------------------------
pip install customtkinter pillow
-------------------------------------

Install Android Platform Tools (ADB) and add adb to your system PATH.

Verify installation:
---------------------
------------
adb devices
------------

Installation and Setup
-----------------------
1. Clone the Repository
--------------------------------------------------------------
git clone https://github.com/yourusername/dg-backup-tool.git
cd dg-backup-tool
---------------------------------------------------------------

2. Run the Application
-------------------------
python dg_backup_tool.py
---------------------------
The GUI will launch automatically.

Application Overview
---------------------
Main Controls
--------------
Start Phone Backup: Backs up Android device data to PC

Start Laptop to HDD Sync: Replicates PC backups to external HDD

Folder Mapping: Configure backup and sync paths

Clear Console: Clears log output

Exit: Safely closes the application


Configuration (Important)
-------------------------

All configuration is managed through the Folder Mapping screen and is saved automatically at:
-------------------------------------
%APPDATA%\DG_Backup_Tool\config.json
--------------------------------------

A) Phone to Laptop Mapping
----------------------------

Defines which folders on the Android device are backed up and where they are stored on the PC.

Example

Phone Path:

/sdcard/DCIM/Camera


Destination:

D:\Backup\Photos\2025


Type:

photo or video


Multiple mappings are supported. Files are filtered automatically based on type.

Note: Windows file picker may not display phone storage due to MTP limitations. Manual path entry is recommended.

B) Laptop to HDD Sync Mapping
-------------------------------

Defines which PC folders are synchronized to an external HDD for redundancy.

Example

Source:

D:\Backup\photo backup


Destination:

E:\Backup\photo backup


Only missing files are copied. Existing files are skipped. Folder structure is preserved.

C) Exclusions
---------------

Folders listed here are skipped during Laptop to HDD synchronization.

Example
D:\Backup\video projects\itachi shoot


Useful for excluding drafts, temporary files, or large projects.

Backup Workflow
------------------
Android to PC Backup

1. Connect Android device via USB
2. Enable USB Debugging
3. Click Start Phone Backup
4. The tool detects the device, lists files using ADB, and copies only new files

No files are deleted or modified on the Android device.

PC to HDD Sync
---------------

1. Connect external HDD
2. Click Start Laptop to HDD Sync
3. The tool compares folder contents and copies only missing files

Excluded folders are skipped automatically.

Supported File Types
----------------------
Photos
.jpg
.jpeg
.png
.heic
.gif

Videos
-------
.mp4
.mov
.avi
.mkv

Logging and Status
------------------------

-Live logs are displayed in the console panel

-Status bar shows current operation

-Errors related to ADB or file operations are clearly logged

-Multi-threaded execution ensures the UI remains responsive

Data Safety and Privacy
-----------------------

-No cloud usage

-No file deletion

-No data modification on Android device

-Read-only access via ADB

-Full user control over all data

Configuration File Location
----------------------------
%APPDATA%\DG_Backup_Tool\config.json

This allows portability and safe upgrades without losing configuration.

Known Limitations
-------------------

Windows file picker may not show Android storage (MTP limitation)

Backup is additive only (no delete sync)

Restore functionality is not yet implemented

Planned Enhancements
----------------------
Restore functionality
Scheduled backups
Backup verification using hashing
Multi-device support
Linux and macOS support

Author
----------
Sundaram Gaur
Copyright © 2025

Project Purpose
----------------
This project demonstrates real-world backup engineering, incremental synchronization logic, ADB automation, GUI application development, and production-ready packaging.

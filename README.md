# Project Title: Registry Tools Documentation

This repository contains a collection of setup instructions, reference URLs, HTML copies of these URLs, and personal observations for various registry tools. The purpose of this repository is to provide a centralized location for all the information related to these tools, making it easier for others to understand and use them.

## Structure

The repository is organized as follows:

- The root directory contains setup instructions for each tool. Each tool's setup is contained in a separate markdown file.
- `html_copies/`: This directory contains HTML copies of the reference URLs. This ensures that we have access to the information even if the original URL becomes unavailable.

## Index

Below is an index of all the tools covered in this repository. Each tool's name is linked to its section in this document.

1. [ERUNTgui](#eruntgui)
2. [RegistryChangesView](#registrychangesview)
3. [RegShot](#regshot)
4. [InstallSpy](#installspy)
5. [Process Monitor](#process-monitor)
6. [WhatChanged](#whatchanged)
7. [REGDIFF](#regdiff)
8. Multimon (to be tested)
9. Systracer (to be tested)
10. Installwatch pro (to be tested)
11. Others to be checked from [here](https://listoffreeware.com/best-free-registry-monitor-software-for-windows/).
---

### ERUNTgui

**Reference URLs:**

- [ERUNTgui will help you Backup, restore and optimize Windows Registry](https://www.thewindowsclub.com/backup-restore-and-opimize-windows-registry-with-new-eruntgui) [(cached)](http://htmlpreview.github.io/?https://github.com/anandphulwani/Registry-Tools/master/html_copies/ERUNTgui.html)
- [Softpedia ERUNTgui](https://www.softpedia.com/get/Tweak/Registry-Tweak/ERUNTgui.shtml#download)

**Observations:**

- Works perfectly for backing and restoring the registry, it backups in a folder, which backups the following files in `C:\Windows\ERDNT\<MM-DD-YYYY>` folder and some supporting files as well.
  - BCD
  - Default
  - SAM
  - SECURITY
  - SOFTWARE
  - SYSTEM
- You can rename the folder to make multiple backups, otherwise it will offer to delete the existing contents of the folder.
- The restored registry required a reboot to apply changes.

---

### RegistryChangesView

**Reference URLs:**

- [RegistryChangesView Homepage](https://www.nirsoft.net/utils/registry_changes_view.html)
- [RegistryChangesView Download](https://www.nirsoft.net/utils/registrychangesview-x64.zip)

**Observations:**

- Has a GUI which takes a snapshot and then compares what has changed since the snapshot.
- Also has a command line which gives a lot of options (you can check the bottom of the Homepage).
  - To save a snapshot of the registry
    
    `RegistryChangesView.exe /CreateSnapshot ".\Snapshot1" /CreateSnapshot.SoftwareHive 1 /CreateSnapshot.SystemHive 1 /CreateSnapshot.NTUserHive 1 /CreateSnapshot.UsrClassHive 1 /CreateSnapshot.DefaultHive 1 /CreateSnapshot.BCD00000000Hive 1 /CreateSnapshot.SAMHive 1 /CreateSnapshot.SecurityHive 1`
  - To compare registry between two snapshots
    
    `RegistryChangesView.exe /DataSourceDirection 1 /DataSourceType1 2 /DataSourceType2 2 /RegSnapshotPath1 ".\Snapshot2"  /RegSnapshotPath2 ".\Snapshot1" /sreg ".\RegDiff.reg"`
  - To compare registry between snapshots and current state
    
    `RegistryChangesView.exe /DataSourceDirection 1 /DataSourceType1 2 /DataSourceType2 1 /RegSnapshotPath1 ".\Snapshot1" /sreg ".\RegDiff.reg"`
  
---

### RegShot

**Reference URLs:**

- [RegShot Homepage](https://sourceforge.net/projects/regshot/)
- [RegShot Download](https://sourceforge.net/projects/regshot/files/latest/download)

**Observations:**

- Normal tool to take 1st snapshot and 2nd snapshot and compare both snapshots.
- Also has the ability to compare changes in path/drive.
- The comparison output comes in text file format and in detail what registry keys are added/modified, registy values are added/modified as well as the new registy values's values are displayed.
- Is better as compared to WhatsChanged as it is way way faster and the changes are displayed in much better.

---

### InstallSpy

**Reference URLs:**

- [MajorGeeks InstallSpy 2.00](https://www.majorgeeks.com/files/details/installspy.html)

**Observations:**

- Good tool to generate registry changes before and after an event (install/uninstall) or other.
- Generates an elaborated html report of the changes, with what values has changed, except for the binary data.

---

### Process Monitor

**Reference URLs:**

- [Process Monitor Homepage](https://learn.microsoft.com/en-us/sysinternals/downloads/procmon#screenshots)
- [Process Monitor Download](https://download.sysinternals.com/files/ProcessMonitor.zip)

**Observations:**

- Good tool to overall monitor the changes happening in your system including registry, file, network, process and thread and profiling event changes.
- Ability to apply filters, on particular processes and particular kind of changes.
- Ability to start and stop capture to track and filter out changes.
  
---

### WhatChanged

**Reference URLs:**

- [WhatChanged Homepage](https://www.majorgeeks.com/files/details/what_changed.html)

**Observations:**

- Normal tool to take 1st snapshot and 2nd snapshot and compare both snapshots.
- Also has the ability to compare changes in path/drive.
- The comparison output comes in text file format and just mentions what registry keys, registry value are added/modified but what are the modified values are not displayed.
- Is worse as compared to RegShot as it is way way slower and the changes are displayed in a serial order, separated in different files like HKCU, HKLM, HKU and HKCR without any bifurcation within them.
  
---

### REGDIFF

**Reference URLs:**

- [RegDiff Homepage](http://p-nand-q.com/download/regdiff.html)
- [RegDiff Download](http://p-nand-q.com/download/regdiff-4.3.7z)

**Observations (haven't used it, on the basis of reading the homepage):**

- Compares two reg files.
- Compares a registry key with a given .reg file.
- Ability to perform the following action on .reg file: create a diff file, merge file, sort file, remove empty keys from the output file, compare the current registry settings with a given file.
  
---

## Usage

To use this repository, clone it to your local machine and navigate to the setup instructions for the tool you're interested in.

## Contributing

Contributions are welcome! If you have any notes or observations to add, please update the corresponding section in this README. If you find a new reference URL, add it to the appropriate tool's section and create an HTML copy in the `html_copies/` directory.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

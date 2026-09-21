# KiCad Installation & Setup Guide

This guide covers installing KiCad 10.0.6, setting up plugins, importing libraries, and creating a new project for the HKUST Robotics Team Hardware.
You may also refer to this [PDF guide](https://github.com/YuanL-013/2026-Hardware-Tutorial/blob/main/KiCAD-Materials/KiCAD-Installation.pdf)\.

---

## Table of Contents

- [Installing KiCad](#installing-kicad)
- [How to Navigate KiCad](#how-to-navigate-kicad)
- [Installing Plugins](#installing-plugins)
  - [1. Interactive BOM](#1-interactive-bom)
  - [2. Via Stitching (External Import)](#2-via-stitching-external-import)
- [Importing Symbol Libraries](#importing-symbol-libraries)
- [Importing Footprint Libraries](#importing-footprint-libraries)
- [Importing DRC Rules](#importing-drc-rules)
- [Setting Up a New Project](#setting-up-a-new-project)
- [Naming Rule](#naming-rule)

---

## Installing KiCad

Download **KiCad 10.0.6** through the link provided:
- [Windows](https://downloads.kicad.org/kicad/windows/explore/stable) / [MacOS](https://downloads.kicad.org/kicad/macos/explore/stable) 

For Linux, install from terminal via Flatpak:
flatpak install https://flathub.org/repo/appstream/org.kicad.KiCad.flatpakref


> **Note:** The rest of this guide is demonstrated under **Windows**.

### Windows Installation

Select the correct installer for your system (x86_64 or ARM64) from the KiCad download page.

![Windows Installer Selection](https://github.com/YuanL-013/2026-Hardware-Tutorial/blob/main/img/00-windows-install.png?raw=true)

Run the installer and follow the steps:

1. Welcome screen → **Next**
2. Select components (default is fine) → **Next**
3. Choose install location → **Install**
4. Click **Finish** to complete

After installation, launch KiCad. The first time you open it, you can set the language to **English** for easier help from seniors.



---

## How to Navigate KiCad

The main KiCad window has the following tools:

| Tool | Description |
|------|-------------|
| **Schematic Editor** | Edit the project schematic |
| **Symbol Editor** | Edit global and/or project schematic symbol libraries |
| **PCB Editor** | Edit the project PCB design |
| **Footprint Editor** | Edit global and/or project PCB footprint libraries |
| **Gerber Viewer** | Preview Gerber files |
| **Image Converter** | Convert bitmap images to schematic symbols or PCB footprints |
| **Calculator Tools** | Show tools for calculating resistance, current capacity, etc. |
| **Drawing Sheet Editor** | Edit drawing sheet borders and title blocks |
| **Plugin and Content Manager** | Manage plugins and libraries |

![Launched Interface](img\01-launched-interface.png)

---

## Installing Plugins

Open **Plugin and Content Manager** from the main KiCad window.

### 1. Interactive BOM

- In the Plugin and Content Manager, search for **Interactive Html Bom**
- Click **Install**
- This plugin generates an interactive HTML BOM to assist with manual PCB assembly

### 2. Via Stitching (External Import)

- Download the plugin from [github/viastitcher](https://github.com/weirdgyn/viastitcher)
- Move it under: C:\Users\YourUser\KiCad\10.0\scripting\pluginsand unzip it
- **Note:** The directory depends on your laptop configuration
 

![Interactive BOM and Via Stitching](https://github.com/YuanL-013/2026-Hardware-Tutorial/blob/main/img/01a-interactive-bom.png?raw=true)
![Via Stitching External](https://github.com/YuanL-013/2026-Hardware-Tutorial/blob/main/img/01b-via-stitching-external.png?raw=true)

After selecting plugins, click **Apply Pending Changes** and wait for installation to complete.

---

## Importing Symbol Libraries

Before importing, make sure you have downloaded the **RDC2026_Libraries** folder. You can download it [here](KiCAD-Materials\2026RDC-Libraries.zip) if you haven't done so.

The folder contains:
- `HKUST_RDC2026_DRC_template` (folder)
- `HKUST_RDC2026_Footprint_Lib.pretty` (folder)
- `HKUST_RDC2026_Symbol_Lib.kicad_sym` (file)
- `HKUST_RDC2026_Symbol_Lib.bak` (backup file)

### Steps to Add Symbol Library

1. Open KiCad and go to **Preferences → Manage Symbol Libraries**
2. Click the **+** button to add a new library
3. Set the **Nickname** to `HKUST_RDC2026_Symbol_Lib`
4. Set the **Library Path** to the location of `HKUST_RDC2026_Symbol_Lib.kicad_sym`
5. Set **Library Format** to `KiCad`
6. Click **OK**

![Symbol Library Import](img\02-symbol-library-import.png)
![Symbol Library Import Detail](img\02a-symbol-library-import.png)

---

## Importing Footprint Libraries

### Steps to Add Footprint Library
This is similar to adding symbol library.  
1. Open KiCad and go to **Preferences → Manage Footprint Libraries**
2. Click the **+** button to add a new library
3. Set the **Nickname** to `HKUST_RDC2026_Footprint_Lib`
4. Set the **Library Path** to the location of `HKUST_RDC2026_Footprint_Lib.pretty`
5. Set **Library Format** to `KiCad`
6. Click **OK**

![Footprint Library Import](img\03-footprint-library-import.png)

---

## Importing DRC Rules

The DRC (Design Rule Check) template is provided in the `HKUST_RDC2026_DRC_template` folder. You can import these rules into your PCB project to ensure your design meets the required manufacturing specifications.

> **Tip:** Check the `HKUST_RDC2026_DRC_template` folder for the `.kicad_dru` file and load it in the PCB Editor under **File → Board Setup → Design Rules**.

---

## Setting Up a New Project

1. Open KiCad
2. Go to **File → New Project** (or press `Ctrl+N`)
3. Choose a location and name for your project
4. Click **Save**

![Setting Up New Project](img\04-setting-up-new-project.png)

> **Important:** Do **NOT** put all project files into a single folder. Follow the **one project, one folder** rule with version tracking.

### Good Habit: One Project One Folder + Version Tracking

Example of proper folder structure:  
2026-RDC-Controller-2026-08-20/  
2026-RDC-Controller-2026-08-25/  
2026-RDC-Controller-2026-08-26/  
2026-RDC-Controller-2026-08-27/  
2026-RDC-Controller-2026-08-28/  
2026-RDC-Controller-2026-08-31/  


---

## Naming Rule

**HKUST Robotics Team - Hardware**

> ### Rule: [nameofboard]\_[version]\[layer]\_[thickness]

**Example:** `test_V1.0_L2_T1d6`

### Version

| Change Type | Version Bump | Example |
|-------------|--------------|---------|
| Schematic change | Major version | `test_V2.0_L2_T1d6` |
| Minor changes in PCB layout | Minor version | `test_V1.1_L2_T1d6` |

### Thickness

- Usually `T1d6` (1.6mm) for L2/L4 boards
- Can be higher for special orders (higher current, thicker copper, etc.)

---


## After Everything Is Done

You should have the following file types in your project folder:

| File Type | Description |
|-----------|-------------|
| `.kicad_pro` | KiCad Project file |
| `.kicad_sch` | KiCad Schematic file |
| `.kicad_pcb` | KiCad Board file |


> **Note:** The file names are not fixed — they will match your project name. Pay attention to the file extensions to identify each file type.

---

*For JLC PCB custom made boards options, you can change colours of your boards φ(*￣0￣)*

[↑ Back to Top](#table-of-contents)
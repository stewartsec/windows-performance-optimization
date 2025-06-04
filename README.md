# Windows Desktop Optimization Guide

## Overview

This guide documents the step-by-step process used to improve performance on a Windows desktop experiencing severe lag, high disk usage, and slow startup times. The goal was to optimize the system without performing a full reinstall of the operating system. The result is a streamlined, stable, and more efficient system suitable for daily use.

---

## Problem Statement

The Windows desktop exhibited the following issues:

* Persistent 100% disk usage during startup
* Excessive boot time (5–10+ minutes)
* Frequent system pop-ups and unwanted background applications
* High memory and CPU usage caused by unnecessary services and programs
* Slow overall responsiveness

---

## Optimization Steps

### 1. Process & Resource Analysis

* Used **Task Manager** to monitor CPU, Memory, and Disk activity
* Identified resource-intensive processes such as:

  * McAfee antivirus suite
  * OneLaunch application
  * ExpressVPN services
  * HP Support and update tools
  * Citrix Workspace components

### 2. Uninstallation of Unnecessary Software

* Removed via **Control Panel > Programs and Features**:

  * McAfee (followed by official [MCPR tool](https://www.mcafee.com/support/?articleId=TS101331))
  * OneLaunch
  * ExpressVPN
  * Citrix-related services
  * HP Support Assistant (based on hardware/software needs)

### 3. Startup Program Optimization

* Disabled non-essential startup apps using:

  * **Task Manager > Startup tab**
  * **Settings > Apps > Startup**
* Examples of disabled items:

  * Microsoft Teams (all instances)
  * OneDrive (if not in use)
  * Adobe and HP updaters
  * Spotify and other personal-use applications

### 4. Background Service Management

Used **services.msc** to disable:

* **SysMain (Superfetch)** – to reduce disk usage
* **Windows Search Indexer** – to prevent background indexing
* Residual services from McAfee, ExpressVPN, and HP utilities

### 5. Temporary File Cleanup

* Manually cleared temporary directories:

  * `%temp%`
  * `C:\Windows\Temp`
* Ran **Disk Cleanup** including:

  * System files
  * Windows Update cleanup
  * Temporary internet and setup files

### 6. Task Scheduler Review

* Used **taskschd.msc** to disable leftover scheduled tasks related to:

  * OneLaunch
  * McAfee updates
  * HP notifications and reminders

### 7. Disabling Windows Widgets

* Turned off via **Settings > Personalization > Taskbar**
* Disabled background widget processes via the Registry:

  * Path: `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced`
  * Entry: `TaskbarDa = 0`

### 8. Notification and Background App Tweaks

* Disabled Windows tips and welcome screens:

  * **Settings > System > Notifications**
* Disabled unnecessary background apps via **Settings > Privacy & Security**

---

## Post-Optimization Results

| Metric               | Before        | After            |
| -------------------- | ------------- | ---------------- |
| Startup Time         | 5–10+ minutes | \~1–2 minutes    |
| Disk Usage (Idle)    | Constant 100% | 5–15% after boot |
| CPU Usage (Idle)     | 60%+          | 5–10%            |
| Background Processes | Overloaded    | Minimal          |
| Popups/Distractions  | Frequent      | None             |

---

## Additional Notes

* **SSD Upgrade** is strongly recommended for even greater performance improvement
* A **System Restore Point** should be created once the system is in a clean state
* Consider a **clean Windows install** only if further problems persist

---

## Tools Utilized

* Task Manager
* Services Manager (`services.msc`)
* Task Scheduler (`taskschd.msc`)
* Windows Settings & Startup tools
* Registry Editor (`regedit`) – for specific tweaks
* [McAfee Consumer Product Removal Tool](https://www.mcafee.com/support/?articleId=TS101331)

---

## Outcome

The optimization process successfully restored system performance to an acceptable level for everyday use. The system now boots quickly, runs efficiently, and is free of unnecessary interruptions and background noise. This guide serves as a reference for similar performance restoration tasks on Windows systems.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

# Torrent Automator 🚀

A lightweight, production-grade background directory monitor for Windows that automates the copying of completed torrents from your local disk (`D:`) to external storage (`E:`). 

This script architecture functions as a stealth system worker—running completely invisibly with zero CPU overhead, while pushing native desktop notification banners during file transfers.

===

## 🛠️ Technologies Used

The architecture of this project is explicitly built using core system languages and scripting environments native to Windows to eliminate heavy external dependencies:

*   *Python 3.x:* Handles the core background monitoring engine, directory auditing, conditional loop checkpoints, path validation hooks, and robust multi-threaded file operations.
*   *VBScript (Visual Basic Script):* Acts as the execution layer wrapper. It interacts directly with the Windows Script Host to launch the Python interpreter with a 0 window flag, masking the active command shell from view.
*   *Windows PowerShell:* Used as a lightweight, inline graphics engine. It pulls down the native .NET framework libraries (System.Windows.Forms) to deliver rich desktop notification banners without slowing down file operations.
*   *HTML5 / CSS3:* Provides a clean, styled, portable setup blueprint readable inside any web browser on any device.

===

## 🌟 Key Features

*   **Stealth Background Execution:** Utilizing native `.vbs` wrappers, the Python runtime environment runs completely hidden without leaving messy console windows active on your desktop.
*   **Safety-Locked Auto-Deletion:** Implements a byte-size integrity lock. The engine checks the exact file size on the destination drive against the source download; files are only purged locally if the transfer matches to the single byte.
*   **Native Windows HUD Banners:** Leverages decoupled background PowerShell API routing to send real-time slide-out notifications for initialization, active copying, and transfer success state-changes.
*   **Zero Resource Drain (0% CPU):** Operates on an efficient 10-second idle thread sleep cycle. Suspended directly by the OS kernel, drawing virtually ~0% CPU and minimal memory (~12MB RAM).
*   **Missing Storage Safeguards:** If your external drive is disconnected, the engine bypasses file operations safely and polls paths patiently every 10 seconds without generating fatal application crashes.
*   **Path Length Limit Protection:** Integrated mitigation strategies ensure complex multi-layered torrent directory trees or long string names never cause unexpected transfer termination.

---

## 🛠️ System Components

The pipeline divides responsibilities across 3 core files deployed in your local storage ecosystem:

| Component File | Deployment Path | Primary Function |
| :--- | :--- | :--- |
| **`torrent_watcher.py`** | `D:\Scripts\` | The core background transfer engine & safety checker. |
| **`Start Torrent Watcher.vbs`** | `Desktop` / `Startup` | Launches the automation engine invisibly with a startup banner. |
| **`Stop Torrent Watcher.vbs`** | `Desktop` | Appends a safe log signature and kills background Python execution. |

---

## 🚀 Deployment Instructions

For step-by-step setup walkthroughs—including configuring Windows Boot automation paths and environmental dependencies—view our interactive documentation.

👉 **[Click Here to View the Interactive HTML Setup Guide](https://vjharan.github.io/torrent-automator/)**

---

## 📄 License

This project is open-source and free to use under the MIT License

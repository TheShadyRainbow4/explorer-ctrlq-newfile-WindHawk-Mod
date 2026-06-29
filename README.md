# Explorer Ctrl+Q to New Folder

This mod enhances Windows Explorer by mapping **Ctrl+Q** to create a new folder instantly.

### Purpose & Fork Details
This is a fork of "Explorer Ctrl+N to New File". The original mod bound the action to **Ctrl+N**, which conflicted with the native "New Window" shortcut, and generated blank, extension-less files which were not useful for most users.
---
This version improves the workflow by:
1.  **Remapping to Ctrl+Q**: Eliminates conflicts with standard Windows shortcuts.
2.  **Creating Directories**: Generates standard file system folders instead of empty files.
3.  **Stability Fixes**: Implements `SHChangeNotify` and thread synchronization to prevent the "Race Condition" crash where Explorer would attempt to rename the folder before the UI had finished creating it.
---
### How it works
The mod utilizes Windhawk to inject a `WH_KEYBOARD_LL` (low-level keyboard hook) directly into the `explorer.exe` process. Upon triggering:
1.  It resolves the current directory path (supporting Windowed Explorer windows only not Desktop).
2.  It creates a unique directory name (e.g., "New folder (2)").
3.  It forces a Shell Update to register the change immediately.
4.  It programmatically selects the new folder and initiates the rename command.


## Scope
Outlines the core functions, limitations, and operational boundaries of the explorer-ctrlq-new-folder-WindHawk-Mod utility.

## Plans
Roadmap includes UI refinements, bug fixes, and expanded compatibility options.

## Development
Built in accordance with EliteSoftware GUI development guidelines.
- **Framework**: .NET Framework 4.6 / WinForms
- **Visual Styles**: Enabled
- **Apartment State**: STA Mode enforced for GUI reliability.

## What It Is
A dedicated system utility developed by EliteSoftwareTech Co. to perform system tasks cleanly and efficiently.

## How to Use
1. Launch the utility.
2. Follow the on-screen instructions or refer to tooltips for interactive elements.
3. Access Settings from the main menu for configuration.

---
### EliteSoftwareTech Co. - GUI Guidelines
- **Authors**: Zachary Whiteman, Susan Gemm, TheShadyRainbow4, EliteSoftwareTech Co.
- **Company**: EliteSoftware / EliteSoftwareTech Co.
- **Document Version**: 1.2.0.0
- **Target Framework**: .NET Framework 4.6 (WinForms / Legacy Win32)
- **Minimum OS Target**: Windows Vista / Windows 7
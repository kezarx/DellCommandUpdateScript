Dell Command Update Script

Overview

This script automates the process of scanning and applying updates using Dell Command Update (DCU). It first checks for the presence of the dcu-cli.exe executable in standard installation paths and then performs the update actions.

Prerequisites

Dell Command Update (DCU) must be installed on the system.

Ensure that the script is executed with administrative privileges.

Create the directory C:\DCU_LOGS to store log files (if it does not already exist).

Script Functionality

Checks for the presence of dcu-cli.exe in the following locations:

C:\Program Files\Dell\CommandUpdate\dcu-cli.exe

C:\Program Files (x86)\Dell\CommandUpdate\dcu-cli.exe

If found, the script:

Scans for available updates and logs the results to C:\DCU_LOGS\ScanUpdates.log

Applies the detected updates and logs the process to C:\DCU_LOGS\ApplyUpdates.log

Disables automatic reboot after applying updates.

If dcu-cli.exe is not found, the script outputs a message indicating its absence.

Usage

Run the script using PowerShell with administrative privileges:

..\update_script.ps1

Logs

C:\DCU_LOGS\ScanUpdates.log: Contains information about available updates.

C:\DCU_LOGS\ApplyUpdates.log: Stores details about applied updates.

Notes

Ensure the system has internet access to download updates.

If updates require a reboot, manually restart the system after execution.

Modify the script as needed to enable automatic reboot by changing -reboot=disable to -reboot=enable.

Troubleshooting

If updates do not apply, ensure Dell Command Update is properly installed.

Check logs for any errors or warnings.

Run PowerShell as administrator if encountering permission issues.

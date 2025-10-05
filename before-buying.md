⚙️ 1. System Configuration Check (Model, CPU, RAM, GPU)
Command 1:
////////////////////////////////////////////////////////////////////////////////////////////

    dxdiag

➡️ Opens DirectX Diagnostic Tool
🔍 Check karo:
- System tab: Model, Processor, RAM
- Display tab: Graphics card info

Command 2 (Detailed Specs via Command Line):
////////////////////////////////////////////////////////////////////////////////////////////

    systeminfo

➡️ Full system details: OS version, manufacturer, BIOS date, RAM, etc.
////////////////////////////////////////////////////////////////////////////////////////////

💻 2. Hardware Information via PowerShell >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    Get-ComputerInfo | Select-Object CsManufacturer, CsModel, OsName, OsArchitecture, WindowsVersion
    
➡️ Shows manufacturer, model, Windows version, and architecture (32-bit / 64-bit).

💾 3. Disk / SSD Health Check             >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    wmic diskdrive get model,name,status
    
➡️ Output should show Status = OK for all drives.
👉 For deeper check (health %):
- Download CrystalDiskInfo → https://crystalmark.info/en/software/crystaldiskinfo/
  → Open → “Health Status = Good” hona chahiye.

🔋 4. Battery Health Report               >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    powercfg /batteryreport
    
➡️ Generates HTML report (path shown in CMD, usually C:\Users\<YourName>\battery-report.html)
🔍 Open it → Compare:
- Design Capacity (original)
- Full Charge Capacity (current)
👉 Example:
Design = 50,000 mWh, Full = 40,000 mWh → 80% health.

💨 5. Temperature & Overheating Test      >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    Use Tool: HWMonitor

➡️ Shows CPU, GPU temps in real-time.
🔍 Idle temp < 55°C, load temp < 85°C preferred.
(No built-in command for live temp in Windows.)

🧠 6. Performance Check (CPU, Memory, Disk Usage)  >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    taskmgr
    
➡️ Opens Task Manager.
🔍 Performance tab me:
- CPU % normal (idle: 2–10%)
- Memory usage reasonable
- Disk usage < 10% idle

🧮 7. Storage Speed (Optional)            >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

Tool: CrystalDiskMark

    https://crystalmark.info/en/software/crystaldiskmark/

➡️ SSD read speed > 400 MB/s (SATA), > 2000 MB/s (NVMe)

🔌 8. Ports & Connectivity Check          >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
- Wi-Fi list: (→ Available Wi-Fi list show karega.)

      netsh wlan show networks

- Bluetooth check: (→ Opens Device Manager → Check under "Bluetooth" → No yellow warning icons.)

      devmgmt.msc

Manual tests:
- USB me pendrive lagao.
- Audio jack me earphones test karo.
- HDMI connect karke display check karo.

🔐 9. Windows Activation & License Check (➡️ Popup aayega → “Windows is activated permanently” likha hona chahiye.)

    slmgr /xpr

- Command ➡️ Shows edition & partial product key. (license key type):

      slmgr /dli

🧱 10. BIOS / UEFI Access Check           >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
- Restart → Press F2 or DEL key → BIOS open hona chahiye.
- Agar password maange to seller se clear karwao.

Command to check BIOS version:

    wmic bios get smbiosbiosversion
    
🧾 11. Serial Number Verification         >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    wmic bios get serialnumber
    
➡️ Note it down → Match with invoice or seller’s record.
Also verify warranty online via brand’s site (e.g., Dell, HP, Lenovo).

💸 12. Laptop Age Check                   >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    systeminfo | find "Original Install Date"

➡️ Approximate install date mil jaayegi (OS level).
Model release year check via Google:
👉 “<Model Name> release year”

🧹 13. System Freshness Check             >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    taskmgr

→ Startup tab → Disable unnecessary items.

OR run

    msconfig

→ “Startup” tab check for bloatware.

✅ Summary of Key Commands (Quick Reference)

| Purpose             | Command                           |                               |
| ------------------- | --------------------------------- | ----------------------------- |
| System Info         | `dxdiag`                          |                               |
| Disk Status         | `wmic diskdrive get status`       |                               |
| Battery Health      | `powercfg /batteryreport`         |                               |
| Windows Activation  | `slmgr /xpr`                      |                               |
| Serial Number       | `wmic bios get serialnumber`      |                               |
| BIOS Version        | `wmic bios get smbiosbiosversion` |                               |
| Wi-Fi Networks      | `netsh wlan show networks`        |                               |
| System Install Date | `systeminfo                       | find "Original Install Date"` |


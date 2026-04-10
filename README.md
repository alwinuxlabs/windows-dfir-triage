# 🚨 Windows DFIR Triage Script v1.0

Lightweight PowerShell-based DFIR triage script for rapid incident response collection.

**Author:** Alwin Espiritu (alwinux)
**Date:** 2026-04-10

---

## ⚠️ Disclaimer

This tool is intended for **authorized security testing and incident response only**.
Unauthorized use may violate local laws and regulations.

---

## 📌 Features

* System information collection
* User and administrator enumeration
* Process listing and process tree
* Network artifacts:

  * netstat
  * ARP table
  * DNS cache
* Persistence checks:

  * Run keys
  * Services
  * Scheduled tasks
* WMI persistence detection
* Installed software inventory
* Full `C:\` file listing
* Optional osquery integration

---

## ⚙️ Requirements

* Windows 10 / 11 / Server
* PowerShell 5+ or 7
* Administrator privileges

**Optional:**

* osquery installed and added to PATH

---

## 🚀 How to Use

1. Clone the repository:

```bash
git clone https://github.com/n00b101/windows-dfir-triage.git
```

2. Navigate to the folder:

```bash
cd windows-dfir-triage
```

3. Run the script as Administrator:

```powershell
powershell -ExecutionPolicy Bypass -File .\dfir-triage.ps1
```

---

## 📂 Output

The script generates a timestamped directory:

```
DFIR_Output_YYYY-MM-DD_HH-MM-SS
```

Each file includes:

* Command executed
* Timestamp
* Raw command output

---

## 📄 Collected Artifacts

### 🖥️ System Information

* `systeminfo.txt`
* `hostname.txt`
* `whoami_all.txt`
* `logical_disks.txt`

### 👤 User Enumeration

* `net_user.txt`
* `local_admins.txt`
* `query_user.txt`

### ⚙️ Process Collection

* `tasklist_verbose.txt`
* `process_tree.txt`

### 🌐 Network Information

* `netstat_ano.txt`
* `ipconfig_all.txt`
* `arp_table.txt`
* `route_table.txt`
* `dns_cache.txt`

### 🔐 Persistence Checks

* `scheduled_tasks.txt`
* `services.txt`
* `runkey_hklm.txt`
* `runkey_hkcu.txt`
* `startup_items.txt`

### 🧠 WMI Persistence

* `wmic_event_filters.txt`
* `wmic_event_consumers.txt`
* `wmic_bindings.txt`
* `wmi_event_filters_ps.txt`
* `wmi_event_consumers_ps.txt`
* `wmi_bindings_ps.txt`

### 📦 Installed Software

* `installed_software.txt`

### 📁 File System

* `file_listing_C.csv`

### 🧪 Optional (if osquery is installed)

* `osquery_processes.txt`
* `osquery_network.txt`

---

## ⚠️ Notes

* Full `C:\` file listing may take significant time depending on disk size
* Ensure sufficient disk space before execution
* Script is intended for **triage collection**, not full forensic imaging
* Some commands may generate large output files

---

## 🧠 Use Cases

* Incident Response (IR)
* Threat Hunting
* Live Response Collection
* Malware Investigations

---

## 📜 License

MIT License

---

## 🙌 Acknowledgements

Built for DFIR practitioners and security teams to accelerate live response and triage investigations.

---

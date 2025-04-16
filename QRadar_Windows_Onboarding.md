
# 📘 QRadar + Windows Server 2019 Onboarding (with WinCollect Agent)

---

## 🧩 Section 1: WinCollect Agent Installation

### 🔧 Prerequisites
- Admin access on Windows Server 2019
- IBM QRadar Console access
- Network connectivity between the server and QRadar
- Firewall ports open for WinCollect (default: TCP/UDP 514 or custom port)

### 📥 Step-by-Step Installation

1. **Download WinCollect Agent**
   - Go to QRadar Console → **Admin > WinCollect > WinCollect Agent Downloads**
   - Download the latest `WinCollect Installer.exe`

2. **Run the Installer**
   - Double-click the installer on the target Windows Server.
   - Choose **Managed WinCollect Agent** mode.
   - Enter the QRadar Console IP and port.

3. **Firewall Configuration**
   - Allow the port used by the agent to communicate with QRadar.
   - Default ports: `514` (Syslog) or custom defined during setup.

4. **Verify Installation**
   - Check that the **WinCollect service** is running (`services.msc`)
   - Logs: `C:\Program Files\IBM\WinCollect\logs`

---

## 🧩 Section 2: QRadar Onboarding – Windows Server 2019

### 🧾 Log Source Setup in QRadar

1. **Login to QRadar Console**
2. Go to **Admin > Log Sources**
3. Click **Add**

#### Example Configuration:
- **Log Source Type**: `Microsoft Windows Security Event Log`
- **Protocol Configuration Type**: `WinCollect`
- **Log Source Identifier**: `WinServer2019-DC`
- **Hostname/IP**: IP of Windows Server
- **Event Types**: `Security`, `System`, `Application`
- **Protocol Port**: Match the port used by WinCollect agent

4. Click **Save** and **Deploy Changes**

---

### 🔍 Validation Steps

1. Trigger an event on the Windows Server (e.g., login/logout)
2. In QRadar:
   - Go to **Log Activity**
   - Set filter: `Log Source = WinServer2019-DC`
   - Check for incoming events

---

### ⚙️ Optional Tuning

- Use **Log Source Extensions (LSXs)** for better parsing
- Create **custom rules** for specific Windows Event IDs
- Adjust **Offense Rules** for Windows-specific threats

---

### ✅ Summary

| Task | Status |
|------|--------|
| WinCollect Agent Installed | ✅ |
| Windows Event Logs Configured | ✅ |
| QRadar Log Source Created | ✅ |
| Events Verified | ✅ |
| Rule Tuning Applied | 🔄 Optional |

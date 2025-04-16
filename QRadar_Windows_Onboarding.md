
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
   - Go to QRadar Console → **Admin > WinCollect > WinCollect Agent Downloads or offical website download file**
![image](https://github.com/user-attachments/assets/67132c57-851f-4306-bd27-c43480ab61e0)
   - Download the latest `WinCollect Installer.exe`
![image](https://github.com/user-attachments/assets/8712a585-48c2-441b-b508-99e01a62742e)


2. **Run the Installer**
   - Double-click the installer on the target Windows Server.
   - Choose **Managed WinCollect Agent** mode.
   - Enter the QRadar Console IP and port.
![image](https://github.com/user-attachments/assets/dbc2cb76-6e04-4f0e-bdf6-04de139d4196)


3. **Firewall Configuration**
   - Allow the port used by the agent to communicate with QRadar.
   - Default ports: `514` (Syslog) or custom defined during setup.

4. **Verify Installation**
   - Check that the **WinCollect service** is running (`services.msc`)
![image](https://github.com/user-attachments/assets/9d482975-ecc4-47f2-bf90-73c0cc83159e)

   - Logs: `C:\Program Files\IBM\WinCollect\logs`
![image](https://github.com/user-attachments/assets/264e1de4-a04e-45d0-82d0-101a62177e3a)

---

## 🧩 Section 2: QRadar Onboarding – Windows Server 2019

### 🧾 Log Source Setup in QRadar

1. **Login to QRadar Console**
2. Go to **Admin > Log Sources**
3. Click **Log Sources**
![image](https://github.com/user-attachments/assets/dda109c0-a0ec-47ba-9ae7-99be0db7361a)


4. **Log Sources Management** [list of logs sources]
  ![image](https://github.com/user-attachments/assets/58624ed7-400c-4d9d-9526-d0dc41b5f45d)


#### Example Configuration:
- **Log Source Type**: `Microsoft Windows Security Event Log`
- **Protocol Configuration Type**: `WinCollect`
- **Log Source Identifier**: `WindowsAuthServer @ WIN-G3GK591KL48`
- **Hostname/IP**: WIN-G3GK591KL48
- **Event Types**: `Security`, `System`, `Application`
- **Protocol Port**: 514
---

### 🔍 Validation Steps

1. Trigger an event on the Windows Server (e.g., login/logout)
2. In QRadar:
   - Go to **Log Activity**
   - Set filter: `Log Source = WIN-G3GK591KL48`
![image](https://github.com/user-attachments/assets/400d6040-ec82-4f92-bfe6-313ef9193d25)

   - Check for incoming events[e.g. login success or failed]
![image](https://github.com/user-attachments/assets/9d7d1430-5386-48f3-bc69-9c6f3e5fd2ca)

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

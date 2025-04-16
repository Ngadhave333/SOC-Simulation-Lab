# 🧠 Advanced Detection & Analysis – QRadar Simulation Report

---

## 🧪 Simulated Security Events

| Event             | Description                          |
|------------------|--------------------------------------|
| Brute Force       | 10 failed RDP login attempts         |
| Malware           | EICAR test file triggered            |
| PowerShell Attack | Suspicious PowerShell script         |
| USB Activity      | Data exfiltration to USB             |

---

## 🔍 Detection

- QRadar detected offenses based on correlation rules
- Windows Defender alerted for EICAR test file
- Hash analyzed using [VirusTotal](https://www.virustotal.com)
- External IPs verified using [Cisco Talos](https://talosintelligence.com)

---

## 🚨 Incident Response

- Investigated logs and offenses in QRadar
- Identified suspicious host: `WIN-G3GK591KL48`
- Documented findings and screenshots
- Simulated escalation to higher tier analyst

---

## ✅ Outcome

| Action Item                      | Status   |
|----------------------------------|----------|
| Alerts generated in QRadar       | ✅       |
| EICAR test successfully detected | ✅       |
| Triage and investigation done    | ✅       |
| Escalation process tested        | ✅       |

---

## 📌 Recommendations

- Fine-tune offense rules to reduce false positives  
- Expand detection to include lateral movement  
- Integrate with SOAR (if available) for automated response  

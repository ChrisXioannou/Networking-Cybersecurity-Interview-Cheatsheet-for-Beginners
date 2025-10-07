## 🔑 Quick Notes

### 🔒 TLS

- Secures communication over the internet.
- Provides **confidentiality, integrity, authentication**.
- Uses a **handshake** to exchange keys and verify certificates.
- Example: HTTPS = HTTP + TLS.

### 🔑 Encryption Standards

- **Symmetric (1 key):** AES (fast, VPNs, disk encryption).
- **Asymmetric (2 keys):** RSA, ECC (TLS, digital signatures).
- **Hashing (1-way):** SHA-256, used for integrity & passwords.
- **Salting:** Add randomness to passwords before hashing.

### 📊 SIEM

- Collects and correlates logs from multiple sources.
- Detects suspicious activity using **rules (signatures)** and **behavior (UEBA)**.
- Integrates with **SOAR** for automated response.
- Example: ClearSkies (Odyssey).

### 📁 Logs

- **Windows:** Event IDs (4624/4625 login, 4688 process, 4720 user created, 7045 service created).
- **Linux:** `/var/log/auth.log`, `journalctl`, `last`, `who`.
- Key logs: authentication, process creation, privilege changes, firewall, VPN.

### 🌐 Networking

- **DNS:** Translates domain → IP.
- **IP:** Address of device (IPv4/IPv6).
- **Firewall:** Filters traffic (ports, protocols, IPs).
- **VPN:** Encrypted tunnel.
- **TLS/HTTPS:** Encrypts web traffic.
- **ARP spoofing/MITM:** Redirects traffic to attacker.

### 💥 Simple Exploits

- **SQL Injection:** Input `' OR 1=1 --` bypasses login.
- **XSS:** `<script>alert('xss')</script>` injects code in page.
- **Buffer Overflow:** Writing beyond memory → crash/control.
- **Phishing:** Fake email → steal credentials.

### 📜 ISO & NIST

- **ISO 27001:** International standard for Information Security Management (ISMS). Risk-based, Annex A controls.
- **NIST CSF:** US framework, 5 functions → Identify, Protect, Detect, Respond, Recover.
- Both give **best practices for managing cyber risk**.

### 🛡️ Firewalls & IDS/IPS

- **Firewall:** Filters traffic based on IP, port, protocol.
- **IDS (Intrusion Detection):** Monitors network/host traffic, alerts on suspicious activity.
- **IPS (Intrusion Prevention):** Same as IDS, but can actively block traffic.
- Rule of thumb: firewall = gatekeeper, IDS/IPS = guard watching activity.

### 🔐 Authentication & Access Control

- **MFA (Multi-Factor Authentication):** Something you know, have, or are.
- **Least Privilege:** Users only get the access they need.
- **RBAC (Role-Based Access Control):** Permissions based on roles (admin, user).

### 📧 Email Security

- **SPF:** Defines which servers can send mail for a domain.
- **DKIM:** Digital signature for email integrity.
- **DMARC:** Policy to reject/quarantine suspicious mail.
- Common phishing indicators: mismatched domain, urgent tone, suspicious links.

### 📊 Incident Response Metrics

- **MTTD:** Mean Time to Detect.
- **MTTR:** Mean Time to Respond/Recover.
- **Dwell Time:** Time attacker stays undetected.

### 🧑‍💻 Common Attacks

- **Brute Force:** Many login attempts until correct.
- **Dictionary Attack:** Using known password lists.
- **DoS/DDoS:** Flood system/network to make it unavailable.
- **MITM (Man-in-the-Middle):** Intercept/alter communication.
- **Privilege Escalation:** Gain higher permissions.

### 🖥️ Operating Systems Security

- **Windows:** Monitor Event IDs, patch regularly, disable unnecessary services.
- **Linux:** Review `/etc/passwd`, `/etc/shadow`, SSH configs, use `fail2ban`.
- **Hardening:** Patching, least privilege, logging, firewall rules.

### 📑 Compliance & Legal

- **GDPR:** Protects EU citizens’ personal data, heavy fines for breaches.
- **NIS2:** EU directive forcing critical sectors to adopt strong cybersecurity.
- **ISO 27001:** ISMS standard (risk-based controls).
- **NIST CSF:** Framework for US companies (Identify, Protect, Detect, Respond, Recover).

---

---

---

---

---

---

# **PLAN:**

---

Operating systems:

1. i learned journalctl for logs, and how to use it to specifically check for certain logs, certain times as well
2. learner the useradd and add user, how to add users basically and log files for them

---

## **TOP PRIORITIES**

1. learn osi really well
2. bash scripting
3. watch dhcp
4. lead code
5. ports, commands, acronyms,protocols
6. packet familiar
7. accorsing to nist
8. watch interview video
9. attack types


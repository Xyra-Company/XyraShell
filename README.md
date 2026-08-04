# X77Shell PRO (X77 Engine v7.1)

> **Advanced PHP 8.5 Web Shell for Educational & Security Auditing Purposes**

![Version](https://img.shields.io/badge/version-7.1-purple)
![License](https://img.shields.io/badge/license-MIT-blue)
![PHP](https://img.shields.io/badge/PHP-8.5.5-cyan)
![Security](https://img.shields.io/badge/Security-CSRF+RateLimit+Stealth-red)

**X77Shell PRO** (powered by the X77 Engine v7.1) is a modern PHP-based web shell optimized for **PHP 8.5.5**.  
This tool is specifically designed for:

- Educational Cybersecurity Labs
- Red Team Simulations
- Server Maintenance Audits
- Security Research Environments
- **Advanced Penetration Testing**

With a responsive Single Page Application (SPA) interface, X77Shell PRO provides advanced features including file management, multi-tab terminal emulation, real-time vulnerability intelligence (NVD API), forensic analysis, **stealth persistence**, **privilege escalation scanning**, and **red-team tooling**.

---

# ⚠️ DISCLAIMER & LEGAL WARNING

> **IMPORTANT: READ BEFORE USING**

1. **Educational Use Only**  
   This tool is developed and distributed strictly for educational purposes, security research, and authorized penetration testing.

2. **User Responsibility**  
   The developers and organization are NOT responsible for any damage, data loss, misuse, or illegal activities performed using this tool.

3. **Illegal Usage**  
   Using this tool on systems, servers, or networks without explicit written authorization is ILLEGAL and may violate cybersecurity laws including:
   - CFAA (United States)
   - Computer Misuse Acts
   - Electronic Information Laws (UU ITE Indonesia)
   - Other local cybersecurity regulations

4. **Compatibility**  
   X77Shell PRO requires **PHP 8.5.5 or newer** for full compatibility and modern security support.

**By using this software, you acknowledge and accept full responsibility for your actions.**

---

# Main Features

## Advanced Terminal Emulator

- Multi-Tab & Split Screen terminal sessions
- Smart autocomplete & command history
- ANSI color support
- Command palette (`Ctrl+P`)
- Ghost text suggestions
- Command queue execution system

---

## Professional File Manager

- Tree View & Grid/List modes
- Bulk file operations
- Zip & Unzip support
- Built-in code editor
- Syntax highlighting
- Auto-save & multi-tab editing
- Dangerous permission auditor

---

## Security & Forensics Tools

- Access log analyzer
- SQLi/XSS/Shell injection detection
- Brute-force activity detection
- Security header auditing
- SSL/TLS certificate checker
- PHP security checklist
- Permission auditing system

---

## CVE Intelligence (NVD API)

- CVE lookup by ID
- Vulnerability keyword search
- Real-time recent CVEs
- Severity-based highlighting

---

## Network & OSINT Utilities

- Whois lookup
- Reverse IP lookup
- TCP port scanner
- CMS detection system

---

## Cryptography & Hashing

Supported algorithms:
- MD5
- SHA1
- SHA256
- SHA384
- SHA512
- RIPEMD160
- CRC32B

Additional tools:
- Hash identifier
- Base64 tools
- URL encoder/decoder
- HEX tools
- ROT13
- HTML entities
- Reverse string utilities

---

## Stealth & Hardening (NEW in v7.1)

- **Error suppression:** All PHP errors redirected to `/dev/null`
- **Bash history protection:** Every command runs with `unset HISTFILE`
- **Non-interactive sudo scanning:** No password prompts during privilege checks
- **Zero-log footprint:** Minimal system log exposure
- **Process renaming:** Hide shell processes as `[kworker]`

---

## Advanced Modules (NEW in v7.1)

### Stealth Module
- Evasion: Clear server logs (Apache, Nginx, Syslog, Auth)
- AES-256-CBC encryption/decryption for payload obfuscation

### Persistence Module
- Reverse shell installation (cron + systemd)
- Custom cron job injection
- Deadrop C2 payload retrieval via curl

### Resilience Module
- DNS tunneling via nslookup exfiltration
- Data fragmentation with randomized delays

### 🔀 Lateral Movement Module
- Credential harvesting (/etc/passwd, /etc/shadow, SSH keys, AWS credentials)
- Network scanning with nmap

### 🧹 Cleanup Module
- Log wiping (Apache, Nginx, Syslog, Auth)
- Shell history shredding
- Secure file deletion

---

## 6 Upgrade Features (NEW in v7.1)

| No | Feature | Description |
|----|---------|-------------|
| 1 | **Auto Privesc** | Scan SUID, Sudo, Cron, .env, kernel, writable files – **no password required** |
| 2 | **Persistence Auto-Heal** | Watchdog re-installs cron & systemd every 2 minutes if deleted |
| 3 | **Memory Payload** | Inject payload into RAM (memfd) – no disk trace |
| 4 | **Self-Obfuscator** | Encode shell as base64+gzcompress – bypass antivirus |
| 5 | **Log Timestomp** | Modify log timestamps to match reference files |
| 6 | **SSH Key Inject** | Inject public key into all users' `authorized_keys` + root |

---

## Rootkit Toolkit (NEW in v7.1)

- **Install Rootkit:** Spawn hidden process, kill monitoring agents, disable SELinux/AppArmor, set `chattr +i`, LD_PRELOAD persistence, rename process to `[kworker]`
- **Hide + Lock File:** Rename file to hidden (`.filename`) and set immutable
- **Kill Process:** Kill processes by name

---

## Extra Utilities (NEW in v7.1)

- **System Monitor:** View uptime, load, memory, disk, ports, processes, services, I/O, connections
- **Cloud Sync:** Upload files to remote server via POST
- **Process Injection:** Inject commands into running processes via gdb
- **Self Destruct:** Delete all logs + remove the shell file itself

---

## Modern Cyberpunk UI/UX

- Multiple themes (Dark, Midnight, Forest, Ember, Light, Custom)
- Responsive SPA interface
- Startup animations
- Toast notifications
- Custom color system

---

# Requirements

## Web Server
- Apache
- Nginx
- IIS

## PHP Version
- **PHP >= 8.5.5**

## Required Extensions
- `proc_open`
- `exec`
- `shell_exec`
- `openssl`
- `zip`
- `curl` (optional, for Cloud Sync)
- `gdb` (optional, for Process Injection)

## Permissions
The web server user must have read/write access to the target directory.

---

# 🛠️ Installation & Usage

## 1. Deployment

Upload the `shell.php` file (or an obfuscated filename) to the target web server directory.

## 2. Access

Open the tool from your browser:

```txt
http://target-domain.com/path/to/shell.php
```

## 3. Login

Default credentials (**CHANGE IMMEDIATELY**):

```txt
Username: admin
Password: admin123

Username: lab
Password: cyber2024
```

## 4. Security Configuration (Required)

Before deployment:

1. Open `shell.php`
2. Locate the `$USERS` array
3. Replace default passwords with secure hashes

```php
$USERS = [
    'admin' => password_hash('YOUR_NEW_PASSWORD', PASSWORD_DEFAULT),
];
```

(Optional) Restrict access using IP whitelist:

```php
$IP_WHITELIST = ['192.168.1.100', '10.0.0.5'];
```

---

# 🛡️ Best Practices for Red Team / Auditors

1. **Obfuscate** the PHP source before deployment (use Self-Obfuscator feature)
2. **Avoid** suspicious filenames like:
   - `shell.php`
   - `backdoor.php`
3. **Use stealth modules** to minimize footprint
4. **Remove** the file immediately after audits
5. **Minimize** operational footprint
6. **Avoid** exposing session identifiers
7. Use **secure deployment environments** only

---

# 🔄 Changelog

## v7.1 (Current)
- ✅ Full stealth hardening (error suppression, bash history disable)
- ✅ Advanced Modules (Stealth, Persistence, Resilience, Lateral, Cleanup)
- ✅ 6 Upgrade Features (Auto Privesc, Watchdog, Memory Payload, Obfuscator, Timestomp, SSH Inject)
- ✅ Rootkit Toolkit (Install, Hide, Kill)
- ✅ Process Injection, Self Destruct, Cloud Sync, System Monitor
- ✅ Non-interactive sudo scanning
- ✅ Auto-Heal persistence

## v7.0 (Base)
- ✅ Terminal with multi-tab & split
- ✅ File Manager with editor
- ✅ Security & Forensics tools
- ✅ CVE Intelligence (NVD API)
- ✅ Network & OSINT utilities
- ✅ Cryptography & Hashing tools

---

# 🤝 Contributions

Contributions are welcome for:
- Security improvements
- Bug fixes
- UI/UX enhancements
- Detection modules
- Performance optimizations

Please fork the repository and submit a Pull Request.

---

# 📄 License

This project is licensed under the **MIT License**.  
See the `LICENSE` file for more information.

---

## Developer Information

**Developed by:** Xyra-Company / Xyra77  
**Version:** 7.1  
**PHP Requirement:** 8.5.5+  
**Last Updated:** August 2026

---

**🔥 X77Shell PRO v7.1 — Silent. Stealth. Lethal.**

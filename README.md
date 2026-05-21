# XyraShell (X77 Engine)

> **Advanced PHP 8.5 Web Shell for Educational & Security Auditing Purposes**

![Version](https://img.shields.io/badge/version-7.0-purple)
![License](https://img.shields.io/badge/license-MIT-blue)
![PHP](https://img.shields.io/badge/PHP-8.5.5-cyan)
![Security](https://img.shields.io/badge/Security-CSRF+RateLimit-red)

**XyraShell** (powered by the X77 Engine v7) is a modern PHP-based web shell optimized for **PHP 8.5.5**.  
This tool is specifically designed for:

- Educational Cybersecurity Labs
- Red Team Simulations
- Server Maintenance Audits
- Security Research Environments

With a responsive Single Page Application (SPA) interface, XyraShell provides advanced features including file management, multi-tab terminal emulation, real-time vulnerability intelligence (NVD API), forensic analysis, and system security auditing.

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
   XyraShell requires **PHP 8.5.5 or newer** for full compatibility and modern security support.

**By using this software, you acknowledge and accept full responsibility for your actions.**

---

# 🚀 Main Features

## 🖥️ Advanced Terminal Emulator

- Multi-Tab & Split Screen terminal sessions
- Smart autocomplete & command history
- ANSI color support
- Command palette (`Ctrl+P`)
- Ghost text suggestions
- Command queue execution system

---

## 📁 Professional File Manager

- Tree View & Grid/List modes
- Bulk file operations
- Zip & Unzip support
- Built-in code editor
- Syntax highlighting
- Auto-save & multi-tab editing
- Dangerous permission auditor

---

## 🛡️ Security & Forensics Tools

- Access log analyzer
- SQLi/XSS/Shell injection detection
- Brute-force activity detection
- Security header auditing
- SSL/TLS certificate checker
- PHP security checklist
- Permission auditing system

---

## 📋 CVE Intelligence (NVD API)

- CVE lookup by ID
- Vulnerability keyword search
- Real-time recent CVEs
- Severity-based highlighting

---

## 🌐 Network & OSINT Utilities

- Whois lookup
- Reverse IP lookup
- TCP port scanner
- CMS detection system

---

## 🔐 Cryptography & Hashing

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

## 🎨 Modern Cyberpunk UI/UX

- Multiple themes
- Responsive SPA interface
- Startup animations
- Toast notifications
- Custom color system

---

# 📋 Requirements

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

## Permissions
The web server user must have read/write access to the target directory.

---

# 🛠️ Installation & Usage

## 1. Deployment

Upload the `xyrashell.php` file (or an obfuscated filename) to the target web server directory.

---

## 2. Access

Open the tool from your browser:

```txt
http://target-domain.com/path/to/xyrashell.php
```

---

## 3. Login

Default credentials (**CHANGE IMMEDIATELY**):

- Username: `admin`
  Password: `admin123`

- Username: `lab`
  Password: `cyber2024`

---

## 4. Security Configuration (Required)

Before deployment:

1. Open `xyrashell.php`
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

1. Obfuscate the PHP source before deployment
2. Avoid suspicious filenames like:
   - `shell.php`
   - `backdoor.php`

3. Remove the file immediately after audits
4. Minimize operational footprint
5. Avoid exposing session identifiers
6. Use secure deployment environments only

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
**Version:** 7.0  
**PHP Requirement:** 8.5.5+  
**Last Updated:** May 2026

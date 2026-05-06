# RustScanner v2.0

Professional Network Security Scanner with Nmap NSE Integration

---

## Features

- Fast multi-threaded port scanning
- Automatic service detection by port
- Nmap NSE script integration for vulnerability detection
- HTML, JSON, and Terminal output formats
- Custom port ranges and lists
- Risk level classification (HIGH / MEDIUM / INFO)

---

## Requirements

| Requirement | Installation Command |
|-------------|---------------------|
| Rust | `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh` |
| Nmap | `sudo apt install nmap -y` |
| Cargo | Installed with Rust |

---

## Installation

```bash
git clone https://github.com/Hasanpy9871/rustscanner.git
cd rustscanner
cargo build --release

Usage
Basic Scan (Default Ports)
bash

sudo ./target/release/rustscanner -t 192.168.1.1

Scan Specific Ports
bash

sudo ./target/release/rustscanner -t 192.168.1.1 -p 22,80,443,3306

Scan Port Range
bash

sudo ./target/release/rustscanner -t 192.168.1.1 -p 1-1000

Full Vulnerability Scan with HTML Report
bash

sudo ./target/release/rustscanner -t 192.168.1.1 -o html

Fast Scan (No NSE Scripts)
bash

sudo ./target/release/rustscanner -t 192.168.1.1 --no-nse

Generate All Output Formats
bash

sudo ./target/release/rustscanner -t 192.168.1.1 -o all

Command Line Options
Option	Description
-t	Target IP address or domain name
-p	Ports to scan (comma-separated or range)
-o	Output format: terminal, html, json, all
--no-nse	Skip NSE scripts (faster scan)
Output Files
File	Format	Description
rustscan_*.html	HTML	Professional visual report
rustscan_*.json	JSON	Machine-readable data
nmap_scan_*.txt	Text	Raw Nmap output
NSE Scripts Used
Service	Scripts
HTTP/HTTPS	vulners, http-enum, http-title, http-headers
SSH	vulners, ssh-auth-methods, ssh2-enum-algos
FTP	vulners, ftp-anon
MySQL	vulners, mysql-info
SMB	vulners, smb-vuln-*
RDP	vulners, rdp-vuln-ms12-020
VNC	vulners, vnc-info


Example Output

╔══════════════════════════════════════════════════════════════════╗
║                     RUSTSCANNER v2.0                            ║
║              Professional Network Scanner with NSE              ║
╚══════════════════════════════════════════════════════════════════╝

[*] Target: 192.168.1.1
[*] Ports to scan: 14 ports

[*] Scanning 14 ports on 192.168.1.1...
    Port 22 (ssh) is OPEN
    Port 80 (http) is OPEN
    Port 443 (https) is OPEN

[*] Running NSE vulnerability scripts...
  ▶ Running vulners on port 22... [INFO]
  ▶ Running vulners on port 80... [HIGH]

✓ Scan completed
✓ Open ports: 3
✓ Vulnerabilities found: 2 (High: 1)

Disclaimer

This tool is for authorized security testing and educational purposes only. Unauthorized scanning of networks or systems you do not own or have explicit permission to test is illegal. Use responsibly.

License: MIT License

Author: Hasan Ali

GitHub: Hasanpy9871

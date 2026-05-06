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

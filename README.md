 Kali Password Checker

Kali Password Checker is an enterprise-focused password audit and policy compliance tool designed for security assessments, red team engagements, and password policy analysis. It analyzes password lists, calculates entropy metrics, detects weak patterns, evaluates policy compliance, and generates structured reports suitable for automation and CI/CD pipelines.

---

## Features

- Wordlist audit mode  
- Enterprise password policy compliance analysis  
- Weak password percentage detection  
- Average password length calculation  
- Average entropy calculation  
- Common weak pattern detection  
- JSON report export  
- CI/CD-friendly exit codes  
- No external dependencies (Python standard library only)  

---

## Installation

### Install via Debian Package (Recommended)

1. Download the latest release file:

   `kali-password-checker_1.2-1_all.deb`

2. Open a terminal in the directory containing the file.

3. Install the package:

```bash
sudo dpkg -i kali-password-checker_1.2-1_all.deb

If dependency errors occur, fix them:

sudo apt -f install

Verify installation:

kali-password-checker --help

If the help menu appears, installation is successful.

Install from Source

Clone the repository:

git clone https://github.com/erraf132/kali-password-checker.git
cd kali-password-checker
chmod +x kali-password-checker

Run directly:

./kali-password-checker --help
Usage
Basic Password File Audit
kali-password-checker --file passwords.txt
Enterprise Policy Audit

Policy format:

length,uppercase_required,digit_required,symbol_required

Example (minimum 12 characters, require uppercase, digit, and symbol):

kali-password-checker --file passwords.txt --policy 12,1,1,1
Export Results to JSON
kali-password-checker --file passwords.txt --json report.json

The file report.json will contain structured audit results.

Example Output
=== Audit Results ===
total_passwords: 14344374
weak_passwords: 4737442
weak_percentage: 33.03
average_length: 8.75
average_entropy: 42.46
patterns_detected: {'common_pattern': 78842}
policy_compliance_percentage: 0.13
Exit Codes

0 → Acceptable password distribution

1 → Weak password percentage exceeds 30%

This enables integration in CI/CD and automated security testing workflows.

License

MIT License

Copyright (c) 2026 Erik Vuagniaux

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files to deal in the Software without restriction.

Disclaimer

This tool is intended for authorized security testing, research, and enterprise password audits only. Use exclusively on data you are permitted to analyze.

 ForenX — Cross-Platform Digital Forensics Framework


A powerful, modular digital forensics tool for acquiring, analyzing, and reporting evidence across Windows, macOS, and Linux systems.




📌 Overview

ForenX is an open-source digital forensics framework designed for investigators, security researchers, and incident responders. It automates the full forensic workflow — from evidence acquisition to in-depth analysis and professional report generation — all from a single, unified tool that works seamlessly across operating systems.

Whether you're investigating a compromised Windows endpoint, a macOS workstation, or a Linux server, ForenX gives you the visibility you need.


✨ Features

🗂️ Acquisition


Disk imaging and file copying with integrity tracking
Automated OS-specific log collection (Windows Event Logs, macOS system logs, Linux auth logs)
Supports multi-platform log gathering in a single run


🔬 Analysis


Windows EVTX Parsing — Parse and extract Windows Security Event logs
Linux Auth Log Parsing — Analyze /var/log/auth.log for suspicious login activity
macOS Login Log Parsing — Extract login/logout events from macOS system logs
Login Event Correlation — Cross-platform logon event analysis (Windows + macOS)
Browser History Extraction — Parse Chrome history from both Windows and macOS
Running Application Snapshots — Capture currently running processes on Windows and macOS
File Metadata Analysis — Extract timestamps, permissions, and ownership metadata
YARA Scanning — Scan acquired files against custom YARA rules for malware detection


📊 Reporting


PDF Reports — Structured case reports with full analysis summaries
HTML Dashboard — Interactive visual dashboard for reviewing findings at a glance



🛠️ Tech Stack


Language: Python 3.x
Supported Platforms: Windows, macOS, Linux
Key Libraries: python-evtx, yara-python, pathlib, and more



📁 Project Structure

ForenX/
├── main.py                  # Entry point — runs the full workflow
├── acquisition/
│   ├── disk_imager.py       # Disk/file copying
│   └── log_collector.py     # OS-specific log collection
├── analysis/
│   ├── evtx_parser.py       # Windows Event Log parser
│   ├── linux_log_parser.py  # Linux auth log parser
│   ├── login_parser.py      # Cross-platform login event parser
│   ├── browser_history.py   # Chrome history extractor
│   ├── app_usage.py         # Running apps snapshot
│   ├── file_metadata.py     # File metadata extractor
│   └── yara_scanner.py      # YARA rule scanner
├── reporting/
│   ├── report_gen.py        # PDF report generator
│   └── html_dashboard.py    # HTML dashboard generator
├── rules/
│   └── test_rules.yar       # Sample YARA rules
├── sample_data/
│   └── sample_disk.txt      # Sample disk image for testing
├── utils/
│   └── logger.py            # Centralized logging utility
└── output/                  # Generated output (auto-created)
    ├── acquired_data/
    ├── analysis_results/
    └── reports/


🚀 Getting Started

Prerequisites


Python 3.8+
pip


Installation

bashgit clone https://github.com/abhilekhkar/ForenX.git
cd ForenX
pip install -r requirements.txt

Running ForenX

bashpython main.py

Output will be saved to the output/ directory:


output/acquired_data/ — Collected logs and disk images
output/reports/report.txt — PDF case report
output/reports/dashboard.html — HTML visual dashboard



⚙️ Configuration

SettingLocationDefaultYARA Rulesrules/test_rules.yarSample rules includedSample Disksample_data/sample_disk.txtIncluded for testingOutput Directorymain.py → OUTPUT_DIR./output


📸 Workflow

Acquisition  ──►  Analysis  ──►  Reporting
   │                  │               │
Disk Image        EVTX/Log         PDF Report
Log Collection    YARA Scan        HTML Dashboard
                  Browser Hist
                  Login Events
                  App Snapshots


🧪 Testing

Place your sample logs in the appropriate paths before running:

Log TypeExpected PathLinux Auth Logoutput/acquired_data/logs/linux_auth.logWindows EVTXoutput/acquired_data/logs/sample.evtxmacOS Login Logoutput/acquired_data/logs/mac_login.logChrome History (Mac)output/acquired_data/Chrome_History_MacChrome History (Win)output/acquired_data/Chrome_History_Win


🛡️ Disclaimer


ForenX is intended for lawful forensic investigations only. Always ensure you have proper authorization before acquiring or analyzing data from any system. Unauthorized access to computer systems is illegal.




🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request.


Fork the repository
Create a feature branch (git checkout -b feature/your-feature)
Commit your changes (git commit -m 'Add your feature')
Push to the branch (git push origin feature/your-feature)
Open a Pull Request




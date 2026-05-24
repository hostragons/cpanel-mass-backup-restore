# 🚀 cPanel Mass Backup Restore Script

Professional cPanel/WHM mass backup restore automation tool by **Hostragons Global Limited**.

This script is designed for system administrators, hosting providers, migration specialists, and server engineers who need to restore multiple cPanel accounts quickly and safely.

Built with performance and reliability in mind, this script automates the entire restore workflow using native cPanel restore functionality while providing parallel processing, automatic recovery, resume support, logging, timeout protection, and an interactive interface.

---

# ⚡ Quick Start

Run directly without downloading files manually:

```bash
bash <(curl -fsSL https://cdn.hostragons.com/storage/bash/cpanel_restore_hostragons.sh)
```

or:

```bash
sudo bash <(curl -fsSL https://cdn.hostragons.com/storage/bash/cpanel_restore_hostragons.sh)
```

---

# 📌 What Does This Script Do?

The script automatically:

✔ Detects cPanel environment  
✔ Verifies root access  
✔ Detects backup directories  
✔ Finds available backup dates  
✔ Lets user choose restore source  
✔ Restores multiple accounts simultaneously  
✔ Handles timeout issues  
✔ Automatically retries failed restores  
✔ Supports resume after interruption  
✔ Generates detailed logs  
✔ Creates final restore reports  

---

# ✨ Main Features

## Parallel Restore Engine

Instead of restoring accounts one by one, the script can restore multiple accounts simultaneously.

Recommended values:

| Storage Type | Recommended Slots |
|-------------|-------------------|
| HDD | 2 |
| SSD | 3 |
| NVMe | 4–6 |

Benefits:

- Faster migration
- Better resource utilization
- Reduced total restore time

---

## Automatic Backup Detection

Supports automatic detection of:

```text
/backup
/home/backup
/mnt/storage
/custom/path
```

Example:

```text
/backup/
└── 2026-05-24/
    └── accounts/
        ├── cpmove-user1.tar.gz
        ├── cpmove-user2.tar.gz
        ├── cpmove-user3.tar.gz
        └── cpmove-user4.tar.gz
```

No need to manually define account names.

---

## Resume Support

If the script stops because of:

- SSH disconnect
- Server reboot
- User interruption
- Network issues

it automatically remembers completed accounts.

Run the same command again:

```bash
bash <(curl -fsSL https://cdn.hostragons.com/storage/bash/cpanel_restore_hostragons.sh)
```

The script continues from where it stopped.

---

## Watchdog Protection

Large accounts sometimes freeze during restore operations.

The watchdog system:

- Monitors restore process
- Detects hangs
- Stops frozen processes
- Continues automatically

Example:

```text
Timeout: 600 seconds
```

---

## Automatic Retry System

Failed accounts are not ignored.

The script:

- Stores failed accounts
- Retries automatically
- Performs multiple attempts
- Generates detailed reports

This significantly reduces manual work.

---

## Detailed Logging System

Logs are generated automatically:

```text
/var/log/cpanel_restore
```

Examples:

```text
main_20260524_142011.log
worker_user1.log
worker_user2.log
worker_user3.log
```

Logs help with:

- Debugging
- Migration tracking
- Error analysis
- Audit history

---

## State Tracking System

Progress information is stored here:

```text
/var/tmp/cpanel_restore_state
```

Files:

```text
done.txt
failed.txt
done_count.txt
fail_count.txt
counter.lock
```

Reset progress:

```bash
rm -rf /var/tmp/cpanel_restore_state
```

---

# 🔧 Requirements

Before running the script:

### Required

- Linux Server
- Root access
- cPanel/WHM
- Existing restore command:

```bash
/scripts/restorepkg
```

- Valid cPanel backup files:

```text
cpmove-user.tar.gz
```

---

# 📂 Supported Backup Formats

Supported:

```text
cpmove-user.tar.gz
user.tar.gz
```

---

# 🖥 Example Workflow

Step 1:

Run:

```bash
bash <(curl -fsSL https://cdn.hostragons.com/storage/bash/cpanel_restore_hostragons.sh)
```

Step 2:

Select backup directory:

```text
/backup
```

Step 3:

Choose detected backup date:

```text
[1] 2026-05-24
[2] 2026-05-23
[3] 2026-05-22
```

Step 4:

Choose parallel slot count:

```text
4
```

Step 5:

Choose timeout:

```text
600
```

Step 6:

Restore starts automatically.

---

# 📊 Final Report Example

```text
╔══════════════════════════════╗
║        FINAL REPORT          ║
╚══════════════════════════════╝

Total Accounts : 150
Successful     : 145
Failed         : 5
Total Time     : 00:21:44
```

---

# 🏢 About Hostragons

Hostragons Global Limited provides enterprise-grade hosting infrastructure and server solutions.

Company Information:

Company Name:

Hostragons Global Limited

Company Number:

14320956

Founded:

2020

Relocated:

2022 → London

Headquarters:

London, United Kingdom

Address:

71–75 Shelton Street  
Covent Garden  
London  
WC2H 9JQ  
United Kingdom

Website:

https://www.hostragons.com/en/

Contact:

https://www.hostragons.com/en/contact

Client Area:

https://my.hostragons.com/

WhatsApp:

+44 7367 063425

Telegram:

https://t.me/hostragons

---

# ⚠ Disclaimer

This script performs real cPanel account restore operations.

Always:

- Test with a small number of accounts first
- Verify backups before production use
- Run with root privileges
- Maintain external backups

The author assumes no responsibility for data loss, server issues, or improper use.

---

# 📜 License

MIT License

---

Made with ❤️ by Hostragons Global Limited

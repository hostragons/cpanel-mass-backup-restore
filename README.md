# cPanel Mass Backup Restore Script

Professional cPanel/WHM mass backup restore automation script by **Hostragons Global Limited**.

This tool is designed to restore multiple cPanel backup accounts from `.tar.gz` backup files using `/scripts/restorepkg`. It includes parallel restore support, automatic date folder detection, resume mode, retry handling, watchdog timeout protection, detailed logging, and a clean interactive terminal interface.

## Quick Install & Run

Run the script directly with:

```bash
bash <(curl -fsSL https://cdn.hostragons.com/storage/bash/cpanel_restore_hostragons.sh)

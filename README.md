# SinoDesk for Windows

Public installers and automatic-update metadata for SinoDesk, a Windows desktop workspace connected to SinoHR.

[Download the latest Windows x64 installer](https://github.com/arhamsadaf7-commits/SinoDesk-Releases/releases/latest)

## Existing users: one-time upgrade to 1.4.7

The updater signing key has changed after loss of the original encrypted key. Version 1.4.6 and earlier cannot automatically accept a package signed by the new key. They keep their verified 1.4.6 update feed; their signature checks have not been disabled.

1. Exit SinoDesk completely, including its system-tray process. **Do not uninstall, sign out or clear application data.**
2. Download [the 1.4.7 installer](https://github.com/arhamsadaf7-commits/SinoDesk-Releases/releases/download/v1.4.7/SinoDesk_1.4.7_x64-setup.exe) and [Upgrade-SinoDesk.ps1](https://github.com/arhamsadaf7-commits/SinoDesk-Releases/releases/download/v1.4.7/Upgrade-SinoDesk.ps1) into the same folder from the official release. SHA256SUMS is available for independent verification.
3. Open PowerShell in that folder and run:

   ```powershell
   powershell.exe -NoProfile -ExecutionPolicy Bypass -File .\Upgrade-SinoDesk.ps1
   ```

   The helper verifies the installer hash, makes and verifies a private backup of the existing app-data folders, runs in-place update mode, and checks that the original data files are unchanged. It stops if the app is running or backup verification fails. The PowerShell policy setting applies only to this process.
4. Open SinoDesk, unlock/sign in normally, go online, and synchronize Employees. The new company/subcontractor policy requires the normal authorized employee download.

Version 1.4.7 and later use the new `latest-v2.json` verified update feed. Future updates can download automatically; installation/restart still waits for your confirmation. The legacy `latest.json` remains the original 1.4.6 manifest byte for byte so older clients do not attempt a new-key update. Keep local data and Windows credentials in place throughout the one-time upgrade.

Each current release includes the installer, its Tauri updater signature, both feed manifests, the safe-upgrade helper, SHA-256 checksums and verification metadata. Application identity, encrypted data format, account isolation, permissions and downgrade protections remain unchanged.

These initial installers do not have a paid Windows Authenticode certificate, so Windows may report an unknown publisher. The app independently verifies update signatures and signed release versions before installation.

Application source and operational credentials are maintained separately. No signing private key, account credentials or employee data is hosted here.
Public SinoDesk Windows installers and verified automatic-update metadata. Application source is maintained separately.

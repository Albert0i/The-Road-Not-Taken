
# 📘 Migration Guide: Garmin Express Device Info

## 1. Locate Device Metadata
On **Computer 1 (source)**:

- **Windows**  
  ```
  C:\ProgramData\Garmin\CoreService\Devices
  ```
- **macOS**  
  ```
  /Library/Application Support/Garmin/CoreService/Devices
  ```

Inside this folder:
- Subfolders named by device ID/serial number.
- Each contains:
  - `Device.xml` → Metadata (model, serial, firmware, last sync).
  - `Backup` folder → Up to 3 backup files per device.
  - Download references for maps/firmware.

---

## 2. Copy Device Metadata
- Copy the **entire `Devices` folder** (including all subfolders/files).
- Paste it into the same location on **Computer 2 (target)**.

---

## 3. Optional: Copy Map/Firmware Downloads
To avoid re‑downloading large files, also copy:

- **Windows**  
  ```
  C:\ProgramData\Garmin\CoreService\Downloads
  ```
- **macOS**  
  ```
  /Library/Application Support/Garmin/CoreService/Downloads
  ```

This preserves cached maps and firmware updates.

---

## 4. Understand What Migrates
- ✅ Device recognition (serial, model, firmware info).  
- ✅ Backups and cached downloads.  
- ❌ Account credentials (username/password or tokens).  

Account credentials are stored separately:
- **Windows** → Windows Credential Manager (encrypted).  
- **macOS** → Keychain.  
These cannot be copied between computers.

---

## 5. First Run on Computer 2
- Plug in your device → Express recognizes it from the copied metadata.  
- Express will **prompt for Garmin Connect sign‑in once**, because the account token isn’t portable.  
- After signing in, Computer 2 caches its own token and syncs automatically going forward.

---

## ✅ Bottom Line
- Copy `CoreService\Devices` (and optionally `CoreService\Downloads`) to migrate device info and cached updates.  
- You **must still sign in once** on Computer 2 to establish the account link.  
- After that, syncing will be seamless, just like on Computer 1.

---

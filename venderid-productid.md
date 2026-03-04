
## 🧭 Guide: Find USB Vendor ID and Product ID on Linux

### 1. Plug in your device
Connect your iPhone or Garmin device to your computer via USB.

### 2. Open a terminal and run:
```bash
lsusb
```

This lists all USB devices currently connected. Look for a line like:

- **iPhone**:
  ```
  Bus 001 Device 005: ID 05ac:12a8 Apple, Inc. iPhone
  ```
- **Garmin**:
  ```
  Bus 001 Device 006: ID 091e:0003 Garmin International
  ```

### 3. Interpret the output
- **Vendor ID** = first part after `ID` → `05ac` (Apple), `091e` (Garmin)  
- **Product ID** = second part → `12a8` (iPhone model), `0003` (Garmin model)

### 4. Optional: Get detailed info
```bash
lsusb -v | less
```
This shows verbose details for each device. Use `/Apple` or `/Garmin` to search inside the output.

---

✅ With these IDs, you can create precise USB filters in VirtualBox to automatically pass your devices to the Windows 11 guest.

---

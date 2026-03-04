# 🧭 Guide: Find USB Vendor ID and Product ID on Linux (with Notes on Extra Filter Fields)

When setting up **VirtualBox USB passthrough** for devices like an iPhone or Garmin on Zorin OS (Linux), you need the **Vendor ID** and **Product ID**. Here’s how to find them and how to handle the other filter fields.

---

## 1. Plug in Your Device
Connect your iPhone or Garmin device to your computer via USB.

---

## 2. Run `lsusb` to List Devices
Open a terminal and type:

```bash
lsusb
```

You’ll see output like:

- **iPhone**:
  ```
  Bus 001 Device 005: ID 05ac:12a8 Apple, Inc. iPhone
  ```
- **Garmin**:
  ```
  Bus 001 Device 006: ID 091e:0003 Garmin International
  ```

---

## 3. Interpret the Output
- **Vendor ID** = first part after `ID` → `05ac` (Apple), `091e` (Garmin)  
- **Product ID** = second part → `12a8` (iPhone model), `0003` (Garmin model)

---

## 4. Optional: Get Detailed Info
For verbose details:

```bash
lsusb -v | less
```

Use `/Apple` or `/Garmin` to search inside the output.

---

## 5. About Extra USB Filter Fields in VirtualBox
When adding a USB filter in VirtualBox, you’ll see fields beyond Vendor ID and Product ID:

- **Revision** → Device firmware/hardware revision. Leave blank unless you want to restrict to a specific revision.  
- **Port No. / Port** → Physical USB port on the host. Leave blank for flexibility; otherwise, the filter only works on one port.  
- **Remote** → Used for remote USB devices (e.g., over RDP). Not needed for local iPhone/Garmin connections.  

👉 **Practical advice**: For iPhone and Garmin passthrough, you only need **Vendor ID and Product ID**. Leave the other fields blank to keep the filter flexible.

---

✅ With these IDs and filter settings, you can configure VirtualBox to automatically pass your iPhone or Garmin device to the Windows 11 guest, ensuring iTunes or Garmin Express detects them reliably.  

---


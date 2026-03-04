# 🖥️ Guide: Checking and Configuring iPhone USB Passthrough in VirtualBox (Zorin Host, Windows 11 Guest)

Running **Windows 11 inside VirtualBox on Zorin OS** and connecting an iPhone requires careful USB passthrough setup. This guide shows you how to check whether the device is controlled by the **host (Zorin)** or the **guest (Windows 11 VM)**, and how to configure a **USB filter** so the iPhone is automatically passed to the VM.

---

## 1. Check if iPhone is Connected to the Host (Zorin OS)

Open a terminal in Zorin and run:

```bash
lsusb
```

- If you see something like:
  ```
  Bus 001 Device 005: ID 05ac:12a8 Apple, Inc. iPhone
  ```
  → The **host OS (Zorin)** currently has control of the iPhone.  
- If Zorin mounts the iPhone (e.g., as a camera or MTP device), you may need to **unmount it** before VirtualBox can capture it.

---

## 2. Check if iPhone is Connected to the Guest (Windows 11 VM)

Inside the Windows 11 VM:

- Open **Device Manager** (`Win + X → Device Manager`).  
- Look under **Portable Devices** or **Universal Serial Bus controllers**.  
- If the iPhone appears there, the VM has successfully captured it.  
- Then open **iTunes** → the iPhone should show up for sync/backup.

---

## 3. Configure VirtualBox USB Passthrough

To enable USB passthrough:

1. Install the **VirtualBox Extension Pack** (adds USB 2.0/3.0 support).  
2. Add your user to the `vboxusers` group:
   ```bash
   sudo usermod -aG vboxusers $USER
   ```
   (Log out and back in afterward.)  
3. In VirtualBox Manager → VM Settings → **USB** → Enable **USB 3.0 (xHCI)**.  

---

## 4. Adding a [USB Filter](usb-filter.md) (Detailed Steps)

A USB filter ensures the iPhone is automatically handed to the VM whenever it’s running:

1. In VirtualBox Manager, select your Windows 11 VM → click **Settings**.  
2. Go to the **USB** section.  
   - Check **Enable USB Controller**.  
   - Select **USB 3.0 (xHCI)**.  
3. Click the **+ (Add Filter)** button.  
   - A list of connected USB devices appears.  
   - Select your iPhone (usually listed as “Apple Inc. iPhone”).  
4. VirtualBox creates a filter entry with the iPhone’s **Vendor ID (05ac)** and **Product ID**.  
   - Leave other fields blank for flexibility.  
5. Save settings and start the VM.  
   - VirtualBox will now automatically capture the iPhone for the guest OS.  

---

## ✅ Quick Diagnostic Flow

- Run `lsusb` on Zorin:  
  - If iPhone shows → Host has it.  
  - If it disappears after VM starts → Guest has it.  
- Inside Windows 11 → Device Manager → iPhone should appear.  
- Open iTunes → iPhone should be recognized for backup/sync.

---


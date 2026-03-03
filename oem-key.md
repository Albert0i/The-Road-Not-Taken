# 📖 Guide: How to Check and Back Up Your OEM Key with ShowKeyPlus

Here’s a simple, safe way to view and save your **OEM Windows 11 product key** using the lightweight tool **ShowKeyPlus**.

---

## 📥 Download ShowKeyPlus
- **Microsoft Store (official)**: ShowKeyPlus – Microsoft Store [(apps.microsoft.com in Bing)](https://apps.microsoft.com/detail/9pkvzcprx9nv?hl=en-US&gl=US)  
- Free, lightweight, and safe to use.

---

## 🛠️ Step‑by‑Step Instructions

1. **Install ShowKeyPlus**
   - Open the Microsoft Store link above.  
   - Click **Get** to install it on your ASUS notebook.

2. **Run the Utility**
   - Launch ShowKeyPlus.  
   - It will immediately display:
     - **Installed Key** → the key currently in use by Windows.  
     - **OEM Key** → the key embedded in BIOS/UEFI.  
     - **Edition** → e.g., Windows 11 Home OEM.

3. **Copy the OEM Key**
   - Highlight the OEM key shown.  
   - Copy it into a text file (e.g., `OEM_Win11_Key.txt`).  
   - Save the file securely (external drive, encrypted cloud folder, or print it out).

4. **Verify Your Backup**
   - Double‑check the saved file matches the key shown in ShowKeyPlus.  
   - Keep it safe — this is your backup in case you ever need to manually enter it.

---

## ⚠️ Notes
- The OEM key is **hardware‑bound** — it will only activate Windows on this notebook.  
- Even without backing it up, Windows setup will auto‑detect it from BIOS/UEFI during reinstall.  
- Backing it up is just an extra layer of peace of mind.

---

👉 With this guide, you now have a reliable way to **see and save your OEM key**.  

---

Open Command Prompt and Run:
```
wmic path softwarelicensingservice get OA3xOriginalProductKey
```
If your OEM key is stored in BIOS/UEFI, it will be displayed.



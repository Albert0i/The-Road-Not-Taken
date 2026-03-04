A **USB filter** in VirtualBox is essentially a rule that tells the hypervisor: *“Whenever this specific USB device is plugged in, give it directly to the guest VM instead of the host.”*  

---

## Why You Need a USB Filter
- **Automatic capture**: Without a filter, the host OS (Zorin) will usually grab the iPhone first. You’d then have to manually attach it to the VM each time.  
- **Consistency**: A filter ensures the iPhone always goes to the Windows 11 guest when the VM is running, so iTunes sees it immediately.  
- **Avoid conflicts**: If the host mounts the iPhone (e.g., as a camera or MTP device), it can block VirtualBox from passing it through. A filter prevents this tug‑of‑war.  
- **Convenience**: Saves you from opening the VirtualBox menu and re‑attaching the iPhone every time you plug it in.

---

## What Happens If You Don’t Add a Filter
- The iPhone will connect to the **host (Zorin)** by default.  
- You’d need to manually go to **Devices → USB → Apple iPhone** in the VirtualBox VM menu each time to attach it.  
- If you forget, iTunes in the guest won’t see the iPhone.  
- In some cases, the host may lock the device, making it harder for the VM to capture it at all.

---

👉 In short: **A USB filter is not strictly required, but it makes the process seamless and reliable. Without it, you’ll have to manually attach the iPhone every time, and risk conflicts with the host OS.**

---


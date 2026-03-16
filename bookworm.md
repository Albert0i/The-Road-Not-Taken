
# 🖋 Debian Bookworm on Chromebook: Packages, Disk Size, and Package Managers

Chromebooks, once seen as lightweight web devices, have become surprisingly versatile thanks to **Crostini**, Google’s Linux container system. With Crostini, you can run a full **Debian Bookworm** environment inside ChromeOS, giving you access to CLI tools, development stacks, and productivity utilities.  

But your Chromebook has **64 GB total storage, ~35 GB free**, and you’ve decided to allocate **15 GB maximum** for Debian. That’s a tight chamber, so every package must be chosen carefully. This guide organizes recommendations into **domestic, development, productivity, and miscellaneous** categories, while keeping disk usage lean. It also explains which package manager is best for your limited resources.  

---

## ⚖️ Disk Size Strategy for 15 GB

Here’s how the 15 GB allocation breaks down:  
- **Base Debian container:** ~2–3 GB.  
- **Domestic tools:** <200 MB.  
- **Development stack (Node.js, Python, compilers, DB clients):** ~2–3 GB.  
- **Productivity tools:** ~1 GB.  
- **Miscellaneous tools:** <200 MB.  
- **User projects:** ~7–8 GB free for code, documents, and updates.  

This balance ensures you won’t run out of space while still having a functional toolkit.  

---

## 🏠 Domestic Packages (Daily Comfort)

**Recommended:**  
- `vim` or `nano` → text editing.  
- `htop` → monitor processes.  
- `mc` (Midnight Commander) → CLI file manager.  
- `neofetch` → system info.  
- `tree` → directory visualization.  

**Install:**  
```bash
sudo apt install vim htop mc neofetch tree -y
```

---

## 💻 Development Packages (Node.js Stack)

**Recommended:**  
- `nodejs` → runtime.  
- `npm` → package manager.  
- `yarn` → alternative package manager.  
- `nvm` → Node Version Manager (installed via script).  
- `git` → version control.  
- `build-essential` → compilers and headers.  
- `python3` + `python3-pip` → required for some Node modules.  
- `sqlite3` → lightweight DB.  
- `postgresql-client` or `mariadb-client` → optional DB clients.  
- `jq` → JSON processor.  

**Install:**  
```bash
sudo apt install nodejs npm yarn git build-essential python3 python3-pip sqlite3 jq -y
```

For **nvm**:  
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source ~/.bashrc
```

---

## 📑 Productivity Packages (Efficiency Tools)

**Recommended:**  
- `ripgrep` → fast text search.  
- `fzf` → fuzzy finder.  
- `pandoc` → document conversion.  
- `texlive-base` → minimal LaTeX support.  
- `lynx` or `w3m` → text‑based web browsing.  

**Install:**  
```bash
sudo apt install ripgrep fzf pandoc texlive-base lynx -y
```

---

## 🎲 Miscellaneous Packages (Extras & Exploration)

**Recommended:**  
- `fortune` + `cowsay` → fun CLI messages.  
- `nmap` → network scanning.  
- `gnupg` → encryption/signing.  

**Install:**  
```bash
sudo apt install fortune cowsay nmap gnupg -y
```

---

## 📦 Package Managers: Apt vs Snap vs Flatpak

Chromebooks are limited in resources, so choosing the right package manager matters.  

### ✅ Apt (Debian’s native manager)
- **Lightweight footprint**: No extra runtimes.  
- **Efficient storage use**: Perfect for 15 GB allocation.  
- **Stable and integrated**: Designed for Debian.  
- **Best for CLI tools**: Node.js, git, htop, sqlite, etc.  

### 📦 Snap
- **Pros**: Sandboxed apps, auto‑updates.  
- **Cons**: Heavy disk usage, slower startup, not tightly integrated with Debian.  
- **Verdict**: Not recommended for a 15 GB container.  

### 📦 Flatpak
- **Pros**: Access to Flathub, newer GUI apps.  
- **Cons**: Large runtimes, heavier storage use.  
- **Verdict**: Useful for GUI apps, but Crostini is mostly CLI — adds overhead you don’t need.  

### 🛠 Practical Recommendation
- Use **apt** for all core packages.  
- Use **nvm** for Node.js version flexibility.  
- Avoid Snap and Flatpak unless you later need GUI apps unavailable in apt.  

---

## 🛠 Installation Workflow

1. **Update package lists:**  
   ```bash
   sudo apt update
   ```
2. **Upgrade existing packages:**  
   ```bash
   sudo apt upgrade -y
   ```
3. **Install chosen packages:**  
   Example:  
   ```bash
   sudo apt install vim git nodejs npm -y
   ```
4. **Verify installations:**  
   ```bash
   node -v
   npm -v
   git --version
   ```
5. **Clean up:**  
   ```bash
   sudo apt autoremove -y
   sudo apt clean
   ```

---

## 🌌 Ceremonial Perspective

Your Chromebook’s Debian container is a **small chamber carved inside ChromeOS**. With only 15 GB, you must inscribe scrolls carefully:  
- Domestic scrolls for comfort.  
- Development scrolls for your Node.js forge.  
- Productivity scrolls for efficiency.  
- Miscellaneous scrolls for joy and exploration.  

The chamber is modest, but balanced. Apt is the **scribe of Debian**, inscribing scrolls directly with precision. Snap and Flatpak are wandering scribes who bring exotic scrolls, but each demands extra space. In a small chamber, the native scribe is the wisest companion.  

---

## 📜 Conclusion

With a **15 GB disk allocation**, you can still build a lean, powerful Debian Bookworm environment on your Chromebook. By curating packages into domestic, development, productivity, and miscellaneous categories, and sticking with apt as your package manager, you balance functionality with storage constraints.  

- Domestic tools make daily use comfortable.  
- Development tools build your Node.js stack.  
- Productivity tools keep you efficient.  
- Miscellaneous tools add personality.  
- Apt ensures stability and efficiency, while nvm gives Node.js flexibility.  

This curated set ensures your Chromebook becomes a **ritual workstation** — compact yet complete, a chamber where scrolls of code, documents, and utilities coexist in harmony.  


# 🧭 Setup Internet Explorer 8 on Wine

---

## 📜 Full Script

```bash
# 1. Create the dedicated Wine prefix folder
md ie8
cd ie8

# 2. Export the WINEPREFIX variable so all commands target this prefix
export WINEPREFIX=/home/alberto/ie8


# 3. Initialize the prefix as 32-bit using Winetricks
wineboot -i
winetricks arch=32

# 4. Install Internet Explorer 8 into this prefix
winetricks ie8

# 5. Apply the IE8 security update (KB2936068)
winetricks ie8_kb2936068

# 6. Launch Internet Explorer 8 from inside the prefix
wine "C:\\Program Files\\Internet Explorer\\iexplore.exe"
```

---

## 💾 Estimated Disk Size
- **Wine prefix (32‑bit)**: ~200–300 MB  
- **Internet Explorer 8 install**: ~70–100 MB  
- **Security update + supporting libraries**: ~50 MB  
- **Total**: ~350–450 MB inside `/home/alberto/ie8`

---

## You then need to turn down all security options (Tools -> Internet Options -> Security)

[Internet Explorer 8.0 for Windows Vista and Windows Server 2008 (32-bit)](https://appdb.winehq.org/objectManager.php?sClass=version&iId=17187)

**Got ActiveX working
by morty on Sunday November 27th 2022, 13:06**
```
winetricks arch=32 prefix=ie
export WINEPREFIX=/home/morty/.local/share/wineprefixes/ie
winetricks ie8
winetricks ie8_kb2936068
wine "C:\Program Files\Internet Explorer\iexplore.exe"
```

You then need to turn down all security options (Tools -> Internet Options -> Security)


---
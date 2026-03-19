# User Quick-Start Guide

## Installation (60 seconds)

1. **Download** `Audio_Config.exe` from GitHub Releases
2. **Save** to any folder (Desktop is fine)
3. **Done!** No installer needed

## First Run

1. **Right-click** `Audio_Config.exe`
2. Select **"Run as administrator"**
3. Click **"Yes"** when Windows asks
4. A dialog will appear - click **OK**

## What It Does

### Full Configuration
Solves the audio volume drop issue + optimizes power & removes notifications
```
Run: Audio_Config.exe
```

### Audio Only
Just fixes the audio jack volume issue
```
Run: Audio_Config.exe /audio
```

### Power Only
Just optimizes power settings
```
Run: Audio_Config.exe /power
```

### Test Mode (Safe)
See what would change without making changes
```
Run: Audio_Config.exe /dry
```

### Replace Audio Driver
Uninstalls HP Realtek driver, installs generic driver (restarts computer)
```
Run: Audio_Config.exe /driver
```

### Disable Notifications
Turns off Windows Update, Store, Tips, Defender alerts
```
Run: Audio_Config.exe /notifications
```

## The Audio Problem (and how this fixes it)

**Problem**: When you plug in headphones, the volume drops to ~35%
- This is HP's audio driver automatically reducing volume
- It happens every time you connect headphones
- Very annoying for audio professionals

**Solution**: This tool disables that behavior by:
1. Changing audio driver settings so the jack is treated as a speaker port
2. Preventing the system from detecting when headphones are plugged in
3. Keeping volume at 100% permanently

**Result**: Volume stays at 100% when headphones are connected ✓

## Logs & Troubleshooting

All changes are logged to:
```
C:\Users\Public\Maas-Rowe\Logs\Bellwether.log
```

**Having issues?**
1. Open the log file to see exactly what happened
2. Check the README.md for detailed troubleshooting
3. Run in dry-mode first (`/dry` flag) to see what would change

## Support

- **Questions?** Contact Maas-Rowe Carillons
- **GitHub Issues?** Report on the repository
- **Still having audio issues?** Try the `/driver` flag to replace the audio driver

## Summary

✅ Download `Audio_Config.exe`
✅ Right-click → Run as administrator
✅ Click OK on the dialog
✅ Done! Your system is optimized for Bellwether

That's it! The tool handles all the complex registry changes automatically.

---

For advanced users, see the full README.md for all configuration options.

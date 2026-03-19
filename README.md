# Bellwether System Configurator

A comprehensive Windows system configuration utility optimized for **professional audio systems** and performance audio workstations.

## Overview

The Audio Configuration tool automates critical system configuration settings for optimal audio performance, power management, and user experience. It eliminates unnecessary system overhead, disables distracting notifications, and resolves audio jack volume reduction issues that commonly affect professional audio systems.

## Intended Clients

- **Audio Professionals** - Audio engineers, technicians, and producers
- **Studio Owners** - Professional audio recording and mixing studios
- **Performance Audio Systems** - Any high-fidelity audio workstations
- **System Integrators** - Professionals setting up audio workstations
- **Maas-Rowe Carillons** - Bellwether performance audio system users

## Key Features

### 🎵 Audio Configuration
- **Jack Detection Disabling** - Prevents automatic volume reduction when headphones are connected
- **Realtek Driver Optimization** - Disables problematic HP-customized audio drivers
- **Generic HD Audio Support** - Automated driver replacement with generic Windows drivers
- **EnableDynamicDevices Setting** - Forces audio jack to remain as permanent line-out port
- **System Sounds Removal** - Eliminates all Windows system notification sounds
- **Auto-Volume Reduction Disabled** - Removes all automatic volume adjustment mechanisms

### ⚡ Power Management
- **Screen Rotation Disabled** - Prevents unwanted display orientation changes
- **Lid Close Customization** - No action on lid close for AC and battery power
- **AC Power Optimization** - Screen never blanks, system never sleeps on AC
- **Battery Power Settings** - 4-hour screen timeout, 15-hour sleep timeout
- **Low Battery Handling** - System sleeps at 5% battery
- **Hibernation Enabled** - Extended battery life support

### 🔔 Notification Control
- **Windows Update Alerts Disabled** - No update notifications
- **Microsoft Store Silenced** - No app delivery notifications
- **Tips & Tricks Removed** - Eliminates Windows tip popups
- **Action Center Disabled** - No notification suggestions
- **Defender Notifications Reduced** - Minimized security alerts
- **Consumer Features Disabled** - No Cortana suggestions or ads

### 📋 System Features
- **Comprehensive Logging** - All changes logged to file with timestamps
- **Dry-Run Mode** - Test configuration without applying changes
- **Selective Configuration** - Apply only desired configuration modules
- **Administrator Integration** - Seamless Windows administrator elevation
- **Error Handling** - Graceful error handling with detailed reporting

## Installation

### Download
1. Download `Audio_Config.exe` from the [Releases](https://github.com/Maas-Rowe/Audio-Configuration-Modification-App/releases) page
2. Save to any location on your computer
3. No installation required - it's a standalone executable

### System Requirements
- **OS**: Windows 10 or Windows 11
- **Privileges**: Administrator rights required
- **Disk Space**: Less than 1 MB
- **.NET**: .NET Framework 4.7.2 or higher (usually pre-installed)

## Usage

### Basic Full Configuration
```powershell
.\Audio_Config.exe
```

### Audio Settings Only
```powershell
.\Audio_Config.exe /audio
```

### Power Settings Only
```powershell
.\Audio_Config.exe /power
```

### Replace Audio Driver
```powershell
.\Audio_Config.exe /driver
```
*This will automatically restart your computer after driver replacement.*

### Disable Notifications
```powershell
.\Audio_Config.exe /notifications
```

### Dry-Run Mode (Test Only)
```powershell
.\Audio_Config.exe /dry
```

### Help & Command Reference
```powershell
.\Audio_Config.exe /?
```

## Running as Administrator

The configurator requires administrator privileges. **Most features will not work without elevation.**

### Method 1: Right-Click
1. Right-click `Audio_Config.exe`
2. Select **"Run as administrator"**
3. Click **Yes** when prompted

### Method 2: PowerShell
```powershell
Start-Process "C:\Path\To\Audio_Config.exe" -Verb RunAs
```

### Method 3: Command Prompt
```cmd
runas /user:Administrator "C:\Path\To\Audio_Config.exe"
```

## Configuration Details

### Audio Jack Volume Fix
The primary audio issue this tool resolves is **automatic volume reduction when headphones are connected**. This is caused by:
1. HP's customized Realtek audio driver
2. Windows' dynamic device detection
3. Jack sensing features

**Solution**: The configurator sets `EnableDynamicDevices = 0` in the audio driver registry, forcing the 3.5mm jack to be treated as a permanent line-out (speaker) port instead of dynamically switching to headphone mode.

### Registry Modifications
All changes are made to Windows registry keys:
- **HKEY_LOCAL_MACHINE** - System-wide settings (driver, power, display)
- **HKEY_CURRENT_USER** - User settings (audio, notifications, explorer)

See **Logging** section below for detailed list of all modifications.

## Logging

All configuration changes are logged to:
```
C:\Users\Public\Maas-Rowe\Logs\Bellwether.log
```

Log entries include:
- Timestamp (ISO 8601 format)
- Information or error level
- Detailed description of each change
- Error messages with stack traces if applicable

## Troubleshooting

### "Access Denied" Errors
- **Cause**: Not running as administrator
- **Solution**: Right-click and select "Run as administrator"

### Audio Jack Still Reducing Volume
- **Cause**: HP audio drivers still installed
- **Solution**: Run `/driver` flag to replace with generic driver (requires restart)

### Changes Not Persisting
- **Cause**: Realtek Audio Service restarting and resetting values
- **Solution**: The tool disables this service. Verify in Services (services.msc)

### Log File Not Created
- **Cause**: Directory doesn't exist
- **Solution**: Run with administrator privileges so the tool can create `C:\Users\Public\Maas-Rowe\Logs\`

## Support This Project

If you find **Audio_Config** valuable for your audio workflow, consider supporting its development:

[![Buy Me A Coffee](https://img.shields.io/badge/☕%20Buy%20Me%20A%20Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/maasrowe)

Your support helps maintain and improve this tool for audio professionals worldwide.

---

## Contact & Issues

For issues, questions, or feature requests:
- **GitHub Issues**: [Report bugs or suggest features](https://github.com/Maas-Rowe/Audio-Configuration-Modification-App/issues)
- **Maas-Rowe Carillons**
- **Email**: [contact@maas-rowe.com]
- **Website**: [www.maas-rowe.com]

## License

All rights reserved by **Maas-Rowe Carillons**. See [LICENSE](LICENSE) file for details.

This software is provided for authorized use with Bellwether performance audio systems only.

## Changelog

### Version 1.0 (Release)
- Initial public release
- Full audio jack detection fixes
- Power management optimization
- Windows notification disabling
- Comprehensive logging system
- Dry-run mode support
- Driver replacement automation

## Contributing

This is a proprietary application maintained by Maas-Rowe Carillons. Third-party contributions are not accepted at this time.

---

**Copyright © 2026 Maas-Rowe Carillons. All rights reserved.**
# Audio-Configuration-Modification-App

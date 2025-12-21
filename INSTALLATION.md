# Installation Guide - WhatsApp Desktop UWP Archive

## Prerequisites Check

Before installing, verify your system meets these requirements:

### 1. Operating System
```powershell
# Check Windows version
winver

# Minimum: Windows 10 build 17763 (version 1809)
# Recommended: Windows 10 21H2 or Windows 11
```

### 2. Architecture
```powershell
# Check system architecture
wmic os get osarchitecture

# Supported: x64, x86, ARM64
```

### 3. Available Space
```powershell
# Check free space on C: drive
wmic logicaldisk get name, freespace
```

## Step-by-Step Installation

### Option 1: Direct Installation (Recommended)

#### Step 1: Enable Sideloading

**Windows 10:**
1. Open **Settings** (Win + I)
2. Navigate to **Update & Security**
3. Click **For developers** in the left sidebar
4. Select **Sideload apps** or **Developer mode**

**Windows 11:**
1. Open **Settings** (Win + I)
2. Navigate to **Privacy & Security**
3. Click **For developers**
4. Toggle **Developer Mode** to **On**
5. Click **Yes** on the confirmation dialog

**Via PowerShell (Admin):**
```powershell
# Enable sideloading
reg add "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock" /t REG_DWORD /f /v "AllowAllTrustedApps" /d "1"
```

#### Step 2: Download the Package

1. Go to the [Releases](../../releases) section
2. Download the latest `.msix` file
3. Verify file integrity (optional but recommended)

**Verify checksum:**
```powershell
# Get SHA256 hash
Get-FileHash .\WhatsApp-Desktop-UWP.msix -Algorithm SHA256
```

#### Step 3: Install the App

**Method A: Double-click**
1. Double-click the `.msix` file
2. Click **Install** in the App Installer window
3. Wait for installation to complete
4. Click **Launch** or find the app in Start menu

**Method B: PowerShell**
```powershell
# Install via PowerShell
Add-AppxPackage -Path ".\WhatsApp-Desktop-UWP.msix"
```

**Method C: App Installer**
```powershell
# Using Windows Package Manager (if available)
winget install --manifest .\WhatsApp-Desktop-UWP.msix
```

### Option 2: Package Installation with Dependencies

If you encounter dependency errors:

#### Step 1: Install Required Frameworks

Download and install these frameworks if not present:

**.NET Native Runtime**
- Download from Microsoft Store or Windows SDK

**Visual C++ Runtime**
```powershell
# Usually included in Windows, but if needed:
# Download from Microsoft's official website
```

#### Step 2: Install with Dependencies
```powershell
# Install with dependency packages
Add-AppxPackage -Path ".\WhatsApp-Desktop-UWP.msix" -DependencyPath ".\Dependencies\"
```

## Post-Installation Setup

### 1. First Launch

1. Find "WhatsApp" in the Start menu
2. Launch the application
3. Scan the QR code with your phone:
   - Open WhatsApp on your phone
   - Tap **Menu** (⋮) or **Settings**
   - Tap **Linked Devices**
   - Tap **Link a Device**
   - Scan the QR code displayed on your PC

### 2. Configure Notifications

**Enable notifications:**
1. Open **Settings** > **System** > **Notifications**
2. Find **WhatsApp** in the app list
3. Toggle notifications **On**
4. Configure notification style as preferred

**Enable Action Center quick replies:**
1. Ensure notifications are enabled (above)
2. In WhatsApp settings, enable "Show notifications in Action Center"
3. Quick reply will work from notification banners

### 3. Set Up Live Tile (Optional)

1. Right-click the WhatsApp tile in Start menu
2. Select **Resize** and choose size (Small, Medium, Wide, or Large)
3. Choose **Pin to Start** if not already pinned
4. Live tile will show recent message previews (if enabled in app settings)

### 4. Configure Startup Behavior

**Launch on Windows startup:**
1. Open **Settings** > **Apps** > **Startup**
2. Find **WhatsApp** in the list
3. Toggle **On**

**Or via app settings:**
1. Open WhatsApp
2. Go to **Settings** > **General**
3. Enable **Launch WhatsApp on Windows startup**

## Verification

### Check Installation Status

```powershell
# Verify app is installed
Get-AppxPackage | Where-Object {$_.Name -like "*WhatsApp*"}

# Expected output shows package details
```

### Verify Update Protection

```powershell
# Check if updates are blocked (should show restricted policy)
Get-AppxPackage -Name "*WhatsApp*" | Select-Object Name, Version, IsBundle
```

### Test Basic Functionality

- [ ] App launches successfully
- [ ] QR code scanning works
- [ ] Notifications appear in Action Center
- [ ] Messages send and receive
- [ ] Media uploads/downloads work
- [ ] Voice notes record and play

## Troubleshooting

### Issue: "App didn't install"

**Solution 1: Check developer mode**
```powershell
# Verify developer mode is enabled
reg query "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock" /v AllowAllTrustedApps
```

**Solution 2: Check package signing**
- Ensure the package is properly signed
- Right-click the `.msix` > Properties > Digital Signatures

**Solution 3: Clear package cache**
```powershell
# Remove any conflicting installations
Get-AppxPackage | Where-Object {$_.Name -like "*WhatsApp*"} | Remove-AppxPackage

# Clear cache
wsreset.exe
```

### Issue: Dependency errors

```powershell
# Install missing frameworks
# Download .NET Native framework from Microsoft Store
# Or use Windows Update to install latest updates
```

### Issue: App won't connect

1. Check internet connection
2. Verify firewall isn't blocking the app
3. Check Windows Defender SmartScreen settings
4. Ensure date/time are correct

```powershell
# Add firewall rule (if needed)
# WARNING: Verify the exact installation path before running this command
# The wildcard path below is approximate and should be replaced with your actual installation path
# Example path: C:\Program Files\WindowsApps\5319275A.WhatsAppDesktop_2.2148.8.0_x64__cv1g1gvanyjgm\WhatsApp.exe
# Use Get-AppxPackage to find exact path:
Get-AppxPackage -Name "*WhatsApp*" | Select-Object InstallLocation

# Then create a specific rule with the full path instead of using wildcards:
# New-NetFirewallRule -DisplayName "WhatsApp UWP" -Direction Outbound -Action Allow -Program "C:\FULL\PATH\TO\WhatsApp.exe"
```

### Issue: No notifications

1. Check notification settings in Windows
2. Verify WhatsApp has notification permissions
3. Check Focus Assist isn't blocking

```powershell
# Check notification settings
Get-AppxPackage -Name "*WhatsApp*" | Get-AppxPackageManifest | Select-Object -ExpandProperty Package | Select-Object -ExpandProperty Capabilities
```

## Uninstallation

### Method 1: Settings App

1. Open **Settings** > **Apps** > **Apps & features**
2. Find **WhatsApp** in the list
3. Click **Uninstall**
4. Confirm the action

### Method 2: Start Menu

1. Find **WhatsApp** in Start menu
2. Right-click the app
3. Select **Uninstall**

### Method 3: PowerShell

```powershell
# Uninstall via PowerShell
Get-AppxPackage | Where-Object {$_.Name -like "*WhatsApp*"} | Remove-AppxPackage

# Remove user data (optional)
Remove-Item "$env:LOCALAPPDATA\Packages\*WhatsApp*" -Recurse -Force
```

## Reinstallation

If you need to reinstall:

1. Completely uninstall the current version (see above)
2. Clear any remaining data
3. Restart your computer
4. Follow installation steps from the beginning

## Data Backup

Before uninstalling, consider backing up:

```powershell
# Backup location (approximate path)
$backupPath = "$env:USERPROFILE\Desktop\WhatsApp-Backup"
$sourcePath = "$env:LOCALAPPDATA\Packages\*WhatsApp*"

# Copy data (adjust package name as needed)
Copy-Item -Path $sourcePath -Destination $backupPath -Recurse
```

**Note:** Messages are end-to-end encrypted and tied to your account, so backups may not be fully restorable.

## Advanced Configuration

### Registry Tweaks (Advanced Users Only)

⚠️ **Warning:** Modifying registry can cause system instability.

```powershell
# Disable update checking (already in patched version)
# For reference only - don't modify
```

### Package Capabilities

To view app capabilities:
```powershell
Get-AppxPackage -Name "*WhatsApp*" | Get-AppxPackageManifest | Select-Object -ExpandProperty Package | Select-Object -ExpandProperty Capabilities
```

## Getting Help

If you encounter issues:

1. Check the [Troubleshooting](#troubleshooting) section above
2. Search existing [Issues](../../issues)
3. Review the [FAQ](README.md#frequently-asked-questions) in the main README
4. Open a new issue with:
   - Windows version (`winver` output)
   - Error messages or screenshots
   - Steps to reproduce

## Security Considerations

⚠️ **Important Security Notes:**

- This is an archived version with no security updates
- Update protection means no patches for vulnerabilities
- Use a firewall and keep Windows Defender updated
- Consider using only on trusted networks
- WhatsApp may restrict accounts using unsupported clients

## Migration to Official Version

To return to the official WebView2 version:

1. Uninstall this archived version
2. Visit the [Microsoft Store](https://www.microsoft.com/store/apps/whatsapp)
3. Download and install the current version
4. Scan QR code to re-authenticate
5. Your messages will sync from the cloud

---

**Need help?** Open an issue in the repository with detailed information about your problem.

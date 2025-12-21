# Frequently Asked Questions (FAQ)

## General Questions

### What is this repository?

This is an **archive and documentation project** for the original WhatsApp Desktop UWP (Universal Windows Platform) application that was available before the transition to the WebView2-based version. It provides information, installation guides, and technical documentation.

### Why does this archive exist?

The original UWP app was significantly faster, more efficient, and better integrated with Windows than the current WebView2 version. Many users with older hardware or resource constraints prefer the native app. This archive preserves that option.

### Is this legal?

This repository contains documentation and educational content, which is legal. The archived application itself is the original from Microsoft Store, unmodified. However, using unofficial or outdated clients may violate WhatsApp's Terms of Service. See [DISCLAIMER.md](DISCLAIMER.md) for full legal information.

### Is this safe to use?

**Proceed with caution**. The archived app receives no security updates, which means:
- Known vulnerabilities won't be patched
- New exploits could emerge
- WhatsApp may ban accounts using unsupported clients

Only use on systems where you accept these risks.

## Installation Questions

### What are the system requirements?

**Minimum:**
- Windows 10 (version 1809 or later) or Windows 11
- 2 GB RAM
- 100 MB free storage
- Internet connection

**Recommended:**
- Windows 10 21H2 or Windows 11 22H2
- 4 GB RAM or more
- 500 MB free storage

See [INSTALLATION.md](INSTALLATION.md) for complete requirements.

### How do I install the archived app?

1. Enable Developer Mode or Sideload Apps in Windows Settings
2. Download the `.msix` package from Releases
3. Double-click to install via App Installer
4. Launch and scan QR code to authenticate

Full instructions: [INSTALLATION.md](INSTALLATION.md)

### Can I install this alongside the official app?

Generally **no**. Both apps use the same package identity, so installing one will replace the other. You must uninstall the official app first.

### Do I need to pay or subscribe?

No. This archive is free. WhatsApp itself is also free (but owned by Meta).

### Why do I need to enable Developer Mode?

Windows requires Developer Mode or Sideload Apps enabled to install applications from outside the Microsoft Store. This is a security measure.

### The installer says "App didn't install" - what do I do?

Common solutions:
1. Ensure Developer Mode is enabled
2. Uninstall any existing WhatsApp installations
3. Clear the Microsoft Store cache: `wsreset.exe`
4. Check if the package is properly signed

See [Troubleshooting](INSTALLATION.md#troubleshooting) for more help.

## Usage Questions

### How do I set up WhatsApp after installation?

1. Open WhatsApp on your PC
2. On your phone, open WhatsApp
3. Go to Settings → Linked Devices → Link a Device
4. Scan the QR code on your PC screen

Your messages will begin syncing.

### Do my messages sync from the cloud?

Limited. The old UWP app has basic message syncing, but not the full cloud backup features of newer versions. Recent messages will appear, but older chat history may not fully sync.

### Can I use this with WhatsApp Web simultaneously?

**No**. The old UWP app doesn't support multi-device mode. Logging in on PC will log you out of WhatsApp Web, and vice versa.

### Do notifications work?

Yes! The UWP app supports native Windows notifications in the Action Center, including:
- Toast notifications
- Quick reply from notifications
- Badge counters
- Live Tile updates (if enabled)

### Do voice and video calls work?

Voice calls typically work. Video call support varies by version - older versions may have limited or no video call support.

### Can I send/receive files, images, and videos?

Yes, all media types supported by WhatsApp should work, including:
- Photos and videos
- Documents (PDF, Office files, etc.)
- Audio messages
- Location sharing
- Contact cards

## Technical Questions

### What makes this different from the current WhatsApp Desktop?

**Old UWP App:**
- Native XAML UI
- C++/C# codebase
- ~50 MB installation size
- ~100-200 MB RAM usage
- Direct WhatsApp server communication

**Current WebView2 App:**
- Web-based UI (HTML/CSS/JavaScript)
- Electron-like architecture
- ~300-500 MB installation size
- ~400-800 MB RAM usage
- Chromium browser engine overhead

See [TECHNICAL.md](TECHNICAL.md) for detailed comparison.

### How does end-to-end encryption work?

The UWP app uses the same Signal Protocol as all WhatsApp clients:
- Curve25519 for key exchange
- AES-256 for encryption
- HMAC-SHA256 for authentication

Messages are encrypted on your device and decrypted only on the recipient's device.

### What Windows features are integrated?

- **Live Tiles**: Message previews on Start menu
- **Action Center**: Native notifications
- **Cortana**: Voice commands (limited)
- **Windows Hello**: Biometric authentication
- **Share Target**: Share to WhatsApp from other apps
- **Background Tasks**: Receive messages when app is closed

### Why is it faster than the WebView2 version?

Native compiled code (C++/C#) runs significantly faster than JavaScript in a browser engine. There's no Chromium overhead, no JavaScript parsing, and direct access to Windows APIs.

### Can I see the source code?

No. WhatsApp's source code is proprietary. This archive contains only the compiled application and documentation.

## Update and Security Questions

### Will I receive updates?

**No**. This is an archived version with update protection. You will not receive:
- Feature updates
- Security patches
- Bug fixes
- Protocol updates

### What are the security risks?

- **Unpatched vulnerabilities**: Security flaws won't be fixed
- **Protocol changes**: WhatsApp may change protocols, breaking functionality
- **Account bans**: Using unsupported clients may violate ToS
- **Compatibility**: Future WhatsApp changes may break the app

### Can I disable update protection and get updates?

The official updates would migrate you to the WebView2 version, defeating the purpose of this archive. We don't recommend it, but uninstalling and downloading from Microsoft Store will give you the current version.

### How do I know if my version is secure?

You can't guarantee security with unpatched software. Best practices:
- Use on isolated systems
- Keep Windows and antivirus updated
- Use strong network security
- Monitor for unusual activity
- Backup data regularly

### Will my WhatsApp account be banned?

Possibly. WhatsApp reserves the right to ban accounts using:
- Unofficial clients
- Modified apps
- Outdated versions
- Automation tools

Use at your own risk. We cannot prevent or reverse bans.

## Compatibility Questions

### Does this work on Windows 11?

Yes! The UWP app runs on both Windows 10 (1809+) and Windows 11.

### Does this work on ARM devices (like Surface Pro X)?

The UWP app was compiled for ARM64, so it should work natively on ARM-based Windows devices.

### What about Windows 10 Mobile or Windows Phone?

This archive focuses on desktop versions. Windows 10 Mobile is discontinued, and support varies.

### Does it work on Windows 10 LTSC/LTSB?

It should work, but may require updating the Windows SDK components or UWP frameworks.

### Can I run this on Linux or macOS?

No. This is a Windows UWP application that requires Windows 10/11. However:
- Linux: Use WhatsApp Web or unofficial clients
- macOS: Use the official macOS app or WhatsApp Web

## Troubleshooting

### The app won't connect to WhatsApp servers

1. Check your internet connection
2. Verify Windows Firewall isn't blocking it
3. Ensure date/time are correct
4. Try restarting the app
5. Check if WhatsApp is down: [downdetector.com](https://downdetector.com/status/whatsapp/)

### Notifications aren't appearing

1. Check Windows Settings → System → Notifications
2. Ensure WhatsApp has notification permissions
3. Verify Focus Assist isn't blocking notifications
4. Check WhatsApp in-app notification settings

### QR code won't scan

1. Ensure your phone has a stable internet connection
2. Make sure your phone's WhatsApp is updated
3. Try restarting both phone and PC
4. Ensure your phone camera works properly
5. Try increasing screen brightness

### The app crashes on startup

1. Restart your PC
2. Check for Windows updates
3. Reinstall the UWP frameworks
4. Clear app data:
   ```powershell
   Get-AppxPackage | Where-Object {$_.Name -like "*WhatsApp*"} | Reset-AppxPackage
   ```

### Messages aren't syncing

1. Check internet connection on both devices
2. Ensure phone isn't in battery saver mode
3. Keep phone's WhatsApp active and connected
4. Try logging out and back in

### Live Tiles aren't updating

1. Ensure Live Tiles are enabled in app settings
2. Check Windows Settings → Personalization → Start
3. Verify background tasks are allowed
4. Pin the app to Start if not already pinned

## Comparison with Alternatives

### Should I use this or WhatsApp Web?

**Use UWP app if:**
- You want native Windows integration
- You have resources to spare
- You prefer offline message access
- You want Live Tiles and better notifications

**Use WhatsApp Web if:**
- You want the latest features
- You don't want installation
- You're okay with browser-based experience
- Security updates are important to you

### Should I use this or the official Microsoft Store version?

**Use archived UWP if:**
- You have limited system resources
- You prefer faster, native apps
- You can accept security risks
- Your hardware struggles with WebView2

**Use official version if:**
- You want ongoing security updates
- You need multi-device support
- You want the latest WhatsApp features
- Account safety is a priority

### What about third-party WhatsApp clients?

Third-party clients come with significant risks:
- Account ban risk is even higher
- Often violate WhatsApp ToS more severely
- May have security vulnerabilities
- Could compromise your privacy

We don't recommend them.

## Data and Privacy

### Where is my data stored?

Locally in:
```
%LocalAppData%\Packages\[WhatsApp-Package-ID]\
```

This includes:
- Messages database (encrypted)
- Media cache
- Settings and preferences

### Can I export my messages?

The UWP app doesn't have a built-in export feature. Your messages remain:
- On your phone (primary device)
- In WhatsApp's cloud (if backup enabled on phone)
- Locally on PC (encrypted)

### How do I backup my data?

Best option: Use phone's WhatsApp backup feature (to Google Drive or iCloud). The PC version doesn't have independent backup.

### What data does this app collect?

The app communicates with WhatsApp servers, which collect:
- Message metadata (timestamps, recipients)
- Usage patterns
- Device information

See [WhatsApp Privacy Policy](https://www.whatsapp.com/legal/privacy-policy) for details.

### Is my data encrypted?

Yes. Messages use end-to-end encryption (Signal Protocol). Local storage is also encrypted. However, archived versions may have older encryption implementations.

## Uninstallation and Alternatives

### How do I uninstall the app?

**Method 1**: Settings → Apps → Apps & features → WhatsApp → Uninstall

**Method 2**: Right-click WhatsApp in Start → Uninstall

**Method 3**: PowerShell:
```powershell
Get-AppxPackage | Where-Object {$_.Name -like "*WhatsApp*"} | Remove-AppxPackage
```

See [INSTALLATION.md](INSTALLATION.md#uninstallation) for details.

### How do I switch back to the official version?

1. Uninstall the archived version
2. Open Microsoft Store
3. Search for "WhatsApp"
4. Install the official version
5. Scan QR code to re-authenticate

### Will I lose my messages?

Messages are stored primarily on your phone and in WhatsApp's cloud (if backup enabled). Switching between PC versions won't affect your messages, but recent chats on the old PC app won't automatically appear on the new one.

## Contributing to This Archive

### Can I contribute?

Yes! We welcome:
- Documentation improvements
- Bug reports and workarounds
- Tips and tricks
- Translations
- Screenshots and guides

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### I found a bug - where do I report it?

Open an issue on GitHub with:
- Windows version
- App version
- Steps to reproduce
- Screenshots if applicable

### Can I request new features?

The app itself is archived and won't receive new features. However, you can request documentation improvements or suggest tips to share with the community.

## Still Have Questions?

- Check existing [Issues](../../issues)
- Review all documentation files in this repository
- Open a new issue with the "question" label
- Search online for community discussions

---

**Disclaimer**: This FAQ is provided for informational purposes. Use archived software at your own risk. We are not responsible for account bans, security issues, or any other problems arising from use of this archive.

# PST Import Tool for Microsoft Purview

**Simplify your PST file imports to Microsoft 365 with this powerful desktop application.**

[![Latest Release](https://img.shields.io/github/v/release/Andorrann/pst-import-releases)](https://github.com/Andorrann/pst-import-releases/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/Andorrann/pst-import-releases/total)](https://github.com/Andorrann/pst-import-releases/releases)

---

## 📥 Download

**[⬇️ Download Latest Version (v1.1.0)](https://github.com/Andorrann/pst-import-releases/releases/latest)**

**System Requirements:**
- Windows 10 or Windows 11
- .NET Framework 4.7.2 or higher (usually pre-installed)
- Internet connection
- Microsoft 365 subscription with Purview

---

## ✨ Key Features

- **🔍 Smart PST Discovery** - Auto-scan common locations or browse manually
- **☁️ Azure Upload** - Fast AzCopy integration with real-time progress
- **🔐 Credential Manager** - Save and reuse SAS URLs securely (encrypted)
- **📊 Microsoft CSV** - Auto-generate Purview-compatible mapping files
- **🎨 Modern Interface** - Splash screen, professional icons, silent background operations
- **⚙️ Easy Mapping** - Visual configuration for mailboxes and archives
- **🔒 Permission Check** - Built-in validator with step-by-step setup guide

---

## 🚀 Quick Start

### 1. Download & Install
Download `PST-Import-Tool-Setup.exe` from the [latest release](https://github.com/Andorrann/pst-import-releases/releases/latest) and run the installer.

### 2. Get Your SAS URL
1. Go to [Microsoft Purview Compliance Portal](https://compliance.microsoft.com)
2. Navigate to **Data lifecycle management** → **Import**
3. Click **New import job** → **Upload your data**
4. Microsoft will provide a **SAS URL** - copy it

### 3. Configure Permissions
You need these roles in Microsoft 365:
- **Purview**: eDiscovery Manager
- **Exchange**: Organization Management or Compliance Management

See the built-in guide for detailed instructions.

### 4. Run the Tool
1. Open PST Import Tool
2. Go to **Setup** tab and paste your SAS URL
3. Go to **Files & Upload** tab to scan for PST files
4. Upload files to Azure
5. Go to **Mapping** tab to configure mailbox mappings
6. Generate CSV file
7. Submit the CSV in Purview to start the import job

---

## 📚 Documentation

### Setup Guide
The application includes a comprehensive setup guide accessible via:
**Setup tab** → **"📖 Open Permissions Setup Guide"**

### Microsoft Documentation
- [Network Upload for PST Files](https://learn.microsoft.com/en-us/purview/use-network-upload-to-import-pst-files)
- [PST Import Overview](https://learn.microsoft.com/en-us/purview/import-pst-files)
- [eDiscovery Permissions](https://learn.microsoft.com/en-us/purview/ediscovery-assign-permissions)

---

## 🔄 What's New in v1.1.0

### ✨ New Features
- **Splash Screen** - Animated loading screen with progress bar
- **Professional Icons** - Visible in app, taskbar, shortcuts, and installer
- **Credential Manager** - Save/reuse SAS URLs with AES-256 encryption
- **Modern Dialogs** - Redesigned upload confirmation and completion
- **Silent Operations** - No CMD windows during uploads or Azure operations

### 🐛 Bug Fixes
- CSV format now matches Microsoft Purview template exactly
- "Use Selected" credential properly loads and validates URL
- Automatic validation after loading saved credentials

[View Complete Changelog](https://github.com/Andorrann/PST-IMPORT-TOOL-O365/blob/main/CHANGELOG.md)

---

## ❓ FAQ

### Do I need an Azure subscription?
**No!** Microsoft provides FREE temporary storage as part of your M365 subscription. You do NOT need a paid Azure account.

### Why is the Delete permission missing?
This is **intentional**. Microsoft's temporary storage excludes delete permission to prevent accidental file deletions. This is normal and expected.

### Can I use this with Exchange on-premises?
No, this tool is designed for **Microsoft 365 cloud mailboxes** only. For on-premises Exchange, use other import methods.

### How long does the SAS URL last?
Typically 30-90 days. The tool will warn you when it's about to expire.

### Where are my logs?
```
C:\Users\<YourUsername>\Documents\PSTImportTool\Logs\
```

### The upload is slow. Is this normal?
Yes, upload speeds depend on:
- Your internet connection
- PST file size
- Azure data center location
- Network congestion

Large PST files (>10 GB) can take several hours.

---

## 🛠️ Troubleshooting

### "SAS URL validation failed"
- Check that you copied the complete URL (it's very long!)
- Ensure the URL hasn't expired
- Verify you generated it from Purview (not Azure Portal)

### "Missing permissions"
- Verify you have eDiscovery Manager role in Purview
- Check Exchange permissions (Organization Management or Compliance Management)
- Wait 15-30 minutes for role propagation
- Sign out and back into Microsoft 365

### Application won't start
- Check Windows Event Viewer for errors
- Ensure .NET Framework 4.7.2+ is installed
- Try running as Administrator
- Reinstall the application

### Upload fails or stalls
- Check your internet connection
- Verify SAS URL hasn't expired
- Check firewall/proxy settings
- Review application logs for detailed errors

---

## 📜 License & Privacy

- This tool is provided **as-is** without warranties
- No data is collected or sent to third parties
- All PST files are uploaded directly to **your** Microsoft-managed Azure storage
- Logs are stored **locally** on your computer only

---

## 🔗 Related Tools

- [Microsoft Network Upload Tool](https://www.microsoft.com/en-us/download/details.aspx?id=54845) (Official Microsoft tool)
- [AzCopy](https://learn.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10) (Command-line utility)
- [PST Capture](https://www.microsoft.com/en-us/download/details.aspx?id=57916) (Microsoft PST export tool)

---

## 📞 Support

For technical support:
1. Check the application logs
2. Review the FAQ above
3. Consult [Microsoft Documentation](https://learn.microsoft.com/en-us/purview/import-pst-files)
4. Contact your IT administrator

---

**⚠️ Important**: This is a community tool and is not officially affiliated with or supported by Microsoft Corporation. Microsoft, Microsoft 365, Purview, and Exchange are trademarks of Microsoft Corporation.

---

**Made with ❤️ for IT administrators managing Microsoft 365 migrations**

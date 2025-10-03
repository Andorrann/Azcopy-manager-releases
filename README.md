# PST Import Tool for Microsoft Purview

**Simplify your PST file imports to Microsoft 365 with this powerful desktop application.**

[![Latest Release](https://img.shields.io/github/v/release/Andorann/PST-IMPORT-RELEASES)](https://github.com/Andorann/PST-IMPORT-RELEASES/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/Andorann/PST-IMPORT-RELEASES/total)](https://github.com/Andorann/PST-IMPORT-RELEASES/releases)

---

## 📥 Download

**[⬇️ Download Latest Version (v1.1.0)](https://github.com/Andorann/PST-IMPORT-RELEASES/releases/latest)**

**System Requirements:**
- Windows 10 or Windows 11
- .NET Framework 4.7.2 or higher (usually pre-installed)
- Internet connection
- Microsoft 365 subscription with Purview

---

## ✨ Features

### 🔍 **Smart PST Discovery**
- Automatically scans common locations for PST files
- Manual folder selection and file browsing
- Displays file sizes and paths

### ☁️ **Azure Upload**
- Integrated AzCopy for fast, reliable uploads
- Real-time progress tracking
- Automatic retry on failure
- Cancel uploads at any time

### ⚙️ **Easy Configuration**
- Visual PST-to-mailbox mapping
- Support for primary mailboxes and archives
- Custom target folder paths
- Bulk configuration options

### 📊 **CSV Generation**
- Automatic creation of Microsoft-compatible CSV mapping files
- Preview before export
- Saves configuration for reuse

### 🔐 **Permission Management**
- Built-in permission checker
- Step-by-step setup guide
- Direct links to Microsoft portals
- SAS URL validation

### 🆕 **Auto-Update (v1.1.0)**
- Checks for updates on startup
- One-click download
- View complete changelog

### 🎨 **Modern Interface**
- Dark theme optimized for productivity
- Intuitive workflow
- Detailed logging and error messages

---

## 🚀 Quick Start

### 1. Download & Install
Download `PST-Import-Tool-Setup.exe` from the [latest release](https://github.com/Andorann/PST-IMPORT-RELEASES/releases/latest) and run the installer.

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

### ✨ Major Updates
- **Automatic update checker** with notifications
- **Help & Updates tab** with version info and changelog
- **Permission dashboard** showing real-time status
- **Modern permissions guide** with direct portal links

### 🐛 Fixes
- Fixed SAS permission detection (now correctly identifies Write/Add/Create/List)
- Removed delete functionality (not available on temp storage)
- Fixed crashes after locking PST selections
- Corrected Azure storage documentation

### 🎨 UI Improvements
- Better color coding (Green/Orange/Red status)
- Explicit permission names instead of abbreviations
- Centered status messages with modern fonts
- Tooltips instead of modal popups

[View Complete Changelog](CHANGELOG.md)

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

---

## 🔗 Related Tools

- [Microsoft Network Upload Tool](https://www.microsoft.com/en-us/download/details.aspx?id=54845) (Official Microsoft tool)
- [AzCopy](https://learn.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10) (Command-line utility)
- [PST Capture](https://www.microsoft.com/en-us/download/details.aspx?id=57916) (Microsoft PST export tool)

---


**⚠️ Important**: This is a community tool and is not officially affiliated with or supported by Microsoft Corporation. Microsoft, Microsoft 365, Purview, and Exchange are trademarks of Microsoft Corporation.

---

**Made with ❤️ for IT administrators managing Microsoft 365 migrations**

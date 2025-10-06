# AzCopy Manager

**A user-friendly desktop application that automates PST file migration to Microsoft 365 Purview using AzCopy technology.**

This tool simplifies the complex process of uploading PST files to Microsoft's cloud storage and generating the required mapping files for Purview import jobs.

[![Latest Release](https://img.shields.io/github/v/release/Andorrann/Azcopy-manager-releases)](https://github.com/Andorrann/Azcopy-manager-releases/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/Andorrann/Azcopy-manager-releases/total)](https://github.com/Andorrann/Azcopy-manager-releases/releases)

---

<p align="center">
  <img src="https://github.com/user-attachments/assets/6a7818bc-fdec-4f99-a026-7804aae55470" alt="Preview 1" width="800">
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/acb85377-3da0-4abe-b865-c13ff0a14ec6" alt="Preview 2" width="800">
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/32ddceed-9e28-42ae-a86b-a154c5980068" alt="Preview 3" width="800">
</p>

## 📥 Download

**[⬇️ Download Latest Version (v1.1.1)](https://github.com/Andorrann/Azcopy-manager-releases/releases/latest)**

**System Requirements:**
- Windows 10 or Windows 11 (64-bit)
- .NET Framework 4.7.2+ (usually pre-installed)
- Internet connection
- Microsoft 365 subscription with Purview

---

## ✅ What This Software DOES

This tool **automates** the technical steps required for PST migration:

- ✅ **Installs AzCopy** - Automatically downloads and configures Microsoft AzCopy
- ✅ **Scans for PST files** - Finds PST files in common locations (Documents, Desktop, Outlook folders)
- ✅ **Validates SAS URL** - Checks your Azure connection and permissions
- ✅ **Uploads PST files** - Uses AzCopy to transfer files to Microsoft's cloud storage
- ✅ **Generates CSV mapping** - Creates Microsoft Purview-compatible mapping files
- ✅ **Manages credentials** - Securely stores SAS URLs with AES-256 encryption (locally)
- ✅ **Tracks progress** - Real-time upload monitoring with detailed logs

---

## ❌ What This Software DOESN'T Do

This tool **does not** handle Microsoft 365 configuration:

- ❌ **Does NOT create Azure storage** - You must generate the SAS URL from Purview
- ❌ **Does NOT configure permissions** - You must assign Purview/Exchange roles yourself
- ❌ **Does NOT submit import jobs** - You must upload the CSV to Purview manually
- ❌ **Does NOT modify mailboxes** - Import happens entirely within Microsoft's systems
- ❌ **Does NOT store data externally** - Everything runs locally on your machine

**You are responsible for:**
- Getting the SAS URL from Microsoft Purview
- Having the correct Microsoft 365 permissions (eDiscovery Manager + Exchange admin)
- Submitting the final CSV file to Purview to start the import

---

## 🔄 What's New in v1.1.1

### 🎨 Rebranding
- **Application renamed** from "PST Import Tool for Purview" to **"AzCopy Manager"**
- More focus on AzCopy technology and clearer naming
- New repository structure (`Azcopy-manager` and `Azcopy-manager-releases`)
- Application data folder renamed to `AzCopyManager`

### 🐛 Bug Fixes
- **Fixed Windows Start Menu Icon** - Icon now displays correctly instead of default disk icon
- **Updated Update System** - All update URLs now point to new repository

### 🎨 UI/UX Improvements
- **Modern "Check for Updates" Dialog** with centered text, Segoe UI font, and larger version display

[View Complete Changelog](https://github.com/Andorrann/Azcopy-manager/blob/main/CHANGELOG.md)

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
C:\Users\<YourUsername>\Documents\AzCopyManager\Logs\
```

---

## 🔒 Privacy & Security - Why This Tool is Safe

### Why I Created This Tool

As an IT administrator, **I was looking for a PST migration tool that I could trust**. When dealing with PST files and SAS URLs (which grant access to company data), **security is critical**.

I couldn't find an open-source tool that met my security requirements, so I built one myself with **privacy and security as the top priority**.

### 🛡️ Zero External Connections

This software **runs entirely on your local machine** with **NO external servers**:

- ❌ **No analytics** - We don't track usage, errors, or any metrics
- ❌ **No telemetry** - Zero data sent to any server (ours or third-party)
- ❌ **No remote logging** - Logs stay on YOUR computer only
- ❌ **No API calls** - Except Microsoft's own APIs (AzCopy, Azure Storage, GitHub for updates)
- ❌ **No cloud storage** - Configuration and credentials are stored locally

**The only external connections are:**
1. **Microsoft AzCopy** (official Microsoft tool for uploads)
2. **Azure Blob Storage** (YOUR Microsoft-managed storage via SAS URL)
3. **GitHub** (for update checks only - optional)

### 🔐 Encrypted Credential Storage

**SAS URLs contain sensitive access credentials.** We take their protection seriously:

- ✅ **AES-256 encryption** - Industry-standard encryption for stored credentials
- ✅ **Local storage only** - Credentials are saved on YOUR computer in `C:\Users\<You>\Documents\AzCopyManager\Config\`
- ✅ **No cloud sync** - Credentials NEVER leave your machine
- ✅ **User-controlled** - You can delete stored credentials anytime via "Manage Keys"

**Even if someone accesses your computer**, the SAS URLs are encrypted and cannot be read without the encryption key (which is also stored locally and tied to your Windows user account).

### 📂 What Data is Stored Locally

The application only stores data **on your computer**:

| Data | Location | Encrypted |
|------|----------|-----------|
| SAS URLs | `Documents\AzCopyManager\Config\` | ✅ Yes (AES-256) |
| Logs | `Documents\AzCopyManager\Logs\` | ❌ No (diagnostic info only) |
| AzCopy | `Documents\AzCopyManager\AzCopy\` | ❌ No (Microsoft binary) |

**No data is ever sent to any server we control.** We don't even have a server.

### 🔍 Open Source Philosophy

The source code is available for review:
- **Main repository**: [github.com/Andorrann/Azcopy-manager](https://github.com/Andorrann/Azcopy-manager)

You can inspect the code yourself to verify:
- No hidden network calls
- No data exfiltration
- No telemetry or tracking
- Proper encryption implementation

### ✅ Trust, But Verify

If you're security-conscious (and you should be!), you can:

1. **Review the source code** on GitHub
2. **Monitor network traffic** during runtime (you'll see only Microsoft connections)
3. **Check stored files** in `Documents\AzCopyManager\` (everything is local)
4. **Build from source** if you prefer to compile it yourself

### 🎯 Our Commitment

**Your data is YOUR data.**

- We **do not** have access to your PST files
- We **do not** have access to your SAS URLs
- We **do not** collect any information about you
- We **cannot** see what you upload

**This tool is a local utility that interfaces with Microsoft's infrastructure only.** All PST uploads go directly from your computer to **Microsoft's Azure storage** using **your SAS URL**.

---

## 📜 License

This tool is provided **as-is** without warranties. It is a community tool and is not officially affiliated with or supported by Microsoft Corporation.

**⚠️ Disclaimer**: Microsoft, Microsoft 365, Purview, and Exchange are trademarks of Microsoft Corporation.

---

**Made with ❤️ by an IT admin who values security and privacy**

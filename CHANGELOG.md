# Changelog - AzCopy Manager

All notable changes to AzCopy Manager will be documented in this file.

---

## Version 1.1.1

**Release Date**: 2025-10-06

### 🎨 Rebranding
- **Application renamed**: "PST Import Tool for Purview" → **"AzCopy Manager"**
- **Updated branding**: More focus on AzCopy technology and clearer naming
- **New repository**: Moved to `Azcopy-manager` (code) and `Azcopy-manager-releases` (releases)
- **Updated paths**: Application data folder renamed from `PSTImportTool` to `AzCopyManager`

### 🐛 Bug Fixes
- **Fixed Windows Start Menu Icon**: Icon now displays correctly in Windows Start Menu instead of default disk icon
- **Updated Update System**: All update URLs now point to new `Azcopy-manager-releases` repository

### 🎨 UI/UX Improvements
- **Modern "Check for Updates" Dialog**: 
  - Centered text layout with modern Segoe UI font
  - Version number displayed larger (24pt) and more prominently
  - "You're Up to Date!" message is bigger and centered (16pt)
  - Cleaner, more professional appearance

---

## Version 1.1.0

**Release Date**: 2025-10-03

### ✨ New Features
- **Automatic Update Checker**: Application now checks for updates on startup and notifies users when a new version is available
- **Help & Updates Tab**: New dedicated tab for version information, update checking, and viewing changelog
- **Permission Status Dashboard**: Real-time display of AzCopy installation, SAS URL validation, permissions, and expiry status
- **Modern Permissions Guide**: Interactive modal dialog with step-by-step setup instructions and direct links to Microsoft portals
- **Unlock PST Selection**: Users can now unlock and change PST selections after locking them for configuration

### 🐛 Bug Fixes
- **Fixed SAS Permission Detection**: Correctly identifies Azure Blob permissions (Write, Add, Create, List) instead of incorrectly checking for Read
- **Removed Delete Functionality**: Removed "Remove" button and delete permission checks (not available on Microsoft's temporary storage)
- **Fixed Application Crash**: Resolved crashes occurring after locking PST files for configuration
- **Corrected Permission Requirements**: Updated guide to reflect that Microsoft provides free temporary storage (no paid Azure subscription needed)

### 🔧 Improvements
- **Simplified Lock Workflow**: Removed confirmation modal when locking PST selections for smoother user experience
- **Better Permission Display**: Explicit permission names (Read, Write, List, Delete) instead of cryptic abbreviations (r, w, l, d)
- **Color-Coded Status**: Green for complete, Orange for warnings (e.g., missing optional Delete permission), Red for critical errors
- **Centered UI Elements**: All permission status labels are now centered with modern Segoe UI font
- **PST Size Display**: Shows PST file sizes in GB for easier understanding
- **Tooltips Instead of Modals**: Replaced aggressive information popups with helpful tooltips on info icons
- **Improved Logging**: Enhanced logging for mapping events and PST locking operations

### 🎨 UI/UX Enhancements
- **Modernized Setup Tab**: Redesigned SAS URL input with better styling and layout
- **"Found X PSTs" Message**: Moved next to "Load PST" button with modern font (green for found, red for none)
- **Centered SAS Status**: "SAS URL is valid" message now centered below input field
- **Reduced Button Heights**: Adjusted "Lock Selection & Configure" and "Remove" button sizes for better visual balance
- **Blue Highlight for Locked PSTs**: Multiple locked PSTs now correctly highlighted in blue
- **Smaller PST Tree**: Adjusted height to prevent overlap with buttons

### 📚 Documentation
- **Complete Permissions Guide**: Comprehensive markdown guide (`PERMISSIONS_GUIDE.md`) with:
  - Azure Blob Storage SAS URL generation instructions
  - Microsoft Purview eDiscovery Manager role assignment
  - Exchange Online permission configuration
  - Troubleshooting common permission issues
  - PowerShell commands for verification
  - Security best practices

### ⚠️ Important Notes
- **SAS URL Permissions**: Microsoft's temporary storage only provides Write/Add/List permissions. Delete permission is intentionally excluded to prevent accidental deletions.
- **No Azure Subscription Needed**: Application works with Microsoft's free temporary storage provided as part of M365 subscription.

---

## Version 1.0.0

**Release Date**: 2025-09-25

### 🎉 Initial Release

- **PST File Discovery**: Automatic scanning of common locations for PST files
- **Azure Upload**: Upload PST files to Microsoft Purview using AzCopy
- **CSV Mapping Generation**: Create import mapping files for Microsoft 365
- **Configuration Management**: Configure target mailboxes, archive settings, and folder paths
- **Progress Tracking**: Real-time upload progress with file-by-file status
- **Modern UI**: Dark-themed interface with PyQt6
- **Comprehensive Logging**: Detailed logs for troubleshooting

---

## Future Roadmap

### Planned for v1.2.0
- Bulk PST upload with parallel processing
- Import job status monitoring from Purview API
- Export/import of configuration presets
- Multi-language support (French, Spanish, German)

### Under Consideration
- Integration with Microsoft Graph API for direct job submission
- Automated mailbox mapping based on PST metadata
- Schedule uploads for off-peak hours
- Email notifications on upload completion

---

## Version Numbering

This project uses [Semantic Versioning](https://semver.org/):
- **MAJOR** version for incompatible API changes
- **MINOR** version for new functionality in a backward-compatible manner
- **PATCH** version for backward-compatible bug fixes

---

## How to Update

1. Download the latest installer from [Releases](https://github.com/Andorrann/Azcopy-manager-releases/releases)
2. Close the current application
3. Run `AzCopy-Manager-Setup-v1.1.1.exe` (or latest version)
4. Follow the installation wizard
5. Launch the updated application

---

**Need Help?** Check the [Main Repository](https://github.com/Andorrann/Azcopy-manager) or visit the [Microsoft Documentation](https://learn.microsoft.com/en-us/purview/use-network-upload-to-import-pst-files).

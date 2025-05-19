# 📦 Repo Gx Manager

![App Screenshot](https://via.placeholder.com/800x400?text=Repo+Gx+Manager+Screenshot)

**The Ultimate GitHub Repository Manager for DEB Packages**  
*A powerful tool to manage your Cydia/APT repositories with ease*

---

## 🌟 Features

```swift
import SwiftUI
import UniformTypeIdentifiers
import Foundation
import CryptoKit
import UIKit

// MARK: - Core Features
enum AppFeatures {
    // Authentication
    static let githubAuth = "Secure GitHub Authentication"
    static let tokenStorage = "Token Storage with Remember Login"
    
    // Repository Management
    static let repoSelection = "Repository Selection"
    static let fileManager = "Advanced File Manager"
    static let createFolders = "Create/Delete/Rename Folders"
    
    // DEB Package Handling
    static let debUpload = "DEB Package Upload"
    static let metadataEditor = "Metadata Editor with Auto-Detection"
    static let checksums = "Automatic Checksum Calculation (MD5, SHA1, SHA256)"
    static let archDetection = "Automatic Architecture Detection"
    
    // Visual Customization
    static let iconUpload = "Icon Upload & Management"
    static let headerUpload = "Header Image Upload"
    static let darkMode = "Dark/Light Mode"
    static let colorThemes = "8 Custom Color Themes"
    
    // Packages File Management
    static let packagesUpdate = "Automatic Packages File Update"
    static let manualUpload = "Manual Packages File Upload"
    static let autoWorkflow = "Automatic Workflow Creation"
    
    // Localization
    static let multilingual = "English/Arabic Support"
    static let rtlSupport = "RTL Layout Support"
    
    // Advanced
    static let progressTracking = "Upload Progress Tracking"
    static let fileEditing = "In-App File Editing"
    static let githubAPI = "Full GitHub API Integration"
}
# For safety reasons please keep a backup before adding it 


# Package Setup Instructions
 
 Follow these steps strictly to ensure the package and Facebook SDK work correctly together.
 
## 1. Import Package
Import this package. It contains the core files needed for the implementation.
 
## 2. Install Facebook SDK
1. Import the Facebook SDK unity package.
2. **CRITICAL STEP:** In the Unity Import window, **UNCHECK** the following folders. Do not import them:
   - `Editor`
   - `StreamingAssets`
   - `Package`
   - `Examples`
3. Click **Import**.
 
## 3. Reinstall External Dependency Manager (EDM) through UPM
The default EDM included with Facebook SDK needs to be replaced with the Package Manager version.
 
1. **Remove Old EDM:**
   - Navigate to your `Assets` folder.
   - Delete the `External Dependency Manager` folder.
 
2. **Add OpenUPM Registry:**
   - Go to `Edit` -> `Project Settings` -> `Package Manager`.
   - Add a new Scoped Registry with these details:
     - **Name:** `OpenUPM`
     - **URL:** `https://package.openupm.com`
     - **Scope(s):** `com.google`
   - Click **Save**.
 
3. **Install EDM via Package Manager:**
   - Open `Window` -> `Package Manager`.
   - Select **Packages: My Registries** (or verify the packages are available).
   - Find and install **External Dependency Manager for Unity**.
 
## 4. Configuration
1. **Facebook Settings:**
   - Open Facebook Settings.
   - Fill in your App details.
2. **Player Settings:**
   - Go to `Player Settings`.
   - Ensure your **Package Name** exactly matches the one in your Meta Developer Portal.
 
## 5. EDM Settings
1. Go to `Assets` -> `External Dependency Manager` -> `Android Resolver` -> `Settings`.
2. **Uncheck/Disable:** `Patch AndroidManifest.xml`.
3. **Check/Enable:** `Verbose Logging`.
4. Click **OK**.
 
## 6. Resolve Dependencies
1. Go to `Assets` -> `External Dependency Manager` -> `Android Resolver` -> `Force Resolve`.
2. Wait for the resolution to succeed.
 
## 7. Pre-Build Clean Up
Before building the APK, verify your plugins folder:
1. Navigate to `Assets/Plugins/Android`.
2. **Check for Manifest:** Look for an `AndroidManifest.xml` file in this specific folder.
   - **If it exists:** DELETE it.
   - **If not:** Proceed.
 
## 8. Build
You are ready to build your Android App (APK/AAB).

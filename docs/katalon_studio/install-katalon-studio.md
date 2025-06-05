Install Katalon Studio
This article shows you how to install Katalon Studio on macOS, Windows, and Linux.

Requirements
A valid email to register your Katalon account.
An active Internet connection to download Katalon Studio.
Do a quick check on system requirements before using Katalon Studio. You can refer to this document here: Supported Environment.
Installation steps
macOS
Windows
Linux
Download the suitable Katalon Studio version and edition for your macOS system on Katalon download page.
Double-click the downloaded .dmg file to proceed with the installation.
Drag Katalon Studio to the Application folder when prompted.
To start Katalon Studio, double-click the Katalon Studio application.
Once started, the application should display the splash screen similar to the following screenshot:

Install Katalon Studio in a restricted environment
note
This workaround applies to Katalon Studio Enterprise (KSE) v10.1.0 and later.

In environments where system directories such as C:\Program Files are write-protected, it's still possible to run applications by redirecting their configuration and workspace data to user-accessible locations. This guide explains how to configure an application to operate normally under such restrictions.

Prerequisites
The application is already extracted or installed in a directory you cannot write to (e.g., C:\Program Files\AppName).
You have read and execute access to the application folder.
The application uses a configuration file (e.g., app.ini or app.cfg) to define runtime data and configuration paths.
Steps
Copy the resources files to a writable directory.
Navigate to the application's configuration\resources directory.
Copy the entire resources folder.
Paste it into a writable path under your user profile, for example:
C:\Users\<your-username>\.yourapp\config\resources

tip
Create the .yourapp\config directory structure manually if it doesn't exist.

Modify the configuration file. Most desktop applications provide an .ini or similar file to define startup parameters. You can override the default configuration and workspace paths here.
Open the application's configuration file (e.g., app.ini) located in the root folder of the application.
Add or update the following lines to redirect configuration and workspace paths to a user-writable location:
-data
@user.home/.yourapp/config
-configuration
@user.home/.yourapp/configuration

Replace .yourapp with a folder name relevant to your application if needed.

The application runs from a restricted directory without needing elevated permissions.

All runtime, workspace, and configuration files are written to your user profile directory.

Application behavior remains unchanged for the end user.

Notes
Ensure the user directory has sufficient space and permissions for storing configuration files and logs.
Back up the user-specific configuration directory if needed for portability or troubleshooting.
This approach is useful in enterprise environments with strict system directory policies.
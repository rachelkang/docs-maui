---
title: "Configure Android development environment in VS Code"
description: "Learn how to configure Android environment for .NET MAUI apps on Android using VS Code."
ms.date: 05/19/2025
no-loc: [ "MY_SPECIFIC_UDID" ]
---

# Configure Android development environment in VS Code

The .NET MAUI extension in VS Code guides you to install the required Android SDK and JDK at default recommended locations. This flow can be accessed through the extension walkthrough or through the command palette. Select **.NET MAUI: Configure Android** followed by **Analyze and Configure Android Environment**.

If you prefer a custom set up, however, the instructions below will guide you through a manual installation process:

## Configure your Java SDK installation

To download and install the Java SDK, and configure Visual Studio Code to use it:

1. Download and install [Microsoft OpenJDK 17](/java/openjdk/download). For information about installing the OpenJDK, see [Install the Microsoft Build of OpenJDK](/java/openjdk/install).

    Alternatively, rather than manually downloading and installing the Java SDK, you can use the `InstallAndroidDependencies` build target to install the Java SDK (and the Android SDK). For more information, see [Using the InstallAndroidDependencies target](#using-the-installandroiddependencies-target).

    > [!IMPORTANT]
    > Ensure that you note the location that the OpenJDK is installed to, as this is required in the next step.

1. Ensure that you've configured the path to OpenJDK via one of the following approaches:
    1. Set the `JAVA_HOME` environment variable to define the Java SDK path for your machine. This is the recommended approach, which defines the Java SDK path at the machine level.

        > [!NOTE]
        > If you install the OpenJDK on Windows via MSI, you can opt into the installer setting the `JAVA_HOME` environmental variable.

    1. In Visual Studio Code, press <kbd>CTRL+SHIFT+P</kbd> on Windows, or <kbd>CMD+SHIFT+P</kbd> on macOS, and then select **.NET MAUI: Configure Android**, followed by **Select Java SDK location** to set the Java SDK path at the user/workspace level.
    1. Configure the Java SDK path in your .csproj file by setting the `$(JavaSdkDirectory)` MSBuild property to the OpenJDK path. This will define the Java SDK path at the project level.

## Configure your Android SDK installation

To download and install the Android SDK, and configure Visual Studio Code to use it:

1. Download and install the Android SDK via one of the following approaches:
    1. Download and install the Android SDK by creating a new .NET MAUI project and then use the `InstallAndroidDependencies` build target, which helps set up your Android environment. This is the recommended approach. For more information, see [Using the InstallAndroidDependencies target](#using-the-installandroiddependencies-target).
    1. Download and install the Android SDK on Windows by [installing the .NET MAUI development workload in Visual Studio](installation.md?tabs=visual-studio), and then [creating and running a .NET MAUI app on Android](first-app.md?pivots=devices-android&tabs=visual-studio). This process will ensure that the Android SDK and an Android emulator are installed.
    1. Download and install the Android SDK through Android Studio. For more information, see [Install Android Studio](https://developer.android.com/studio/install) on developer.android.com.
    1. Download and install the Android SDK through your preferred package manager on Linux.

1. Ensure that you've configured the path to the Android SDK via one of the following approaches:
    1. Set the `ANDROID_HOME` environment variable to define the Android SDK path for your machine. This is the recommended approach, which defines the Android SDK path at the machine level.
    1. In Visual Studio Code, press <kbd>CTRL+SHIFT+P</kbd> on Windows, or <kbd>CMD+SHIFT+P</kbd> on macOS, and then select **.NET MAUI: Configure Android**, followed by **Select Android SDK location** to set the Android SDK path at the user/workspace level.
    1. Configure the Android SDK path in your .csproj file by setting the `$(AndroidSdkDirectory)` MSBuild property to the Android SDK path. This will define the Android SDK path at the project level.

1. In Visual Studio Code, verify that your Android environment is configured correctly by pressing <kbd>CTRL+SHIFT+P</kbd> on Windows, or <kbd>CMD+SHIFT+P</kbd> on macOS, and then selecting **.NET MAUI: Configure Android**, followed by **Analyze and Configure Android Environment**. Any detected errors must be addressed:
    - In the command palette, select **.NET MAUI: Configure Android** followed by both **Select Android SDK location** and **Select Android JDK location** and validate that they correctly point to installations of each. On Windows, if you install the SDKs via Visual Studio, OpenJDK will be located at *C:\Program Files\Microsoft* and the Android SDK will be located at *C:\Program Files (x86)\Android\android-sdk*.
    - Ensure that your Android SDK folder has sub-folders such as *build-tools*, *cmdline-tools*, and *platform-tools*.
    - Ensure that your OpenJDK folder has sub-folders such as *bin*, *lib*, and more.
    - Ensure that the `ANDROID_HOME` environment variable is set to your Android SDK path.
    - Ensure that the `JAVA_HOME` environment variable is set to the your Java SDK path.
    - If Android licenses haven't been accepted, in an elevated terminal navigate to your Android SDK's *cmdline-tools/{version}/bin* folder and run `sdkmanager --licenses` and then follow the CLI prompts.

## Using the InstallAndroidDependencies target

The recommended approach to installing the required dependencies for your .NET MAUI project on Android is to run the [InstallAndroidDependencies](/dotnet/android/building-apps/build-targets#installandroiddependencies) MSBuild target. This target will install the Android SDK for you, if it isn't already installed.

In a terminal, create a new .NET MAUI project:

```dotnetcli
dotnet new maui -n "MyMauiApp"
```

In a terminal, change directory to *MyMauiApp*, and build the app while specifying the `InstallAndroidDependencies` build target:

```dotnetcli
cd MyMauiApp
dotnet build -t:InstallAndroidDependencies -f:net9.0-android -p:AndroidSdkDirectory="/path/to/sdk" -p:AcceptAndroidSDKLicenses=True
```

> [!NOTE]
> The `InstallAndroidDependencies` MSBuild target can also install the Java SDK if the `JavaSdkDirectory` MSBuild property is provided.

In the command above:

- `-p:AndroidSdkDirectory="/path/to/sdk"` installs or updates Android dependencies to the specified absolute path. Suggested paths are *%LOCALAPPDATA%/Android/Sdk* on Windows, and *$HOME/Library/Android/sdk* on macOS.
- `-p:AcceptAndroidSDKLicenses=True` accepts the required Android licenses for development.
- (optional) `-p:JavaSdkDirectory="/path/to/sdk"` installs the Java SDK to the specified absolute path.

Try to avoid using paths that contain spaces or non-ASCII characters.

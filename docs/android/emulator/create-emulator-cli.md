---
title: "Install emulators through Android CLI"
description: "This article explains how to use the Android CLI to create and configure Android Virtual Devices (AVDs) that emulate physical Android devices, for .NET MAUI. You can use these virtual devices to run and test your app without having to rely on a physical device"
ms.date: 05/19/2025
no-loc: ["user.config"]
---

# Install emulators through Android CLI

This article explains how to install Android emulators through various Android CLI commands.

If you're using Visual Studio, follow the instructions to create an Android emulator with [Android Device Manager](device-manager.md).

If you're using VS Code, the .NET MAUI extension in VS Code guides you to install a default recommended emulator. This flow can be accessed through the extension walkthrough or through the command palette. Select **.NET MAUI: Configure Android** followed by **Create an emulator**.

If you prefer to configure additional emulators, however, the instructions below will guide you through a manual installation process:

1. In a terminal, navigate to the *{YOUR_ANDROID_SDK_FOLDER}/cmdline-tools/{version}/bin/*.
1. In a terminal, use the `sdkmanager` command to download and install an Android emulator:

    On Windows, run the following commands:

    ```console
    sdkmanager --install emulator
    sdkmanager --install "system-images;android-35;google_apis;x86_64"
    ```

    On macOS, run the following commands:

    ```console
    ./sdkmanager --install emulator
    ./sdkmanager --install "system-images;android-35;google_apis;arm64-v8a"
    ```

    > [!NOTE]
    > The above command assumes an Apple Silicon Mac. For an Intel Mac, replace `arm64-v8a` with `x86_64`.

    For more information about the `sdkmanager` command, see [sdkmanager](https://developer.android.com/tools/sdkmanager) on developer.android.com.

1. In a terminal, use the `avdmanager` command to create a new Android emulator:

    On Windows, run the following commands:

    ```console
    avdmanager create avd -n MyAndroidVirtualDevice-API35 -k "system-images;android-35;google_apis;x86_64"
    ```

    On macOS, run the following commands:

    ```console
    ./avdmanager create avd -n MyAndroidVirtualDevice-API35 -k "system-images;android-35;google_apis;arm64-v8a"
    ```

    > [!NOTE]
    > The above command assumes an Apple Silicon Mac. For an Intel Mac, replace `arm64-v8a` with `x86_64`.

    For more information about the `avdmanager` command, see [avdmanager](https://developer.android.com/tools/avdmanager) on developer.android.com.
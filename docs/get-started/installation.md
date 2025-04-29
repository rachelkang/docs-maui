---
title: "Install Visual Studio 2022 and Visual Studio Code to develop cross-platform apps using .NET MAUI"
description: "Learn how to install Visual Studio 2022 and Visual Studio Code with the .NET MAUI extension to develop native, cross-platform apps using .NET MAUI."
ms.date: 01/06/2025
monikerRange: ">=net-maui-9.0"
---

# Installation

Developing native, cross-platform .NET Multi-platform App UI (.NET MAUI) apps requires Visual Studio 2022 17.12 or greater, or the latest Visual Studio Code with the .NET MAUI extension.

<!-- markdownlint-disable MD025 -->
# [Visual Studio](#tab/visual-studio)
<!-- markdownlint-enable MD025 -->

To start developing native, cross-platform .NET MAUI apps on Windows, install Visual Studio 2022 17.12 or greater by following the [installation](#installation) steps.

## Prerequisites

- Visual Studio 2022 17.12 or greater. For information about supported operating systems, hardware, supported languages, and additional requirements and guidance, see [Visual Studio 2022 System Requirements](/visualstudio/releases/2022/system-requirements).

To build, sign, and deploy .NET MAUI apps for iOS and Mac Catalyst, you'll also need:

- A Mac that is compatible with Xcode. For more information, see Apple's [minimum requirements documentation](https://developer.apple.com/support/xcode/).
- A specific version of Xcode, which depends on the version of .NET MAUI that you're using. For information, see [Release versions](https://github.com/dotnet/maui/wiki/Release-Versions).
- An [Apple ID](https://appleid.apple.com/account) and paid [Apple Developer Program](https://developer.apple.com/programs) enrollment. An Apple ID is required to deploy apps to devices, and to submit apps to the Apple Store.

Alternatively, to deploy debug builds of your app directly from Windows to your iOS device with [hot restart](~/ios/hot-restart.md), you'll need:

- An [Apple Developer account](https://appleid.apple.com/account) and paid [Apple Developer Program](https://developer.apple.com/programs) enrollment.

## Installation

1. To create .NET MAUI apps, you'll need to download the latest version of Visual Studio 2022:

    - [Download Visual Studio 2022 Community](https://c2rsetup.officeapps.live.com/c2r/downloadVS.aspx?sku=Community&channel=Release&Version=VS2022&source=VSLandingPage&add=Microsoft.VisualStudio.Workload.CoreEditor&add=Microsoft.VisualStudio.Workload.NetCrossPlat;includeRecommended&cid=2305)

    - [Download Visual Studio 2022 Professional](https://c2rsetup.officeapps.live.com/c2r/downloadVS.aspx?sku=Professional&channel=Release&Version=VS2022&source=VSLandingPage&add=Microsoft.VisualStudio.Workload.CoreEditor&add=Microsoft.VisualStudio.Workload.NetCrossPlat;includeRecommended&cid=2305)

    - [Download Visual Studio 2022 Enterprise](https://c2rsetup.officeapps.live.com/c2r/downloadVS.aspx?sku=Enterprise&channel=Release&Version=VS2022&source=VSLandingPage&add=Microsoft.VisualStudio.Workload.CoreEditor&add=Microsoft.VisualStudio.Workload.NetCrossPlat;includeRecommended&cid=2305)

1. Either install Visual Studio, or modify your existing installation through the Visual Studio installer, and install the .NET Multi-platform App UI development workload with its default optional installation options:

    :::image type="content" source="media/installation/vs/vs-workloads.png" alt-text="Visual Studio workloads for .NET MAUI.":::

<!-- markdownlint-disable MD025 -->
# [Visual Studio Code](#tab/visual-studio-code)
<!-- markdownlint-enable MD025 -->

To start developing native, cross-platform .NET MAUI apps on Windows, macOS, or Linux, install the latest Visual Studio Code by following the [installation](#install-visual-studio-code) steps.

## Prerequisites

To build, sign, and deploy .NET MAUI apps for iOS and Mac Catalyst, you'll need:

- A Mac that is compatible with Xcode. For more information, see Apple's [minimum requirements documentation](https://developer.apple.com/support/xcode/).
- A specific version of Xcode, which depends on the version of .NET MAUI that you're using. For information, see [Release versions](https://github.com/dotnet/maui/wiki/Release-Versions).
- An [Apple ID](https://appleid.apple.com/account) and paid [Apple Developer Program](https://developer.apple.com/programs) enrollment. An Apple ID is required to deploy apps to devices, and to submit apps to the Apple Store.

## Install Visual Studio Code

1. To create .NET MAUI apps, you'll need to download the latest version of Visual Studio Code:

    - [Download Visual Studio Code](https://code.visualstudio.com)

1. Install Visual Studio Code. For detailed instructions on how to install Visual Studio Code, see [Visual Studio Code on Windows](https://code.visualstudio.com/docs/setup/windows), [Visual Studio Code on macOS](https://code.visualstudio.com/docs/setup/mac), and [Visual Studio Code on Linux](https://code.visualstudio.com/docs/setup/linux).

## Install the .NET MAUI extension

Before you can create .NET MAUI apps in Visual Studio Code you'll need to install the .NET MAUI extension:

1. Launch Visual Studio Code.
1. In Visual Studio Code, navigate to the **Extensions** tab and search for ".NET MAUI". Then select the [.NET MAUI](https://aka.ms/mauidevkit-marketplace) extension and install it by pressing the **Install** button:

    :::image type="content" source="media/installation/vscode/maui-extension.png" alt-text="Screenshot of the Visual Studio Code extension pane showing the .NET MAUI extension.":::

    The .NET MAUI extension automatically installs the [C# Dev Kit](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit) and [C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) extensions, which are required for the .NET MAUI extension to run. For more information about C# Dev Kit, see [C# Dev Kit for Visual Studio Code](/visualstudio/subscriptions/vs-c-sharp-dev-kit).

## Follow the steps in the walkthrough

Once you install the .NET MAUI extension, you will be welcomed by the .NET MAUI walkthrough, "Get Started with .NET MAUI". Click through and follow the prompts at each step to fully configure your .NET MAUI environment and target platforms.

This walkthrough can also be accessed from the command palette. Select **Welcome: Open Walkthrough...** followed by **Get Started with .NET MAUI**.

### Connect your account to C# Dev Kit

Using C# Dev Kit requires you to sign in with a Microsoft account that has an active Visual Studio subscription:

1. In the **Welcome** tab for getting started with .NET MAUI, press the **Connect** button:

    :::image type="content" source="media/installation/vscode/connect-account.png" alt-text="Screenshot of the Visual Studio Code connect account to c# dev kit button.":::

    Follow the prompts to sign into your Microsoft account. For more information, see [Signing in to C# Dev Kit](https://code.visualstudio.com/docs/csharp/signing-in#_sign-in-with-a-microsoft-or-organizational-account).

For more information about C# Dev Kit licensing, see [C# Dev Kit FAQ](https://code.visualstudio.com/docs/csharp/cs-dev-kit-faq).

### Set up your .NET environment

You'll need the .NET SDK installed on your machine to develop .NET MAUI apps. If you don't have the .NET SDK installed on your machine, the preferred approach to installing it on Windows is through the Visual Studio Installer. For more information, see [Installation](installation.md?tabs=visual-studio).

Alternatively, to manually install the .NET SDK:

1. Download the [.NET installer](https://aka.ms/dotnet-extensionpack-sdk).
1. Install the .NET SDK by running the .NET installer. For more information, see [Install .NET on Windows, Linux, and macOS](/dotnet/core/install/).

    > [!TIP]
    > On Linux, you can install the .NET SDK using the [scripted installation instructions](/dotnet/core/install/linux-scripted-manual#scripted-install).

To verify that the .NET SDK is installed:

1. Open a terminal.
1. In the terminal, run the following command:

    ```dotnetcli
    dotnet --version
    ```

    You should see the version of the .NET SDK that you've installed.

    > [!NOTE]
    > It may be necessary to restart your machine before verifying that the .NET SDK is installed.

### Set up your .NET MAUI environment

You'll need the .NET MAUI SDK installed on your machine to develop .NET MAUI apps. If you don't have the .NET MAUI SDK installed on your machine, the preferred approach to installing it on Windows is through the Visual Studio Installer. For more information, see [Installation](installation.md?tabs=visual-studio).

Alternatively, to manually install the .NET MAUI SDK:

1. Open a terminal.
1. In the terminal on Windows, run the following command:

    ```dotnetcli
    dotnet workload install maui
    ```

    In the terminal on macOS, run the following command:

    ```dotnetcli
    sudo dotnet workload install maui
    ```

    In the terminal on Linux, run the following command:

    ```dotnetcli
    dotnet workload install maui-android
    ```

To verify that the .NET MAUI SDK is installed:

1. Open a terminal.
1. In the terminal, run the following command:

    ```dotnetcli
    dotnet workload list
    ```

    On Windows and macOS, you should see the `maui` workload ID listed alongside the installed version. However, if you've installed it through the Visual Studio Installer on Windows the following workload IDs are listed:

    ```
    android
    maui-windows
    maccatalyst
    ios
    ```

    On Linux, you should see the `maui-android` workload ID listed alongside the installed version.

### Set up target platforms

To build and debug a .NET MAUI app, you'll need to have a valid target platform relative to your development machine's operating system. The following table lists the supported target platforms on each operating system:

| Your Operating System | Supported Target Platforms |
|---|---|
| Windows | Windows, Android |
| macOS | Android, iOS, macOS |
| Linux | Android |

The commands at each walkthrough step will set up everything you need to be successful with each of the target platforms.

<!-- markdownlint-disable MD025 -->
#### [Android](#tab/android)
<!-- markdownlint-enable MD025 -->

To set up your Android development environment, simply click on the **Configure Android Environment** button from the walkthrough to enter the full Android acquisition flow.

The Android acquisition flow will analyze your Android environment and offer to install all missing components:

- **Android SDK and Java SDK** - Android SDK and Java SDK components are required.
    - The Android acquisition flow will prompt you to install these components directly, or to select a preexisting installation you may already have.
    - To configure SDK and JDK further, follow the instructions to [configure your installations](./android/sdk-config.md).
- **Android emulator** - Installing an Android emulator is recommended, and required in the absence of a physical device. 
    - The Android acquisition flow will prompt you to install a default emulator directly.
    - To configure emulators further, follow the instructions to [install an Android emulator through CLI](./android/create-emulator-cli.md).

> [!NOTE]
> Android licenses will need to be manually reviewed and accepted in Terminal. When prompted, review each license. To accept, type 'y', and press 'Enter'.

View the Output pane for more details on your Android environment status. See

<!-- markdownlint-disable MD025 -->
#### [iOS and macOS](#tab/macios)
<!-- markdownlint-enable MD025 -->

To set up your Mac for .NET MAUI development on iOS and Mac Catalyst with Visual Studio Code:

1. Install the version of Xcode that's required by the version of .NET MAUI that you're using. For information, see [Release versions](https://github.com/dotnet/maui/wiki/Release-Versions). The latest stable Xcode release can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/xcode/id497799835?mt=12).
1. In a terminal, run the following command to acquire the Xcode command line tools:

    ```console
    xcode-select --install
    ```

1. Launch Xcode and accept any license agreements. If simulators don't start installing, navigate to **Xcode > Settings > Components** and install your chosen simulator runtimes.
1. In Visual Studio Code, verify that your Apple environment is configured correctly by pressing <kbd>CMD+SHIFT+P</kbd> and then selecting **.NET MAUI: Configure Apple**, followed by **Refresh Apple environment**. Any detected errors must be addressed:
    - Ensure you've ran `xcode-select --install` in a terminal.
    - If you receive an error that Xcode hasn't been found, run `xcode-select -p` in a terminal and check that it returns a path to your Xcode installation.
    - Open Xcode to ensure it loads correctly, and then navigate to **Xcode > Settings > Location** and check that the **Command Line Tools** field is pointing to the correct Xcode installation.

## Troubleshooting

If you encounter issues when installing the .NET MAUI extension in Visual Studio Code, more information about the issues can be found by navigating to the **Output** window (<kbd>CTRL+SHIFT+U</kbd> on Windows or <kbd>CMD+SHIFT+U</kbd> on macOS) and selecting **.NET MAUI** in the drop-down.

## Provide feedback

To provide feedback about the .NET MAUI extension from inside Visual Studio Code, navigate to the **Help > Report Issue** dialog. Then, ensure you select "Bug Report" as the value of the **This is a** drop-down, "A VS Code extension" as the value of the **For** drop-down, and ".NET MAUI" as the value of the **Extension** drop-down:

:::image type="content" source="media/installation/vscode/report-issue.png" alt-text="Picture of the report issue dialog in Visual Studio Code":::

---

## Next steps

To learn how to create and run your first .NET MAUI app in Visual Studio 2022 on Windows, or Visual Studio Code, click the button below.

> [!div class="nextstepaction"]
> [Build your first app](first-app.md)

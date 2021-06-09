# Visual Thinking Toolkit

<p align="center"><img src="http://t-s.net/tmp/visthink/visualthinking.jpg" width="480"></p>

The CITRIS UC Davis Visual Thinking Toolkit facilitates the creation of interactive VR "visual thinking" puzzles.
It is based on the widely used Unity application framework, and currently supports the Oculus Quest VR headset.

The toolkit provides a set of application assets (e.g. 3D models, textures, scenes, source code) and a choice of
puzzle type templates (currently three, but more are planned). It is designed to be extensible so that new puzzle types, assets, and game logic can be easily added.

CITRIS UC Davis has also created a few example Visual Thinking puzzles (one based on each puzzle type template) using the toolkit.
The repositories for these, as well as additional information about them, can be found at the following URLs:

 - Folded Pattern: [https://github.com/citris-ucdavis/foldedpattern](https://github.com/citris-ucdavis/foldedpattern)
 - Rotating Dice: [https://github.com/citris-ucdavis/rotatingdice](https://github.com/citris-ucdavis/rotatingdice)
 - Nine Dots: [https://github.com/citris-ucdavis/ninedots](https://github.com/citris-ucdavis/ninedots)

For more information, see the documentation and guides in the `visthink` repository's `docs` directory here:

 - [https://github.com/citris-ucdavis/visthink/tree/master/docs](https://github.com/citris-ucdavis/visthink/tree/master/docs)

## Puzzle Installation

Binary APK releases of the Visual Thinking puzzles are provided so that they may be installed on an Oculus Quest device without the need to build them from source.
Here we document how these releases may be downloaded and installed to your Oculus Quest using a Windows 10 machine.
Please note that the tools used here, as well as the Oculus Quest firmware, tend to change from time to time, so some aspects of this
process may be slightly different for some users.

### Enable Developer Mode on Your Oculus Quest

To install a Visual Thinking puzzle binary release directly onto an Oculus Quest, the device must be in "developer mode".
Official Oculus instructions for enabling "developer mode" can be found here:

 - [https://developer.oculus.com/documentation/native/android/mobile-device-setup/](https://developer.oculus.com/documentation/native/android/mobile-device-setup/)

### Install Oculus ADB Drivers

In order for your computer to communicate with your Oculus Quest device with ADB over USB, it must have the Oculus ADB drivers installed.
If you haven't already installed these, they can be found here:

 - [https://developer.oculus.com/downloads/package/oculus-adb-drivers/](https://developer.oculus.com/downloads/package/oculus-adb-drivers/)

<p align="center"><img src="http://t-s.net/tmp/visthink/adb_drivers.png" height="300"></p>

Once downloaded, the drivers can be installed as follows:

 1. Unzip the downloaded file.
 1. Navigate to the unzipped file tree and locate the `android_winusb.inf` file in the `usb_driver` directory.
 1. Right-click on the `android_winusb.inf` file and select "Install".
    <p align="center"><img src="http://t-s.net/tmp/visthink/driver_install.png"></p>

### Install the Android SDK Platform Tools

The Android Debug Bridge (adb) tool is needed to install the Visual Thinking puzzle APK files to your Oculus Quest.
The `adb` tool is part of the Android SDK Platform Tools which can be found here:

 - [https://developer.android.com/studio/releases/platform-tools](https://developer.android.com/studio/releases/platform-tools)

Once downloaded, extract the `platform-tools` directory from the `.zip` file to a convenient location (for this example we'll use `C:\platform-tools`).

### Download Visual Thinking Release Builds

Release builds for the Visual Thinking puzzles can be found at the following URLs:

 - [Folded Pattern release builds](https://github.com/citris-ucdavis/foldedpattern/releases)
 - [Rotating Dice release builds](https://github.com/citris-ucdavis/rotatingdice/releases)
 - [Nine Dots release builds](https://github.com/citris-ucdavis/ninedots/releases)

For each of these, click on the `.apk` file for the latest release version to download it.
Once you have downloaded the APKs, open the Windows File Explorer and shift-right-click on your `Downloads` folder.
In the menu that appears, select "Open PowerShell window here".

<p align="center"><img src="http://t-s.net/tmp/visthink/open_powershell_v2.png"></p>

### Install the Release APKs to Your Oculus Quest

 1. Ensure your Oculus Quest is powered on and booted up.
 1. Connect your Oculus Quest to your PC with a USB cable.
    Note that some Oculus Quest devices apparently ship with a power-only USB cable; be sure to use a USB cable that supports data transfer as well.
 1. Test connectivity by typing `C:\platform-tools\adb devices` into the PowerShell.
    You may need to briefly wear the Oculus Quest in order to select "Allow" to any permissions-related prompts you may be given
    via the device, such as the following:
    <p align="center">
      <img src="http://t-s.net/tmp/visthink/allow_usb_debugging.png" height="240">
      <img src="http://t-s.net/tmp/visthink/allow_access_to_data.png" height="240">
    </p>
 1. If you see a device listed under "`List of devices attached`" in the `adb` command output in the PowerShell, then ADB connectivity has been established successfully:
    <p align="center"><img src="http://t-s.net/tmp/visthink/devices_attached.png"></p>

    You should now be able to install the Visual Thinking puzzles to your Oculus Quest by executing the following commands:
    - `C:\platform-tools\adb install -r FoldedPattern.apk`
    - `C:\platform-tools\adb install -r RotatingDice.apk`
    - `C:\platform-tools\adb install -r NineDots.apk`

### Run the Puzzles

Once installed, the Visual Thinking puzzles may be run from the Apps menu in the Oculus Quest UI.
However, since they did not come from the official Oculus application store, the "Unknown Sources" category
must be selected in order to see the apps in the Apps menu list, as illustrated here:

<p align="center"><img src="http://t-s.net/tmp/visthink/unknown_sources.png" height="300"></p>

Once the Visual Thinking apps are visible, simply click on one to run it.

### Questions?

If you have any questions about installation, or about the Visual Thinking software in general, please feel free to contact the current maintainer
of the Visual Thinking software, Travis, at `trav@ucdavis.edu`.


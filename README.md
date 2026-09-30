# Redumper GUI

A cross-platform digital fidget spinner and GUI for [redumper](https://github.com/superg/redumper).

<img width="1506" height="894" alt="tutorial" src="https://github.com/user-attachments/assets/59947cca-3d63-4b79-9282-861a2061d7a4" />

Redumper GUI also supports running [MPF](https://github.com/SabreTools/MPF)'s post-processing immediately after a dump, if you have the [MPF.Check](https://github.com/SabreTools/MPF/releases/latest) executable in the same folder. Alternatively if you're submitting to redump, try out the [MPF GUI](https://github.com/SabreTools/MPF/releases/latest) instead!

## Installation

Download the latest version for your OS from the [Releases](../../releases/latest) page.

The download contains both `redumper-gui` and `redumper` executables. Changing the bundled version of redumper is not recommended as it may not be supported by the GUI.

### Windows

Unzip the download to your location of choice and then double-click `redumper-gui.exe` to run.

If the Windows SmartScreen warning appears, click on **More info**, then **Run anyway**.

### Linux

Extract the `.tar.gz` archive to your location of choice and run the `redumper-gui` executable.

```sh
mkdir -p ~/Redumper-GUI
tar -xzf Redumper-GUI-Linux-x64.tar.gz -C ~/Redumper-GUI
~/Redumper-GUI/redumper-gui
```

#### Flatpak

Build and install from a clone of this repository:

```sh
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak install -y flathub org.freedesktop.Platform//25.08 org.freedesktop.Sdk//25.08 org.freedesktop.Sdk.Extension.rust-stable//25.08 org.freedesktop.Sdk.Extension.llvm22//25.08
flatpak-builder --install --force-clean build packaging/flatpak/com.redumper.gui.yml
```

The sandbox can read and write your home directory. Dumps default to `Downloads/Dumps`. Dumping a disc needs access to `/dev/sg*` and `/dev/sr*`, the same `cdrom` group membership as the tarball. A Flatpak install cannot run a host `MPF.Check` binary.

### macOS

Open the dmg file in Finder, and move `Redumper GUI.app` to the Applications folder. After attempting to open the .app, macOS will warn you it could not verify the app as it is self-signed, go to the bottom of the "Privacy & Security" settings page where it says "Redumper GUI" was blocked to protect your Mac, then click 'Open Anyway' and try again.

Alternatively you can first clear the protection setting in terminal with:

```sh
xattr -cr "Redumper GUI.app"
```

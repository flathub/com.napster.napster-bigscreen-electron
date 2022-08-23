# About

Official client for Napster streaming service, providing a native Linux desktop experince.

## Disclaimer

It is simply an Electron wrapper that loads the official Napster bigscreen application page, just as it would in a regular web browser.

# Steamdeck

Find the assets for your library here:

- [banner](./assets/steamdeck/banner.png)
- [capsule](./assets/steamdeck/capsule.png)
- [icon](./assets/steamdeck/icon.png)

# Manual Installation

- Go to the [latest release](https://github.com/flathub/com.napster.napster-bigscreen-electron/releases/latest).
- Download the specific file that best fits your disto.

# Building from source

## Pre-requisites

- A machine running Arch/Ubuntu on a `x86_64` achitecture (VMs/docker should work)
- `nmp` & `node` for building only the electron app, see `.nvmrc` file
- Flatpak installed on your local machine as well as the `flatpak-builder` package from apt/dnf/pamac
- `org.freedesktop.Platform` flatpak
- `org.freedesktop.Sdk` flatpak
- `org.electronjs.Electron2.BaseApp` flatpak

## Cloning the source code

Once you have npm, clone the wrapper to a convenient location:

```bash
git clone https://github.com/flathub/com.napster.napster-bigscreen-electron.git
```

## Building Electron Only

```bash
npm install
npm run build
```

The package should be inside the `<project-roo>/dist`; If built on mac, generates a `dmg` as well as `.app` file; Linux gets electron binary as well as AppImage

## Building Flatpak Only

```bash
npm run build:flatpak
```

## Building Flatpak with a specific Electron build

You can point to a different electron build (zip) by changing the following lines inside the [yaml](./com.napster.napster-bigscreen-electron.yaml) file:

From:

```
sources:
      - type: file
        url: https://github.com/flathub/com.napster.napster-bigscreen-electron/releases/download/v1.0.0/napster-bigscreen-electron_1.0.0_linux.zip
        sha256: 4c7b6f7cfbb7d07303aa4b7bf1dd93f12382dc3a32333497df90361dad2c46da
```

To:

```
sources:
      - type: file
        path: path/to/my/build/napster-bigscreen-electron_1.0.0_linux.zip
        sha256: (update the sha265 here; mac use `shasum` command; linux use `sha256sum` command)
```

## Testing

Use a gamepad! It's intended to be used with gamepads, however, up/down/left/right/enter/backspace can be used for navigation as well as touch-screen/mouse. Note that you cannot input text with your keyboard on text fields as you'll need to use the virtual on-screen keyboard; This is so we can have a cross-platform app.

Set your window to 1280x800 to simulate Steamdeck's aspect ratio and resolution.

For testing you have two approaches:

- using the electron build, described above, which is multi-platform (mac,linux,windows,x64,arm) thanks to `electron-builder`;
- using the flatpak build, described above, which internally pulls the latest zip release from github

# Publishing

Until we solve the below to-dos:

1. Generate a new electron build on a `linux/x86_64` environment
1. Upload it to the project's [releases here](https://github.com/flathub/com.napster.napster-bigscreen-electron/releases)
1. Update the `url` and `sha` on the [yaml file](./com.napster.napster-bigscreen-electron.yaml) under "sources"
1. Push these changes to the `master` branch

## Pending Tasks

1. Use flatpak's node package to build the app in-place (and support multi-platform builds)
1. Automation to automatically update the version on github's releases

# Links

- [Napster Official website](https://www.napster.com/)

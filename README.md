# About

Official client for Napster streaming service, providing a native Linux desktop experince.

## Disclaimer

It is simply an Electron wrapper that loads the official Napster bigscreen application page, just as it would in a regular web browser.

# Steamdeck

Find the assets for your library here:

- [banner](./assets/banner.png) 
- [capsule](./assets/capsule.png) 
- [icon](./assets/icon.png)

# Manual Installation

- Go to the [latest release](https://github.com/flathub/com.napster.napster-bigscreen-electron/releases/latest).
- Download the specific file that best fits your disto.

# Building from source

## Pre-requisites

- `nmp` & `node` for building only the electron app, see `.nvmrc` file
- Flatpak installed on your local machine to build the flatpak
- `org.freedesktop.Platform` flatpak
- `org.freedesktop.Sdk` flatpak
- `org.electronjs.Electron2.BaseApp` flatpak

## Cloning the source code

Once you have npm, clone the wrapper to a convenient location:

```bash
git clone https://github.com/flathub/com.napster.napster-bigscreen-electron.git
```

## Building Flatpak

```bash
npm run build:flatpak
```

## Building Electron

```bash
npm install
npm run build
```

## TO-DO

1. Use flatpak's node package to build the app in-place (and support multi-platform builds)
1. Automation to automatically update the version on github's releases

# Links

- [Napster Official website](https://www.napster.com/)

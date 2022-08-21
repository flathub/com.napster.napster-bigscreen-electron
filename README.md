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

- `nmp` & `node`, see `.nvmrc` file
- Flatpak installed on your local machine
- `org.freedesktop.Platform` flatpak
- `org.freedesktop.Sdk` flatpak
- `org.electronjs.Electron2.BaseApp` flatpak

## Cloning the source code

Once you have npm, clone the wrapper to a convenient location:

```bash
git clone https://github.com/flathub/com.napster.napster-bigscreen-electron.git
```

## Building

```bash
npm install
npm run build:flatpak
```

# Links

- [Napster Official website](https://www.napster.com/)

# HVAC Desktop Analyzer releases

This repository distributes public Windows and Linux installers and their release metadata; it does not publish the application source. Downloads are public and can be inspected. See [README.md](README.md) for what the application does and how to install it.

## Current release: 0.62.0

- App: HVAC Desktop Analyzer (`com.hvac.analizer`)
- [All releases](https://github.com/JosueJosende/hvac-desktop-analyzer/releases)

| Platform | Asset | Size | SHA-256 |
| --- | --- | --- | --- |
| Windows 10+ (x64) | [HVAC-Desktop-Analyzer-0.62.0-win-x64.exe](https://github.com/JosueJosende/hvac-desktop-analyzer/releases/download/v0.62.0/HVAC-Desktop-Analyzer-0.62.0-win-x64.exe) | 124,816,292 bytes | `444be538d3cbdb4d0ed3d1aab4ae137a447520ec09a9914d5fbc921bd036874f` |
| Linux (x86_64) | [HVAC-Desktop-Analyzer-0.62.0-linux-x86_64.AppImage](https://github.com/JosueJosende/hvac-desktop-analyzer/releases/download/v0.62.0/HVAC-Desktop-Analyzer-0.62.0-linux-x86_64.AppImage) | 160,819,907 bytes | `d45475269f0131ca23a0a8b6ab8e664c9ca17a8e66447f1015c43b28c8caf926` |

Neither installer is code-signed. The Windows binary carries an empty Authenticode security directory, so SmartScreen reports an unknown publisher and the SHA-256 above is the way to check what you downloaded.

## What this version is

The first public release of the desktop application, at the version the private source repository had reached. The application imports a measurement dataset, charts every variable and circuit with the alarms of the analysed range, computes per-variable statistics, correlations and out-of-band values, and exports the result as a standalone HTML file or a PDF report. Saved tests, telemetry and annotations can be kept, shared and moved between equipment; accounts are optional, and the guest mode keeps everything local.

Version 0.62.0 carries the AI report in its field-report form — purpose, technical diagnosis with the reproduction of the fault, alarms of the analysed range, action taken in the field, tests and verification, additional observations, recommended actions, equipment state before and after, and a conclusion — together with optional technician inputs and a differential reasoning that quantifies the change, names the reference band that was crossed and records each ruled-out cause with the data that rules it out. It offers Gemini 3.5 Flash-Lite as a fast, low-cost model, and separates a saturated model, an exhausted quota and a momentary rate limit in the messages it shows. It also fixes the AI model list to offer only what the API currently serves, the report being truncated by the output limit, the provider's raw error reaching the screen, and the alarm totals and diagnostic cache being able to contradict the data they describe.

## Update feed

The packaged application reads `latest.yml` (Windows) and `latest-linux.yml` (Linux) from this repository when it starts, downloads a newer version automatically and verifies the SHA-512 recorded in that metadata before applying it.

## Migration

There is no earlier public desktop release, so this is a first installation. Two notes for anyone who ran a pre-release build:

- The product name changed from "HVAC Analyzer" to "HVAC Desktop Analyzer" for this release. On Windows the installer places the application in `%ProgramFiles%\HVAC Desktop Analyzer` and the Start Menu entry is renamed, so an installation made under the old name is not updated in place; uninstall it after checking where your data lives, or install the new version alongside it.
- The per-user application data directory does not change, because it derives from the application's package name, which was not renamed. The local database, configuration and logs carry over to the new installation.

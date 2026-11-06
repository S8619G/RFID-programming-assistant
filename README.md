# RFID Programming Assistant

RFID Card Identification & AppBlaster Config Assistant is a Windows app for Elatec TWN4 card readers. It interprets reader scans, identifies likely card formats and bit lengths, and generates AppBlaster configuration guidance. It works with official Elatec DevPacks 4.x or higher.

## Download

Get the latest version from [Releases](https://github.com/S8619G/RFID-programming-assistant/releases/latest):

- `RFIDapp-Windows-x64-v0.9.1.zip` for Intel and AMD Windows PCs
- `RFIDapp-Windows-ARM64-v0.9.1.zip` for Windows on ARM PCs
- `SHA256SUMS-v0.9.1.txt` to verify the downloads

## Getting started

1. Close any running copy of the app.
2. Extract the ZIP for your PC into a new folder, keeping any earlier version.
3. Run `RfidApp.Api.exe`.
4. In the browser window that opens, press Ctrl+Shift+R and check that the version in the footer is v0.9.1.

Each package includes `How To Use.txt`, `Change Log.txt`, and the release notes.

## Notes

- The packages are self-contained and do not need a separate .NET install.
- The packages are not code-signed, so Windows SmartScreen may show a warning the first time you run the app.
- Windows ARM64 reader and driver compatibility has not yet been confirmed on physical hardware.
- macOS is not supported yet.

# RFID Assistant v0.9.1

This release adds a native Windows ARM64 package alongside Windows x64. Existing card identification, scanning, calculation, and export workflows are retained.

## Changes

- **Windows ARM64:** Separate hardened, self-contained Windows ARM64 and x64 packages are built from the same source.
- **Visible version:** v0.9.1 appears in the footer and browser tab title. The footer retains the build timestamp, and the running app reports its product version through the build-info endpoint.
- **Safer packaging:** The hardening pipeline accepts `win-x64` or `win-arm64`, stages and checks the result, and refuses to overwrite an existing output path.
- **Release files:** Product version is 0.9.1; assembly and file versions are 0.9.1.0. Each package includes release notes, the cumulative functional change log, and usage instructions.
- **Bundled runtime:** Both self-contained Windows packages include .NET 8.0.31.

## Downloads

- `RFIDapp-Windows-x64-v0.9.1.zip`
- `RFIDapp-Windows-ARM64-v0.9.1.zip`
- `SHA256SUMS-v0.9.1.txt`

## Automated verification

- **Baseline:** The exact v0.9.0 source and binary ZIP hashes were verified. The unchanged source rebuilt successfully, passed 410 backend and 97 frontend checks, and reproduced the hardened x64 publish pipeline.
- **Backend:** v0.9.1 passed 412 tests, a Release build with zero warnings/errors, and formatting verification.
- **Frontend:** 103 source checks passed. Each packaged webroot passed 102 checks plus one source-only declaration assertion checked against editable source.
- **Packaging:** Seven build-safety checks passed. Both Windows executable and support-DLL architectures and executable version resources were verified; outputs contain no PDB files or loose plaintext recipe JSONs.
- **Dependencies:** Current NuGet and npm audits reported no known vulnerabilities in the dependencies checked.
- **Runtime smoke test:** A Linux host using the hardened managed assemblies and packaged ARM64 web assets passed browser checks for version display, Compute, simulated keyboard capture, CSV export, and version fallback. This does not constitute native Windows or physical-reader validation.

## Installation and validation

Close the old app and extract the appropriate ZIP into a new folder, preserving the previous version. Run `RfidApp.Api.exe`, then hard-refresh the browser with Ctrl+Shift+R and confirm v0.9.1 in the footer and browser tab title.

Windows ARM64 is a new target for hardware testing, not a claim of validated reader compatibility. Native Windows execution, ARM64 USB/COM drivers, reader discovery, connection, and physical-card scans require testing on the target computer. No native Windows or physical-reader validation was possible in the Linux build environment, and the packages are not Authenticode-signed.

The app's existing reader-discovery filters and communication behavior are unchanged. If CDC mode needs a separate driver, that driver must support the Windows architecture in use; the app package does not install a driver.

macOS is not included in this release.

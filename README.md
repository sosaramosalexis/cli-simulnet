# cli-simulnet

Fix simultaneous Ethernet + WiFi connections on Windows.

## Usage

```powershell
# Fix (enable both connections simultaneously)
irm https://raw.githubusercontent.com/alsosram/cli-simulnet/master/Fix-SimultaneousConnections.ps1 | iex

# Restore defaults (download first to pass -Restore)
curl.exe -fsSL https://raw.githubusercontent.com/alsosram/cli-simulnet/master/Fix-SimultaneousConnections.ps1 -o fix.ps1
powershell -ExecutionPolicy Bypass -File fix.ps1 -Restore
```

Or download and run:

```powershell
curl.exe -fsSL https://raw.githubusercontent.com/alsosram/cli-simulnet/master/Fix-SimultaneousConnections.ps1 -o fix.ps1
powershell -File fix.ps1
```

## What It Does

- Sets `fBlockNonDomain = 0` in registry to allow simultaneous connections
- Sets WiFi interface metric to 1 (highest priority)
- `-Restore` flag removes the registry key and reverts metric to auto

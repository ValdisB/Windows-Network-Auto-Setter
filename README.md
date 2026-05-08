# Windows Network Auto-Setter (MTU Optimizer)
Version: 1.1.0  
Author: Valdis B.  
License: MIT License

Platform: Windows 10 / Windows 11 (PowerShell 5+ / PowerShell 7+)

## Overview
Windows Network Auto-Setter is a lightweight PowerShell utility that automatically detects your active network type (mobile vs fixed) and applies the optimal MTU value.

Windows does not adjust MTU dynamically, even when switching between mobile networks, CGNAT, PPPoE or fixed broadband. This tool fills that gap by detecting the network type and applying the correct MTU automatically.

## Features
- Fast internet connectivity test (Test-Connection)
- Public IP detection with 3 fallback services:
  - api.ipify.org
  - ifconfig.me
  - checkip.amazonaws.com
- CGNAT detection (RFC 6598 range)
- Determines whether the connection is Mobile or Fixed
- Automatically applies MTU:
  - Mobile (CGNAT): 1460
  - Fixed network: 1500
- Updates MTU for both IPv4 and IPv6
- Detects active IPv4 interface
- Generates MTU.ini with:
  - MTU value
  - Provider type
  - Public IP
  - Timestamp
- Fully portable, no installation required
- Safe: user can inspect the full source code

## Requirements
- Windows 10 or Windows 11  
- PowerShell 5.0 or newer  
- Administrator privileges (auto-elevates)

## How to Use
1. Download the `.ps1` file  
2. Right-click → Run with PowerShell  
3. The tool will:
   - Test internet
   - Detect public IP
   - Detect CGNAT
   - Select MTU
   - Apply MTU
   - Save MTU.ini
4. Press ENTER to exit

## Why MTU Matters
Incorrect MTU can cause:
- Packet fragmentation  
- Slow downloads  
- High latency  
- VPN issues  
- VoIP problems  
- Gaming lag  
- Throughput drops  

Mobile networks and CGNAT almost always require MTU < 1500.

## Notes
- The script is transparent and editable  
- No external dependencies  
- No telemetry  
- No installation  
- No registry modifications  

## Changelog
### 1.1.0
- Added fallback public IP sources  
- Cleaned code and comments  
- Updated version header  
- Improved error handling  

### 1.0.0
- Initial release

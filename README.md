# luci-proto-amneziawg

LuCI Web UI support for AmneziaWG VPN on OpenWrt.

## Features

- Full AmneziaWG v2.0 parameter support in Web UI
- Visual connection status indicators
- QR code generation for mobile clients
- Drag-and-drop configuration file import
- Ranged value validation (e.g., `123456-123500` for H parameters)
- Real-time peer status monitoring

## Screenshots

### Connection Status
- Color-coded badges: Connected (green), Idle (yellow), Disconnected (red)
- Handshake time with relative and absolute display
- Data transfer statistics

### Configuration
- Tabbed interface for General, Advanced, AmneziaWG Settings, and Peers
- Inline validation for all parameters
- Tooltips explaining each parameter

## AmneziaWG Parameters

### Junk Packet Parameters (Jc, Jmin, Jmax)
Control the number and size of junk packets sent to obfuscate traffic.

### Session Header Parameters (S1-S4)
Control the size of junk headers for different packet types.

### Packet Type Header Parameters (H1-H4)
Define packet type headers. Support ranged values for randomization.

### Signature Parameters (I1-I5)
Custom payload signatures for packet obfuscation.

## Installation

```bash
opkg update
opkg install luci-proto-amneziawg
```

## Usage

1. Navigate to Network > Interfaces in LuCI
2. Create new interface with protocol "AmneziaWG VPN"
3. Configure your parameters:
   - General: private key, listen port, IP addresses
   - AmneziaWG Settings: J, S, H, I parameters
   - Peers: add peer configurations
4. Save & Apply

## QR Code Export

For each peer, you can generate a QR code containing the full configuration. This can be scanned by the AmneziaVPN mobile app.

## Dependencies

- `amneziawg-tools`
- `ucode`
- `luci-lib-uqr`
- `resolveip`

## License

Apache-2.0

## Links

- [amneziawg-tools-openwrt](https://github.com/xyzmean/amneziawg-tools-openwrt) - CLI tools
- [kmod-amneziawg-openwrt](https://github.com/xyzmean/kmod-amneziawg-openwrt) - Kernel module
- [amneziawg-go-openwrt](https://github.com/xyzmean/amneziawg-go-openwrt) - Go implementation

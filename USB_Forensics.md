# USB Device Forensics: Key Information

## Registry Path/Location
- USB device metadata is stored in the Windows Registry under a specific path.

## Fields Explained
- **Address**: `0x00000004` (hexadecimal) – Address/port of the connected USB device.
- **Capabilities**: `0x00000010` – Indicates features, such as being removable.
- **ClassGUID**: `{4d36e967-e325-11ce-bfc1-08002be10318}` – Identifies the device class (e.g., disk drive).
- **CompatibleIDs**: Lists device identifiers for driver matching.
- **ContainerID**: `{9b8ec98a-d2c1-5306-89d5-4e342db986a9}` – Unique identifier for the device.
- **DeviceDesc**: Human-readable device description (e.g., "Disk drive").
- **FriendlyName**: Example: "Verbatim STORE N GO USB Device."
- **HardwareID**: Detailed identifiers for driver selection.
- **Mfg (Manufacturer)**: Typically generalized (e.g., "Standard disk drives").
- **Service**: Specifies driver service (e.g., `disk`).

---

## ClassGUID in Windows
1. **Driver Matching**: Helps locate the appropriate driver for a device.
2. **Registry Organization**: Devices are grouped under ClassGUID.
3. **Device Manager Grouping**: Groups devices into classes:
   - Disk Drives: `{4d36e967-e325-11ce-bfc1-08002be10318}`
   - USB Devices: `{36fc9e60-c465-11cf-8056-444553540000}`
4. **Policy Application**: Settings applied to a class affect all devices with the same ClassGUID.

### Common ClassGUIDs
| Device Class       | ClassGUID                                |
|--------------------|------------------------------------------|
| Disk Drives        | `{4d36e967-e325-11ce-bfc1-08002be10318}`|
| USB Devices        | `{36fc9e60-c465-11cf-8056-444553540000}`|
| Network Adapters   | `{4d36e972-e325-11ce-bfc1-08002be10318}`|
| Audio Devices      | `{4d36e96c-e325-11ce-bfc1-08002be10318}`|
| Keyboards          | `{4d36e96b-e325-11ce-bfc1-08002be10318}`|

---

## What is the ContainerID?
- A unique identifier for a physical device, stored in the Windows Registry.
- Generated based on:
  - Serial number (if available and unique).
  - Device descriptors (e.g., manufacturer, model).
  - Connection details (e.g., USB port).

### Scenarios Affecting ContainerID:
1. **Unique Serial Number**: Stays consistent across PCs.
2. **No/Fake Serial Number**: Generated dynamically; may vary across ports/PCs.
3. **Virtualization/Drivers**: May cause ContainerID changes.
4. **Same PC, Same Port**: Typically remains consistent unless the device is reformatted.

### Testing ContainerID Consistency:
1. Plug the pen drive into different PCs/ports.
2. Retrieve ContainerID from the Windows Registry:
   - Path: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR`.
   - Check the `ContainerID` under the device entry.
3. A consistent ContainerID indicates a unique serial number.

---

## Getting USB Device Serial Number
1. Right-click on the USB device → **Properties**.
2. Go to the **Details** tab.
3. From the **Property** dropdown, select:
   - **Device Instance Path** or **Hardware IDs**.
   - The last part of the string (after `\`) is the serial number.

Example: `USB\VID_XXXX&PID_XXXX\SerialNumber`.


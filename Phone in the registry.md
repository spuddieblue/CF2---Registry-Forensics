# Lab: Investigating USB Devices in the Windows Registry

## Objective
Learn how to investigate USB device details using the Windows Registry and analyze information such as Vendor ID (VID), Product ID (PID), and other metadata.

---

## Steps

### Step 1: Locate the USB Device in the Registry
1. **Open the Registry Editor**:
   - Press `Win + R`, type `regedit`, and press **Enter**.
2. **Navigate to the USB Device Key**:
   - Go to: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USB`.
   - Expand this key to view subkeys for connected or previously connected USB devices.

---

### Step 2: Identify the Device
1. **Find the Relevant VID and PID**:
   - Each subkey is named in the format `VID_XXXX&PID_XXXX`. These represent:
     - **VID (Vendor ID)**: Identifies the manufacturer.
     - **PID (Product ID)**: Identifies the specific product model.
   - Locate the folder corresponding to your device (e.g., `VID_28E8&PID_2646`).
2. **Verify the Device Name**:
   - Select the subkey and check the `DeviceDesc` value (e.g., "USB composite device") in the right-hand pane to confirm the device.

---

### Step 3: Analyze Device Metadata
1. Select the identified device key.
2. Review the following fields in the right-hand pane:
   - **Address**: The USB port number (e.g., `0x00000001`).
   - **ClassGUID**: The GUID identifying the device type (e.g., `{36fc9e60-c465-11cf-8056-444553540000}` for USB devices).
   - **HardwareID**: Lists specific identifiers (e.g., `USB\VID_28E8&PID_2646`).
   - **ContainerID**: A unique identifier for the physical device.
   - **Mfg (Manufacturer)**: Indicates the manufacturer (e.g., a generic driver string or specific name).

---

### Step 4: Verify the Manufacturer Using VID
1. Note the **VID** (e.g., `28E8`) and **PID** (e.g., `2646`) values.
2. Use an online USB database (e.g., [USB ID Database](https://usb-ids.gowdy.us/)) to verify the manufacturer and product details.

---

### Step 5: Check Device Consistency
1. **Inspect the ContainerID**:
   - The `ContainerID` field helps identify if the device has a unique serial number.
   - If the `ContainerID` changes across ports or systems, the device likely lacks a unique serial number.
2. **Test Consistency**:
   - Reconnect the device to different USB ports or systems.
   - Check if the `ContainerID` remains the same.

---

### Step 6: Investigate Advanced Parameters
1. Expand the **Device Parameters** subkey under the selected device key.
2. Analyze settings related to the USB device’s behavior (e.g., power management, connection type).

---

## Summary
By completing this lab, you should be able to:
- Locate USB devices in the Windows Registry.
- Identify key metadata such as VID, PID, and ContainerID.
- Analyze the device’s manufacturer and properties.
- Determine if a USB device has a consistent identifier across systems.

---

## Additional Resources
- [USB ID Repository](https://usb-ids.gowdy.us/)
- Windows Documentation: [Registry Editor](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/regedit)

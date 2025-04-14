# RPI-PICO-esp8285-wifi-chip
This is an instruction / code manual for working with non-compliant esp8285 wifi chip based RPi Pico devices (mostly found as chinese clones for the pico on sites like AliExpress)

# ESP8285 + Raspberry Pi Pico W Serial Firmware Setup

This guide walks you through the steps to flash your Raspberry Pi Pico W and ESP8285 module for serial communication and firmware updates.

## Requirements

- Raspberry Pi Pico W
- ESP8285 USB module
- `Serial_port_transmission.uf2` firmware file
- `WIFI-ESP8285_upgrade.bin` firmware file (or equivalent)
- MicroPython firmware (e.g., `RPI_PICO_W-20240105-v1.23.uf2`)
- [ESP Web Tool](https://esp.huhn.me/) (in-browser ESP flasher)

---

## Flashing Instructions

### Step 1: Flash the Pico W with Serial Transmission Firmware

1. Hold down the **BOOTSEL** button on the Raspberry Pi Pico W.
2. While holding it, plug the Pico into your USB port.
3. Release the button once the board appears as a USB drive.
4. Drag and drop the `Serial_port_transmission.uf2` file onto the Pico.
5. The Pico will reboot and begin serial communication.

---

### Step 2: Flash Firmware to ESP8285 Using ESP Web Tool

1. Go to [ESP Web Tool](https://esp.huhn.me/).
2. Plug in the ESP8285 USB module **while holding down its BOOT switch**.
3. Click **Connect** and choose the serial port:
   - It should appear as `Tiny USB device (ttyACMx)` (or similar).
4. You can now either:
   - **Erase** existing firmware, or
   - **Program** new firmware:
     1. Click **Browse** and select your firmware (e.g., `WIFI-ESP8285_upgrade.bin`).
     2. Click **Program** to upload the firmware.
5. Wait for the confirmation that programming is complete.

---

### Step 3: Re-flash the Pico W with MicroPython

1. Disconnect the USB cable from the Pico.
2. Hold the **BOOTSEL** button again and reconnect the USB.
3. Flash the latest MicroPython UF2 (e.g., from [micropython.org](https://micropython.org/download/RPI_PICO_W/)) by dragging it to the Pico’s USB drive.
4. The Pico will now boot into MicroPython.

---

## Notes

- Make sure all connections are secure during flashing.
- Serial communication between the Pico W and ESP8285 should now be active.
- For UART communication, ensure TX/RX lines are properly connected.

---

## License

MIT License

---

## Credits

Thanks to [ESP Web Tool](https://esp.huhn.me/) for an easy and reliable way to flash ESP devices.

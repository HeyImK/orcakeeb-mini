# orcakeeb-mini

A 16-key mechanical macropad featuring a rotary encoder, per-key RGB, and a 0.91-inch OLED screen. The board is built around the Waveshare RP2040-Zero module, which handles the USB-C connection and logic, allowing for a highly compact PCB design. Fully compatible with QMK and KMK (CircuitPython) firmware.

## Pictures

| Top View | Bottom View |
| :---: | :---: |
| ![Board Front](Images (R) /topbrd.png) | ![Board Back](Images (R)/btmbrd.png) |

## Features

* **Main Controller:** Waveshare RP2040-Zero, providing a dual-core ARM Cortex-M0+ and natively handling USB-C and 3.3V regulation.
* **Switch Matrix:** 4x4 grid supporting 16 TTC low-profile mechanical switches, fully diode-isolated to prevent ghosting.
* **RGB Leds:** 16 reverse-mounted SK6812MINI-E LEDs sitting flush inside the switch cutouts. Powered directly via the 5V VBUS line.
* **Rotary Encoder:** Standard rotary encoder with push-button functionality. Relies on internal RP2040 pull-up resistors and software debouncing.
* **OLED Display:** I2C header for a standard 0.91" SSD1306 OLED module to display active layers, WPM, or custom graphics.

## Components Used

* **Microcontroller:** Waveshare RP2040-Zero Dev-Board
* **Switches:** 16x Cherry MX Switches or similar knock-offs
* **Diodes:** 16x 1N4148 
* **LEDs:** 16x SK6812MINI-E
* **Screen:** 0.91" SSD1306 I2C OLED Module
* **Miscellaneous:** 1x 10µF Ceramic Cap (for main 5V), 16x 0.1µF Caps (LED decoupling), EC11 (or similar knockoffs) Rotary Encoder

| Schematic Design |
| :---: |
| ![Schematic Diagram](Images (R)/schematics_orcakeeb.png) |

| PCB Top Layer Routing | PCB Bottom Layer Routing |
| :---: | :---: |
| ![Top Routing](Images (R)/routing_topbrd.png) | ![Bottom Routing](Images (R)/routing_btmbrd.png) |

### Connections
* **VBUS (5V):** Routes power straight from the USB-C port to the main 10µF bulk capacitor, then daisy-chains to the VDD pins of all 16 LEDs. 
* **OLED Header:** Connecetd to pins (SDA) G10 (SCK) G9
* **Encoder:** Connected to Pin G4, and A And B pins to G3 and G2
* **RGB Led Data:** Data IN pins connected to G14
  
## License

This hardware project is open-source and licensed under the CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN-OHL-S-2.0). 

You are free to copy, modify, distribute, and manufacture this board for personal or commercial use. However, if you modify these schematic or layout files and distribute your new design, you must release those modifications under this exact same CERN-OHL-S-2.0 license.

This design is shared without any warranty or implied guarantee. Check the LICENSE file for the full legal text.

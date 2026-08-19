# ProtoCentral Pulse Express — Hardware

![ProtoCentral Pulse Express Pulse-Ox & Heart Rate Sensor](assets/protocentral-pulse-express.jpg)

Open-source hardware design files for the **ProtoCentral Pulse Express** pulse-oximetry / heart-rate breakout — pairing the [Maxim MAX30102](https://www.analog.com/en/products/max30102.html) optical sensor with the [Maxim MAX32664D](https://www.analog.com/en/products/max32664.html) biometric sensor hub.

Unlike our [Pulse](https://github.com/Protocentral/protocentral_pulse_hardware) board, which streams raw PPG for the host to process, Pulse Express runs Maxim's algorithms on the MAX32664D hub itself and returns computed heart rate, SpO₂, and blood-pressure-trend estimates over I²C. That offloads the signal processing from your MCU at the cost of visibility into the raw signal.

## Links

| | |
|---|---|
| 🛒 Product page | https://protocentral.com/product/pulse-express-pulse-ox-heart-rate-sensor-with-max32664/ |
| 💻 Arduino library | https://github.com/Protocentral/protocentral-pulse-express |
| 📄 Sensor hub datasheet (Analog Devices / Maxim) | https://www.analog.com/media/en/technical-documentation/data-sheets/MAX32664.pdf |
| 📄 Optical sensor datasheet | https://www.analog.com/media/en/technical-documentation/data-sheets/MAX30102.pdf |

## Specifications

- **Sensor hub:** Maxim MAX32664GTGD+ (MAX32664D variant) with 32.768 kHz crystal
- **Optical sensor:** Maxim MAX30102 — red (660 nm) + IR (880 nm) LEDs, photodiode, and AFE
- **Output:** computed heart rate, SpO₂, and blood-pressure trend from the on-hub algorithms
- **Interface:** I²C, via 2× TXS0102 bidirectional level translators
- **Connector:** 6-pin 0.1″ header
- **Supply:** onboard AP2112K-3.3 V and AP2112K-1.8 V LDOs
- **Board:** 36.0 × 17.5 mm, 2-layer

## Revisions

| Revision | Design files | Notes |
|---|---|---|
| **v3** (current) | [`hardware/`](hardware/) | KiCad 10 |
| earlier | [`protocentral-pulse-express/hardware/`](https://github.com/Protocentral/protocentral-pulse-express/tree/master/hardware) | Eagle; retained in the Arduino library repository so existing links keep working |

## Repository layout

| Folder | Contents |
|---|---|
| [`hardware/`](hardware/) | KiCad project (schematic + PCB layout) and the exported [schematic PDF](hardware/protocentral-pulse-express-v3-schematic.pdf) |

## Important notice

This device is intended for research, education, and evaluation use only. It is **not** a medical diagnostic instrument and is not FDA, CE, or FCC approved for consumer use. The blood-pressure-trend output of the MAX32664D requires per-user calibration and is not a substitute for a validated blood-pressure monitor.

## License

The hardware design files in this repository are licensed under the **CERN Open Hardware Licence Version 2 – Permissive (CERN-OHL-P v2)**. See [LICENSE](LICENSE).

The accompanying firmware/library (in the separate [protocentral-pulse-express](https://github.com/Protocentral/protocentral-pulse-express) repository) is licensed under the MIT License.

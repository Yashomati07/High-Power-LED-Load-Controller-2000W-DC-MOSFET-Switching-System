#  High-Power DC Load Controller

This project is a robust, high-power DC load controller utilizing an STM32 microcontroller. It's capable of managing and monitoring a **2000W DC load** (such as LEDs or resistive elements) powered by a **40V DC input supply**. The system integrates key features including **thermal monitoring**, a **buck converter for voltage regulation**, **logic-level MOSFET switching**, and multiple **protection mechanisms** to ensure reliable operation.

---

##  Key Features

- Supports input voltage up to 40V DC  
- Buck converter (XL4016) steps voltage down to 36V DC  
- Delivers up to 56A continuous, with 100A peak current handling  
- Managed by an STM32F103C8T6 MCU ("Blue Pill" board)  
- Supports 4–6 NTC thermistors for temperature sensing  
- Logic-level N-channel MOSFET (IRLZ44NPBF) for load control  
- Integrated protection using TVS diode, PTC resettable fuse, and flyback diode  
- PCB designed and documented using **EasyEDA**

---

##  System Modules

1. **Input Stage & Protection**  
   - Power entry through **XT60 connector**  
   - **TVS diode (P6KE43A)** for overvoltage protection  
   - **PTC fuse (MF-RX050)** to guard against overcurrent events  

2. **Voltage Regulation**  
   - **XL4016E1 Buck Converter** for stepping down input from 40V to 36V  
   - Handles high current loads with built-in heat dissipation features  

3. **Load Switching**  
   - **IRLZ44NPBF** logic-level MOSFET driven by MCU GPIO  
   - **Schottky diode (1N5822)** for reverse current protection  

4. **Temperature Sensing**  
   - Up to 6 × **10kΩ NTC thermistors** connected to ADC pins  
   - Monitors system temperature for thermal protection and diagnostics  

---

## 🛠️ Tools & Technologies

- **EasyEDA** – Used for schematic capture and PCB layout  
- **STM32F103C8T6 (Blue Pill)** – ARM Cortex-M3 microcontroller  
- **STM32CubeIDE / PlatformIO** – For firmware development

---

##  Project Structure

| Folder/File         | Contents                                  |
|---------------------|--------------------------------------------|
| `/hardware/`        | Schematic and PCB layout files (EasyEDA)   |
| `/firmware/`        | STM32 source code for control and sensing  |
| `README.md`         | Project overview and documentation         |
| `BoM.csv`           | Complete Bill of Materials                 |
| `/images/`          | System block diagram and PCB renders       |

---

##  Roadmap / To-Do

- [ ] Add and upload STM32 firmware code  
- [ ] Implement automatic load cutoff based on temperature readings  
- [ ] Optional: Design and test enclosure for physical safety  
- [ ] Conduct real-world tests with different 36V DC loads  

---

##  License

This is an open-source project available under the terms of the [MIT License](LICENSE). Contributions and forks are welcome.

---

##  Credits & Thanks

- Community support from **STM32CubeIDE** and **PlatformIO**  
- Hardware design tools by **EasyEDA**  
- Inspired by the open hardware and maker communities

---

### Valden: Remote Display v1.x
<b>  This device allows you to control the [Valden Heat Pump](https://github.com/openhp/HeatPumpController/) via remote display. Display can be used with a signal cable up to a few hundred meters long.</b> As well as the controller this display is an also open product with available gerber and source code.<br><br>
## Specs
- 12V 0.5A DC power supply,
- build-in RTC,
- Day/Night temperature set,
- LCD 16x02,
- RS485 connection to the Heat Pump,
- secondary RS485 connection to integrate with external systems ( [example here](https://github.com/openhp/HP-integration-example/) ),
- JSON,
- MODBUS.

## Changelog and history
- 2019-2020: prototyping, installations, development, tests, revisions, redesigns,
- Dec 2020: [Service display](https://github.com/openhp/ServiceDisplay/) software fork created,
- Mar 2021: Documentation and release stage.

## Get your own copy of PCB and board assembly
- download PCB Gerber file or get your own copy {-link here-}
- order electronic components, see BOM (Bill Of Materials) appendix below,
- solder electronic components. {- assembly instructions here-}

## Firmware upload
This process is same as for other Arduinos:
- connect USB-> UART converter,
- start Arduino IDE,
- open the firmware {-link here-} file,
- select board and MCU in the Tools menu (hint: we are using "mini" board with 328p MCU),
- press the "Upload" button in the interface and "Reset" on the Arduino.

For arduinos with an old bootloader you need to update it. (Tools-> Burn Bootloader).<br>
For successful compilation, you must have "DS3231", "LiquidCrystal" and "SoftwareSerial" libraries installed (see Tools -> Manage Libraries).<br>
Note that SoftwareSerial library must be downloaded from the "Valden Remote Display" GitHub repository and located at the same directory as "Remote Display" source. This library is slightly modified.<br>
A manual configuration is not required, your display will work as in the pictures below after connecting to the heat pump.<br><br>


## Wiring and installation
Wiring is very simple:<br>
- connect "internal" RS485 terminal through a wire of the desired length to the [Heat Pump Controller](https://github.com/openhp/HeatPumpController/). Note that A is connected to A, B to B and GND to GND,
- if used, connect "external" RS485 terminal to your computer, Raspberry, or server ([communication example here](https://github.com/openhp/HP-integration-example)).
- connect 12V, you can get it from your [Heat Pump Controller](https://github.com/openhp/HeatPumpController/), or from another 12V power supply unit.

{- wiring photo here-}<br>

## Usage
An end user does not want to know much about refrigerants, evaporation, cycles and so on, so this display designed as simple as possible.<br><br>

After powering on, you will see the following main screen:<br>
![main view](./m_display_main.jpg)<br>

Here you'll see current time, "d:" Day setpoint temperature,"n:" Night setpoint temperature.<br>

Second string, "Ts1": water tank temperature (or "Thi": hot in, if a "warm floor" scheme used). And the last value is a current state, one of the followings
- **Run**: the heat pump is powered on,
- **Stop**: heat pump is in power-saving mode,
- **Chkg**: the heat pump is checking target temperature (then it will go into power save mode or switched on, if temperature is lower than setpoint)

<br><br>
Press the "Left" and "Right" buttons together to enter the time configuration mode.<br>
Now you can set the time. The "Middle" button switches to the next option.<br>

![time configuration view](./m_display_timeconf.jpg)<br><br>

To set "day" or "night" temperature return to the main screen and press "Middle" button. Then use "left" and "right" buttons to change setpoint value.<br>

![day/night temperature configuration view](./m_display_t_conf.jpg)<br><br>

## License
GPLv3. <br>
This product is distributed in the hope that it will be useful,	but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.<br>

## Author
<br>
gonzho АТ web.de (c) 2018-2021<br>

## Appendix A: bill of materials
| Part | Quantity |
| ------------- | ------------- |
| **1206 Resistors:**    ||
| 100      | 2 |
| 120      | 2 |
| 1K       | 4 |
| 10K      | 9 |
| 100K     | 4 |
| **1206 Caps:**    ||
| 0.01uF      | 4 |
| 0.1uF       | 9 |
| 1uF         | 1 |
| 10uF        | 10 |
| **KF124 terminals:** ||
| KF124-3.81-3P     | 2 |
| KF124-3.81-2P     | 1 |
| **SOP(SOIC) ICs:**    ||
| DS3231M     (SOIC-16)     | 1 |
| ADM2587EBRWZ (SOIC-20)    | 2 |
| **Others:**    |                |   
| MMBT2222A (SOT-23-3)    | 1 |
| LM7805 (TO-220)         | 1 |
| 1N4148W (SOD-123)       | 1 |
| 0.22F  11.2x6.5 (supercap)    | 1 |
| 10nF HV-9.0x3.0 (blue disc 2kV HV cap)    | 2    |
| KLS7-TS6601-13.0-180 (13 mm tact button)    | 3    |
| 2.54_pins_x40_female          | 1 |
| 2.54_pins_x4                  | 1 |
| BUZZER-R9.0-2P-4.0                     | 1    |
| ARDUINO PRO MINI              | 1 |
| 1602 display with i2c         | 1 |
| 1602 Plastic case             | 1 |

## Author
<br>
gonzho АТ web.de (c) 2018-2021<br>

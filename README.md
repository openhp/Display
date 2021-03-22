### Valden: Remote Display v1.x
<b>  This device allows you to conrol the [Valden Heat Pump](https://github.com/openhp/HeatPumpController/) via remote display. Display can be used with a wire up to few hundred meters long.</b>

## Specs
- 12V 0.5A DC power supply, 
- build-in RTC,
- Day/Night temperature set,
- LCD 16x02,
- RS485 connection to heat pump,
- secondary RS485 connection to external systems integration ( [example here](https://github.com/openhp/HP-integration-example/) ),
- JSON,
- MODBUS.


## Changelog and history
- 2019-2020: prototyping, installations, development, tests, revisions, redisigns,
- Dec 2020: [Service display](https://github.com/openhp/ServiceDisplay/) software fork created,
- Mar 2021: Documentation and release stage.
- 
## Get your own copy and PCB assembly
- download the PCB gerber file, [Valden RemoteDisplay Gerber](./Valden_RemoteDisplay_Gerber.zip)
- find in Google, [where to order a printed circuit board](https://www.google.com/search?q=order+pcb+gerber) (keywords: order pcb gerber), place an order,
- order electronic components, see BOM (Bill Of Materials) appendix below,
- solder electronic components. {- assembly instructions here-}

## Firmware upload
The process is the same as for others Arduinos:
- connect USB-> UART converter,
- start Arduino IDE,
- open the firmware file,
- select board and MCU in the Tools menu (hint: we are using "mini" board with 328p MCU),
- press the "Upload" button in the interface and "Reset" on the Arduino.

For arduinos with old bootloader you need to update it. (Tools-> Burn Bootloader).<br>
For successful compilation, you must have "SoftwareSerial", "OneWire" and "DallasTemperature" installed (see Tools -> Manage Libraries).<br>
Note that software serial must be downloaded from Display guthub repository and located at same directory as main source. Library is slightly modidied.<br>
Configuration not needed, display will work as at pictures below after connecting to heat pump.<br>

## Wiring and installation
Wiring is very simple: <br>
- RS485 through a wire of the desired length to the remote control display (if used, another control method is a local computer with a USB-UART converter, you may like it for the first time). Note that A is connected to A in the display, B to B and GND to GND,
- you can power the display from a 12V controller, the board has 12V and GND secondary pins,

## Usage

 ![main view](./m_display_main.jpg)<br>
 ![time configuration view](./m_display_timeconf.jpg)<br>
 ![day/night temperature configuration view](./m_display_t_conf.jpg)<br>

## License
GPLv3. <br>
This product is distributed in the hope that it will be useful,	but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.<br>

## Author
<br>
gonzho АТ web.de (c) 2018-2021<br>

## Appendix D: bill of materials
| Part | Quantity |
| ------------- | ------------- |
| **1206 Resistors:**	||
| 100K	| 2	|

## Author
<br>
gonzho АТ web.de (c) 2018-2021<br>

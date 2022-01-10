# NOWAE - KiCad6 Schematic Symbols Design Rules

Ispired by [Library Conventions](https://klc.kicad.org/symbol/).
This document contains our rules to design schematic symbols and is more or less the same of KiCad Conventions.

## Symbol libraries files

Symbol libraries are individual `.lib` files.
Symbol library names must be defined based on the priority list below, with each element separated by the underscore character:
* Function (e.g. Sensor, Amplifier, MCU)
* Sub-function (e.g. Temperature, CurrentSense)
* Manufacturer name (e.g. Atmel, Infineon)
* Symbol series name (e.g. PIC24, STM32)
* Extra library descriptors

## Symbol name

* General symbol naming guidelines
  * Library naming should not be duplicated in symbol name
  * If symbol with same name exists for multiple manufacturers, the manufacturer name is written first
  * Fully specified symbols are named based on the manufacturer part number

* Non-functional variations in part number should be replaced with wildcard.

* Separate symbol must be drawn for each footprint: where parts are available in multiple footprint options, a separate symbol must be drawn for each footprint.

## General symbol requirements

* Origin is centered on the middle of the symbol.

* Text fields should use a common text size of `1.27mm` (pin name, pin number, value, reference, footprint, datasheet).

* Symbol outline body must have a line width of `0.254mm`.

* Symbols with complex functionality may incorporate simple functional diagrams.
 
* Pin connection points must be placed outside of the symbol

* For IC components with exposed pads, the number of the exposed pad should start one greater than the pin-count of the footprint.

* For symbols with multiple units that are drawn separately, where the units share common power pins, the power pins must be added to the first part (A).

## Pin requirements

* Using a `2.54mm` grid, pin origin must lie on a grid node (IEC-60617),

* Pins should have a length of at least `2.54mm`

* Pin numbers must be unique (no two pins may have the same number)

* Where possible, pins should be grouped by similar function, rather than by their physical location on the associated footprint.

* Pin Electrical type should be set to match the appropriate pin function.

* Pins not connected on the footprint may be omitted from the symbol.

* Active low pins should be designated using a bar above the symbol name.

## Footprint Association

* Symbols with a default footprint link to a valid footprint file.

## Metadata

### Component Reference Designator (RefDes)

|Designator|Component Type|
|-|-|
|BT|Battery|
|C|Capacitor|
|D|Diode|
|DL|Diode LED|
|F|Fuse|
|FB|Ferrite bead|
|JP|Jumper|
|K|Relay|
|L|Inductor|
|M|Motor|
|P|Connector|
|Q|Transistor|
|R|Resistor|
|SW|Switch|
|T|Transformer|
|TP|Test point|
|U|Integrated Circuit|
|Y|Crystal/Oscillator|
|Z|Zener diode|

### Symbol metadata fields

* Symbol and alias fields and metadata filled out as required:
  * **Reference** field is selected appropriately for the symbol and is visible,
  * **Value** field contains the name of the symbol and is visible
  * **Footprint** field contains footprint link for fully specified symbols and must be invisible
  * **Datasheet** entry is filled out, and is invisible
  * TODO

## Special Symbols

* Power flag symbols are special symbols in KiCad, used to designate global nets. These symbols use a special RefDes value to indicate that they must be considered as global power flags. Label dimension should be `1.27mm`

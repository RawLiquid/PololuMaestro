# Pololu Maestro Servo Controller library for Arduino

Version: 1.0.0<br/>
Release date: 2015 Jan 12<br/>
[www.pololu.com](http://www.pololu.com/)

## Summary

This is a library for the Arduino IDE that helps interface with a
[Maestro Servo Controller](http://www.pololu.com/maestro). It communicates with
Maestros using the Serial Protocol described in the
[Maestro Servo Controller User's Guide](http://www.pololu.com/docs/0J40) Section
5, "Serial Interface".

## Supported platforms

This library is designed to work with the Arduino IDE versions 1.0.x and 1.5.x,
and will probably not work with older versions.

This library supports any Arduino-compatible board.

## Getting started

### Hardware

The Maestro Servo Controllers can be purchased from
[Pololu's website](http://www.pololu.com/maestro). Before continuing, careful
reading of the
[Maestro Servo Controller User's Guide](http://www.pololu.com/docs/0J40) is
recommended.

The minimal connections required for using this library are:

    Arduino TX pin (see table below) - Maestro RX
    Arduino GND                      - Maestro GND

The example sketches try to use a hardware serial port on your Arduino if one is
available. The one used is defined by SERIAL_PORT_HARDWARE_OPEN. The pins for
this serial port are different depending on which Arduino you are using.

| Microcontroller Board | Hardware serial? | MCU RX pin | MCU TX pin |
|-----------------------|------------------|------------|------------|
| A-Star 32U4           |        Yes       |      0     |      1     |
| Arduino Leonardo      |        Yes       |      0     |      1     |
| Arduino Micro         |        Yes       |      0     |      1     |
| Arduino Mega 2560     |        Yes       |     19     |     18     |
| Arduino Due           |        Yes       |     19**   |     18     |
| Arduino Uno           |        No        |     10     |     11     |
| Arduino Yun           |        No        |     10     |     11     |

If you would like to read information from the Maestro, like in the Input
example sketch, you need to make one additional connection:

    Arduino RX (see table above) - Maestro TX

** The Due's serial port is 3.3&nbsp;V, so it should not be directly connected
to the Maestro's 5&nbsp;V TX line. A voltage divider or level shifter can be
used.

### Maestro configuration

Before using the example sketches, you should go to the Serial Settings tab in
the Maestro Control Center and apply these settings:

* Serial mode: UART, fixed baud rate
* Baud rate: 9600
* CRC disabled

### Software

Download the
[maestro-arduino library from GitHub](https://github.com/pololu/maestro-arduino),
decompress it, and drag the "PololuMaestro" folder into the "libraries"
subdirectory inside your Arduino sketchbook directory. You can view your
sketchbook location by selecting File->Preferences in the Arduino environment.
If there is not already a "libraries" folder in that location, you should create
it yourself. After installing the library, restart the Arduino environment.
Example code for using this library can be found in the File->Examples menu.

## Examples

Several example sketches are available that show how to use the library. You can
access them from the Arduino IDE by opening the "File" menu, selecting
"Examples", and then selecting "PololuMaestro". If you cannot find these
examples, the library was probably installed incorrectly and you should retry
the installation instructions above.

## Documentation

For complete documentation of this library, including many features that were
not mentioned here, see
[the maestro-arduino documentation](https://pololu.github.io/maestro-arduino/).

## Version history

* 1.0.0 (2015 Jan 12): Original release.

# Build Cypress USB Serial Library for Android

This library is meant to be built within Android AOSP.
Applications can reference this as shared lib in their blueprint files.
Please see example application for reference.

For native build on various platforms with cmake, please see this project [1].

[![LGPLv2.1+ License](http://img.shields.io/badge/license-LGPLv2.1+-blue.svg)](https://www.gnu.org/licenses/lgpl-2.1.html)

## Target Hardware

Cypress has a range of USB-Serial Bridge Controller devices to assist embedded applications.
These devices can work in two modes.

Quote from vendor's homepage [4][4]:

```
In CDC mode (CDC device class) the device will come up as Virtual COM Port (VCP) device.
Native APIs can be used to access the device in CDC mode for all the OS.
In Vendor mode, the device enumerates as a USB device and is accessed using
the Cypress provided library (for all OS).
```

This library enables usage of the later mode.

## Dependencies

1. libusb 1.0.9 (or higher) is required for compilation and functioning of the
   APIs in the library. [libusb][2] should be present in your AOSP environment.

## Integration and Build

1. Clone into android project (e.g. /\<android\>/external)

2. source and lunch for your device

3. make libcyusbserial

## Note
Refer to the [CyUSBSerial API documentation][3] for descriptions of all the
vendor mode APIs. The header file of the library is in
`./include/CyUSBSerial.h`.

[1]: https://github.com/cyrozap/libcyusbserial
[2]: https://android.googlesource.com/platform/external/libusb/
[3]: http://www.cypress.com/?docID=45725
[4]: https://www.cypress.com/documentation/software-and-drivers/usb-serial-software-development-kit

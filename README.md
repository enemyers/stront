# stront

Split keyboard with 38 keys, LCD display and trackpad (Azoteq or Cirque).

## Features

- MX, KS-33 or Choc switches
- wired split with USB-C or TRRS interconnection
- 38 keys
- roller/rotary encoders
- LCD display (1.69" 240x280 by default)
- Azoteq/Cirque trackpad support
- 2-key pinky columns
- 3D printed cases
- [VIK](https://github.com/sadekbaroudi/vik) support - **MX/KS version only**

**PCB has all SPI/I2C contacts exposed, so any other device can be used instead, it's just a matter of changing the case (at least that's the idea).**

## Photos

#### MX Version

![](./images/mx.jpg)
![](./images/mx3.jpg)
![](./images/tps65.jpg)

#### Choc version

![](./images/top.jpg)
![](./images/pcb.jpg)

#### Display with PC companion app

https://github.com/zzeneg/stront/assets/910255/bb812821-9b2b-454a-a9a5-45d696a1f5aa

## Firmware

[Companion app](https://github.com/zzeneg/qmk-hid-host) for Raw HID communication.

QMK

- [source code](https://github.com/zzeneg/qmk_firmware/tree/feature/stront/keyboards/stront)
- [pre-compiled files](./firmware/qmk/)

Vial

- [source code](https://github.com/zzeneg/vial-qmk/tree/feature/stront)
- [pre-compiled files](./firmware/vial/)

Compiled versions:

- `default` - sample keymap with home row mods. Not recommended for longer use - create your own.
- `hid` - default keymap with HID support. Requires companion application.
- `zzeneg` - my highly customized layout.
- `*-rect` - version with rectangular display (ST7789 240x280)
- `*-round` - version with round display (GC9A01 240x240)
- `*-flat` - version with flat Cirque
- `*-curved` - version with curved Cirque
- `*-mirror` - version with trackpad on left and display on right side

## Build Guide

[MX/KS version](./build-guide/mx/readme.md)

[Choc version](./build-guide/choc/readme.md)

## Azoteq touchpads - MX/KS version only ⚠️

- covers (right side only) - [TPS43](./stl/mx/azoteq-tps43.stl), [TPS65](./stl/mx/azoteq-tps65-right.stl) (tested)
- firmware - experimental support [source code](https://github.com/zzeneg/qmk_firmware/tree/feature/zzeneg/keyboards/stront)
- to connect touchpad you can use either [VIK adapter](https://github.com/sadekbaroudi/vik/tree/master/pcb/azoteq-tps) or solder wires directly from Azoteq pads to I2C contacts on PCB

## VIK - MX/KS version only ⚠️

> VIK is a standard for a data interface between printed circuit boards. It is intended to provide modularity between a mechanical keyboard PCB and additional features.

[VIK repository ](https://github.com/sadekbaroudi/vik)

#### Certification card

| Category               | Classification       | Response                          |
| ---------------------- | -------------------- | --------------------------------- |
| FPC connector          | Required             | :heavy_check_mark:                |
| Breakout pins          | Recommended          | :heavy_check_mark:                |
| Supplies: SPI          | Strongly recommended | :heavy_check_mark: <sup>[1]</sup> |
| Supplies: I2C          | Strongly recommended | :heavy_check_mark: <sup>[1]</sup> |
| I2C on main PCB        | Discouraged          | No                                |
| I2C pull ups           | Informative          | Optional<sup>[2]</sup>            |
| Supplies: RGB          | Strongly recommended | :heavy_check_mark:                |
| Supplies: Extra GPIO 1 | Required             | Digital                           |
| Supplies: Extra GPIO 2 | Required             | Digital                           |

**[1]**: I2C and SPI use same pins, so you can use only one or the other, not both. Selection is configured in firmware.

**[2]**: PCB has pads designed for 1206/3216 SMD resistors, you can solder them manually if needed.

![image](https://github.com/zzeneg/stront/assets/910255/4969cd8e-7a2b-40d1-b238-135fe3c2e75f)

#### VIK usage

Built-in display and trackpad use the same interface, so any additional VIK module will have to replace one of them. Depending on the size it can integrated into the cover or a standalone case.

All possible connectors support VIK - FPC horizontal on the back, FPC vertical on the front and the breakout pins.

## Support

If you like my work and want to support my future designs, please consider [sponsorship](https://github.com/sponsors/zzeneg), ordering from PCBWay using my shared projects - [Choc](https://www.pcbway.com/project/shareproject/Stront_low_profile_keyboard_85ec2664.html) and [MX/KS](https://www.pcbway.com/project/shareproject/Stront_MX_KS_33_keyboard_6a70e49a.html), or using [referral link](https://pcbway.com/g/3wpLAF) for signing up.

#### Sponsors

Thank you very much for your support!

<a href="https://shop.beekeeb.com" target="_blank"><img src="https://beekeeb.com/beekeeb-logo.png" align="left" width="200" ></a>

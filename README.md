# GingerLight

Yet another CN5816-based LED boost driver board design for 36v 40w COB LED, like CREE CXB2540/3040/3540.

## Usage

- Provide a 20v, 2A DC input (e.g. from a USB PD charger)
- Hook up a 36v 40w LED, like CREE CXB2540/3040/3540 (I've tested with CREE CXB2540 for now), remember to put on a heatsink or otherwise it may become a bit smoky!
- It should work now

## Fine adjustments

- According to CN5816's official datasheet and component calculator:
- When `Vin` = **20v**, `Vled` = **36v**, `Iout` = **0.8A**:
  - <img width="684" alt="image" src="https://github.com/huming2207/gingerlight/assets/4463497/4808d9f5-904e-40f8-9a26-e0c03cf795f2">
  - If Vled goes too high, try reducing R1 to 4260kohm
- If you don't want it to be that bright, or you can't afford a big heatsink, then try increasing `R6` (the `Rsw`) to something like 0.2ohm.

## Caveats

According to Consonance FAE, when calculating the resistor divider for voltage threshold reference, the `Vout` here means `Vin` + `Vled`:

<img width="720" alt="image" src="https://github.com/huming2207/gingerlight/assets/4463497/95d61678-8938-495f-8d93-b981c3afa04b">

For example, my `Vin` is 20v, `Vled` (the LED's `Vf`) is 36v, then `Vout` needs to be 56v, not 36v.


## License 

CC-BY-NC-SA 4.0

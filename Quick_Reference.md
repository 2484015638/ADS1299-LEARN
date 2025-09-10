# ADS1299 BIAS Pin Quick Reference

## Pin Summary

| Pin Name | Pin # | Function | Typical Connection |
|----------|-------|----------|-------------------|
| BIASIN   | 6     | BIAS input to multiplexer | Common-mode sensing point |
| BIASREF  | 5     | BIAS reference voltage | Mid-supply (1.65V @ 3.3V) |
| BIASOUT  | 7     | BIAS drive output | RLD electrode via resistor |
| BIASINV  | 8     | Inverted BIAS output | Usually not connected |

## Quick Component Values

### Single Device Setup
- **BIAS Drive Resistor**: 2.2kΩ (performance) or 220kΩ (safety)
- **Reference Capacitor**: 1μF ceramic
- **Reference Resistors**: 10kΩ voltage divider

### Multi-Device Setup  
- **Master Device**: Same as single device
- **Slave Devices**: BIASOUT not connected, BIASREF shared
- **Common BIASIN**: All devices connected to same sensing point

## Safety Guidelines

- **Maximum Current**: 10μA DC (IEC 60601)
- **Isolation**: 4kV minimum for patient safety
- **Electrode Impedance**: <5kΩ for optimal performance

## Common Issues & Solutions

| Problem | Likely Cause | Solution |
|---------|--------------|----------|
| High 50/60Hz noise | Poor BIAS electrode contact | Check RLD electrode impedance |
| Saturated BIAS output | Wrong BIASREF voltage | Set BIASREF to AVDD/2 |
| System oscillation | High capacitive load | Add 100Ω series resistance |

## Datasheet References

- **Section 8.3**: Pin descriptions for BIAS pins
- **Figure 39**: Multi-device BIAS configuration
- **Section 9.1**: Electrical characteristics
- **Section 11**: Application information

---
*For detailed explanations, see README.md and BIAS_Configuration_Guide.md*
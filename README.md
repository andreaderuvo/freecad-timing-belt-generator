# FreeCAD Timing Belt Generator

A parametric timing belt generator for FreeCAD. Create accurate 3D models of timing belts for 3D printing, CNC machining, or mechanical design.

![FreeCAD Timing Belt](https://img.shields.io/badge/FreeCAD-0.19+-blue.svg)
![License](https://img.shields.io/badge/license-CC%20BY--SA%203.0-green.svg)

## Features

- 🔧 **Multiple Belt Profiles**: S3M, GT2, T2.5, T5, MXL, HTD series, and more
- 🎯 **Accurate Tooth Profiles**: Based on manufacturer specifications
- ⚡ **Fast Generation**: Optimized for FreeCAD's geometry engine
- 🎨 **GUI Interface**: Easy parameter selection with preview
- 📐 **Fully Parametric**: Customize tooth count, width, and profile

## Supported Belt Profiles

- **S3M** - 3mm pitch (popular in RC cars)
- **GT2** - 2mm pitch (3D printers)
- **T2.5** - 2.5mm pitch (light automation)
- **T5/T10** - 5mm/10mm pitch (industrial)
- **MXL** - 2.032mm pitch (miniature applications)
- **HTD 3mm/5mm/8mm** - High Torque Drive
- **XL/L** - Imperial pitch belts
- And more!

## Installation

1. Download `TimingBeltGenerator.FCMacro`
2. In FreeCAD: **Macro** → **Macros...** → **User macros**
3. Place the file in the macro directory
4. Execute from the Macro menu

## Usage

### Quick Start (GUI)
```python
# Run the macro - opens parameter dialog
```

### Python Console
```python
import TimingBeltGenerator

# Quick functions
belt_72()      # S3M 72 teeth
gt2_60()       # GT2 60 teeth
t25_60()       # T2.5 60 teeth

# Custom belt
create_timing_belt(
    tooth_count=80, 
    profile="GT2_2mm",
    belt_width=6,
    use_accurate_teeth=True
)
```

### Available Functions

| Function | Description |
|----------|-------------|
| `create_belt_gui()` | Opens parameter dialog |
| `belt_72()` | S3M 72 teeth (RC car standard) |
| `belt_90()` | S3M 90 teeth |
| `gt2_60()` | GT2 2mm, 60 teeth |
| `gt2_80()` | GT2 2mm, 80 teeth |
| `t25_60()` | T2.5 60 teeth |
| `mxl_100()` | MXL 100 teeth |

### Custom Parameters

```python
create_timing_belt(
    tooth_count=120,          # Number of teeth
    belt_width=9,            # Width in mm
    profile="S3M",           # Belt profile
    use_accurate_teeth=True  # Use accurate (True) or simple (False) teeth
)
```

## Examples

### RC Car Belt (S3M)
```python
# Typical 1/10 scale RC car belt
create_timing_belt(tooth_count=72, profile="S3M", belt_width=9)
```

### 3D Printer Belt (GT2)
```python
# Common 3D printer timing belt
create_timing_belt(tooth_count=80, profile="GT2_2mm", belt_width=6)
```

### Large Belt (simplified teeth for speed)
```python
# 200+ teeth belt with simplified geometry
create_timing_belt(tooth_count=200, profile="S3M", use_accurate_teeth=False)
```

## Belt Profile Specifications

| Profile | Pitch (mm) | Default Width (mm) | Common Use |
|---------|------------|-------------------|------------|
| S3M | 3.0 | 6 | RC cars, robotics |
| GT2_2mm | 2.0 | 6 | 3D printers |
| T2.5 | 2.5 | 6 | Light machinery |
| T5 | 5.0 | 10 | Industrial |
| MXL | 2.032 | 6.35 | Miniature |
| HTD_3mm | 3.0 | 9 | High torque |

## Tips

- For belts with 100+ teeth, consider using `use_accurate_teeth=False` for faster generation
- The generated belts are ready for 3D printing or CNC machining
- Use **View** → **Fit All** after generation to see the complete belt
- Export as STL for 3D printing or STEP for CAD integration

## Technical Details

The tooth profiles are mathematically accurate representations based on manufacturer specifications. The macro creates proper FreeCAD Part objects that can be further modified or integrated into assemblies.

## Credits

Inspired by the [OpenSCAD Parametric Timing Belt Generator](https://github.com/cmlarsen/scad-parametric-timing-belt-generator) project. Ported and optimized for FreeCAD by andreaderuvo.

## License

Creative Commons - Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests on GitHub.

## Future Enhancements

- [ ] Additional belt profiles (S5M, S8M, etc.)
- [ ] Belt path generator for custom shapes
- [ ] Pulley generator companion
- [ ] Belt tension calculator
- [ ] Animation support

---

**Note**: Requires FreeCAD 0.19 or newer. Tested on FreeCAD 0.21.
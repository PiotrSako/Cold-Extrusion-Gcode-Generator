# Cold Extrusion · G-code Generator

**▶ Live app: https://piotrsako.github.io/Cold-Extrusion-Gcode-Generator/**

A single-file, browser-based G-code generator for **cold extrusion / syringe-pump dispensing** on Marlin-based 3D printers (developed for the Creality Ender 3). No installation, no server, no dependencies — everything runs locally in your browser.

Interface available in **English** and **Polish** (EN/PL switch in the header).

## What it does

The tool turns your printer's extruder stepper into a precise syringe pump. You enter the syringe and drive-mechanics parameters, and it generates ready-to-run G-code for dispensing a set volume at a set flow rate.

### Modes

- **Syringe mode** — the main mode: pick a syringe preset (or enter the plunger diameter manually), set the volume (mL / µL) and flow rate (mL/min, µL/min, µL/s), and generate the dispensing G-code. Includes:
  - screw lead (mm/rev, e.g. M4 ≈ 0.7), steps per revolution and microstepping,
  - optional automatic `M92` extruder steps-per-mm configuration,
  - plunger direction selection (CW/CCW) with custom labels,
  - motor RPM readout for transparency about actual motor speed,
  - **approximate maximum plunger force and barrel pressure**, from motor torque, screw efficiency and lead — the pressure turns amber above 3 bar and red above 10 bar, where typical disposable syringes start to leak.
- **Continuous test** — move a total distance in fixed step lengths (for calibration and dry runs).
- **Cycle test** — repeated push/pull cycles (e.g. for checking backlash or priming).

## Usage

1. Open the [live app](https://piotrsako.github.io/Cold-Extrusion-Gcode-Generator/) — or download `generator_zimnej_ekstruzji.html` and open it in any modern browser.
2. Enter your syringe and mechanics parameters.
3. Generate and copy/save the G-code, then run it on your printer (e.g. from SD card or a host like OctoPrint/Pronterface).

> ⚠️ **Safety note:** cold extrusion requires either `M302` (allow cold extrusion) or appropriate firmware settings, and the generated motion depends on your hardware. Always verify the first run with an empty or water-filled syringe.

## Files

| File | Description |
|---|---|
| `generator_zimnej_ekstruzji.html` | The complete application (HTML + CSS + JS in one file) |
| `index.html` | Redirect to the app for GitHub Pages |

## License

[MIT](LICENSE) © 2026 Piotr Sakowski

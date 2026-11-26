# Third-party notices

WarRig's own work is under the PolyForm Noncommercial License 1.0.0 (see `LICENSE.md`).
The parts below are made by others. They are not covered by that licence and keep their own terms,
which allow them to be used and shipped with WarRig.

## LVGL (graphics library, including its QR code generator)

Shipped in source form in the WarRig package (`lvgl/`) and built into the screen program.
Licence: MIT. The full text is in `lvgl/LICENCE.txt` in the package.
The small libraries that come inside LVGL (for example its QR code generator and TrueType reader)
keep their own licence files next to their code in `lvgl/src/libs/`.

```text
MIT licence
Copyright (c) 2025 LVGL Kft

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

## Inter (typeface)

Shipped in `fonts/` as a Latin subset converted to TrueType outlines.
Copyright 2016-2023 The Inter Project Authors (https://github.com/rsms/inter).
Licence: SIL Open Font License 1.1. The full text is in `fonts/Inter-LICENSE.txt` in the package.
The fonts may be used, changed and shipped with other software, but may not be sold on their own.

## Print macros based on the printer's stock configuration

`macros/warrig_macros.cfg` and `macros/warrig_mesh.cfg` contain copies of the printer maker's own
PRINT_START, G29 and related macros, changed to add WarRig's options. Those copied parts stay the
work of their original authors and under their original terms; the PolyForm licence covers only
WarRig's own changes and additions.

## Not shipped with WarRig

These are used by WarRig but are not part of it, and are not covered by its licence:

- Klipper and Moonraker (GPL-3.0) are already on the printer. WarRig talks to them; it does not change or ship them.
- Tailscale is downloaded from Tailscale by the PC tool only when you set up remote access, under Tailscale's own terms.
- ntfy is a separate app and service you choose to use for phone alerts, under its own terms.

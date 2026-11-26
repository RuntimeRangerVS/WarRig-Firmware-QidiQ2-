<p align="center">
  <img src="docs/images/hero.png" alt="WarRig Firmware Mod for the QIDI Q2" width="100%">
</p>

<p align="center">
  <img alt="Printer" src="https://img.shields.io/badge/printer-QIDI%20Q2-ff7a12">
  <img alt="Stock firmware" src="https://img.shields.io/badge/stock%20firmware-01.01.02.01%20to%2001.01.03.04-555">
  <img alt="Version" src="https://img.shields.io/badge/WarRig-V1.0%20release%20candidate-ff9a3c">
  <img alt="Languages" src="https://img.shields.io/badge/languages-8-555">
</p>

# WarRig Firmware Mod for the QIDI Q2

WarRig replaces the stock touchscreen program on a QIDI Q2 with its own, and adds a set of print macros
that make print starts shorter and the filament box easier to live with. It runs on the printer next to
the stock Klipper and Moonraker. Nothing is flashed: it is installed, tested and removed again from a
Windows PC, and the stock screen is kept on the printer the whole time, so you can always go back.

**WarRig is an unofficial Firmware Mod. It is not made, endorsed or supported by QIDI.** Read
[Pros and cons](#pros-and-cons) before you install it.

---

## Contents

- [Highlights](#highlights)
- [The screen](#the-screen)
- [Pros and cons](#pros-and-cons)
- [Compatibility](#compatibility)
- [What you need](#what-you-need)
- [Install](#install)
- [Try, update, remove](#try-update-remove)
- [The PC tool](#the-pc-tool)
- [Full test](#full-test)
- [Remote access and phone alerts](#remote-access-and-phone-alerts)
- [The WarRig ecosystem](#the-warrig-ecosystem)
- [Print start and the print macros](#print-start-and-the-print-macros)
- [Safety](#safety)
- [Languages and looks](#languages-and-looks)
- [FAQ and troubleshooting](#faq-and-troubleshooting)
- [Credits](#credits)
- [Disclaimer](#disclaimer)

---

## Highlights

- **A screen built for touch.** Home, Files, Filament, Control and Settings in a bottom tab bar, big tiles,
  side sheets that open over the page you are on, changes that show the moment you tap.
- **Shorter print starts, your way.** Per print (or as a default): probe the bed mesh or use the saved one,
  level the gantry or skip it, reload the filament or keep what is in the head.
- **A filament box that behaves.** A drawn box with every slot, load / unload / eject, drying in the box or
  on the bed, spool turning while drying, auto refill, RFID, a guided external-spool load, and a choice
  after every print: leave the filament in the head or send it back to the tube.
- **See your print.** A 3D layer view of the file (also for sliced `.gcode.3mf`), a 3D bed mesh you can turn
  with a finger, live flow and pressure advance on the job card, full print details.
- **Safety first.** Risky tools lock while printing, temperatures are held to the printer's own limits, Stop
  asks twice, and if the screen ever crashes the stock screen takes over by itself.
- **Easy to try, easy to undo.** A 3-minute test run, a one-step remove, and a keeper that puts your
  calibration and macros back if a stock update replaces them.
- **Part of an ecosystem.** WarRig Slicer, the WarRig Companion app and the PC tool share settings with the
  screen through the printer - no account and no cloud needed at home.
- **Remote access and phone alerts** with Tailscale and ntfy, set up from the screen or the PC, connected to a
  phone by scanning one QR code.
- **A full test** that checks the whole install - program, macros, box, sensors, system, network - and
  changes nothing.

---

## The screen

<p align="center"><img src="docs/images/gallery.png" alt="Screens of the WarRig Firmware Mod" width="100%"></p>

<details>
<summary><b>Home</b> - the printer at a glance</summary>
<br>

Printing: file, layer, time left and the finish time, a progress ring, live flow and pressure advance,
nozzle / bed / chamber / Z offset chips, Pause, Skip object and Fans. Tap the job card for the 3D layer
view. Idle: the last print with Reprint, the loaded filament and the same chips.

<img src="docs/images/screens/home.png" width="49%"> <img src="docs/images/screens/home_idle.png" width="49%">
</details>

<details>
<summary><b>Filament and box</b> - slots, loading, drying</summary>
<br>

Every slot of every box with its colour and material, the one in the head ringed, humidity and box
temperature. Load, unload and eject per slot; drying in the box (with spool turning, only when the slots are
empty) or loose spools on the heated bed; box options for auto refill, RFID reading and faster feed. The
external spool loads step by step: heat, push the filament in, Feed until it comes out, Yes, flush.

<img src="docs/images/screens/filament.png" width="49%"> <img src="docs/images/screens/xl1_push.png" width="49%">
<img src="docs/images/screens/f_bed_dry.png" width="49%"> <img src="docs/images/screens/box_options.png" width="49%">
</details>

<details>
<summary><b>Files, start print and the 3D layer view</b></summary>
<br>

The file list with thumbnails (or a 3D picture when the slicer made none), print details including sliced
`.gcode.3mf` files, and the Start print page: colour to slot, build plate, and switches for this print only.
The 3D layer view shows the file layer by layer, by colour, feature or speed.

<img src="docs/images/screens/files.png" width="49%"> <img src="docs/images/screens/details_3mf.png" width="49%">
<img src="docs/images/screens/start_panel.png" width="49%"> <img src="docs/images/screens/g3d_preview.png" width="49%">
</details>

<details>
<summary><b>Control, temperatures and the bed mesh</b></summary>
<br>

Temperatures with a live graph and material presets, a number keypad that knows the limits (the chamber is
off or 40-65 °C), fans, speed, motion, and the bed mesh flat or in 3D.

<img src="docs/images/screens/temperature.png" width="49%"> <img src="docs/images/screens/kp_chamber_35.png" width="49%">
<img src="docs/images/screens/bedmesh_3d_turned.png" width="49%"> <img src="docs/images/screens/print_done.png" width="49%">
</details>

<details>
<summary><b>Toolbox</b> - tools, levelling, tuning, care</summary>
<br>

Clean nozzle, cut filament, park; full calibration (Z tilt, bed mesh, resonance), Z offset, bed screws;
input shaper, PID tuning, pressure advance, flow rate, extruder steps; and maintenance reminders on the
factory schedule.

<img src="docs/images/screens/tools.png" width="49%"> <img src="docs/images/screens/calibration_tuning.png" width="49%">
</details>

<details>
<summary><b>Settings and status</b></summary>
<br>

Wi-Fi, Display & sound (brightness, sleep, beeper, lights after a print, touch check, theme colour),
language, print options, toolbox and status (Klipper, Moonraker, box, macros, network, CPU, memory,
storage, restart, logs to a USB stick, power).

<img src="docs/images/screens/settings.png" width="49%"> <img src="docs/images/screens/health.png" width="49%">
<img src="docs/images/screens/f_print_options.png" width="49%"> <img src="docs/images/screens/wifi.png" width="49%">
</details>

---

## Pros and cons

Be honest with yourself about these before installing. WarRig is a hobby project for one printer model.

### Pros

| | |
|---|---|
| **Faster, clearer screen** | Built around touch, with quick side sheets, instant feedback, 8 languages and theme colours. |
| **Shorter print starts** | Skip the bed mesh when a saved one is good, skip gantry levelling, keep the loaded filament - per print or as a default. |
| **Better box handling** | Leave-in-head after a print, guided external spool, drying with spool turning, auto refill, RFID, eject. |
| **More to see** | 3D layer view, 3D bed mesh, live flow and pressure advance, details for `.gcode.3mf` files. |
| **Safety built in** | Tools lock while printing, heater limits come from the printer, Stop asks twice, crash fallback to the stock screen, freeze watchdog, power-loss resume. |
| **Low risk to try** | 3-minute test, one-step remove, nothing flashed, the stock screen stays on the printer, original files are backed up. |
| **Survives stock updates** | The keeper puts calibration and macros back by itself if a stock update replaces them (on tested firmware). |
| **Works across firmware** | One install adapts itself to the box commands of 01.01.02.x and 01.01.03.x. |
| **Ecosystem** | Slicer, Companion app and PC tool share settings with the screen through the printer, no account needed. |
| **Remote and alerts without a vendor cloud** | Tailscale for private remote access, ntfy for phone alerts, both optional. |
| **Self-checking** | A full test and diagnostic logs from the PC tool. |

### Cons

| | |
|---|---|
| **Unofficial** | Not made or supported by QIDI. Support questions about the stock firmware may be harder while it is installed, and it may affect your warranty - check with QIDI if that matters to you. |
| **Stock updates are held back** | The stock updater lives in the stock screen, so it does not run while WarRig is the screen. To take a stock update: remove WarRig (PC tool option 3), update, install WarRig again. |
| **Some stock features are off** | The stock camera failure detection is switched off, and what lives only inside the stock screen program (such as its update check) is not available. The camera page is not on the WarRig screen - use the Companion app or the web interface. |
| **Needs a Windows PC to install** | The PC tool uses SSH, which is built into Windows 10 and 11. You need the printer's login password once. (A USB installer can be made for other printers of the same firmware.) |
| **First install takes a while** | WarRig is compiled on the printer: about 10-20 minutes the first time, a minute or two for updates. |
| **Hardware-tested on two versions** | Real-printer testing was on 01.01.03.02 and 01.01.03.04. 01.01.02.x and 01.01.03.01 are checked against their stock configuration files, not yet on a printer. |
| **Some parts are new** | The guided external-spool load, Tailscale setup and the `.gcode.3mf` details are new in this release and need real-world testing. |
| **Planned, not here yet** | The camera print watch (spotting failed prints and stopping them) and the printer sending its own alerts are planned; today you can set alerts up and send a test from the PC. |
| **Small screen, dense pages** | 480 x 272 pixels: some pages hold a lot. Translations may have rough spots. |
| **One printer model** | Built for the QIDI Q2 only. |

---

## Compatibility

| Stock firmware | Box commands | Status |
|---|---|---|
| 01.01.03.04 | 01.01.03 | tested on a printer |
| 01.01.03.02 | 01.01.03 | tested on a printer |
| 01.01.03.01 | 01.01.03 | checked against its configuration |
| 01.01.02.01 - 01.01.02.04 | 01.01.02 (`MULTI_COLOR_LOAD`) | checked against its configuration |
| newer than 01.01.03.04 | - | the installer asks before going ahead |

The installer reads the firmware version on the printer and stops on anything else unless you confirm. The
print macros are adapted to the box commands and flush routine of the firmware they are installed on.

---

## What you need

- A QIDI Q2 on stock firmware from the table above, on your Wi-Fi.
- A Windows 10 or 11 PC on the same network (OpenSSH, built in).
- The printer's SSH login (user name and password).
- About 15 minutes for the first install. The printer must be idle.

---

## Install

1. Download the WarRig package from this repository's **Releases** page and unzip it. It holds
   `START_WARRIG.cmd`, the PC tool, the Firmware Mod source package and the printer-side script.
2. Double-click `START_WARRIG.cmd`. The first time, it asks for the printer's IP address and saves it in
   `WarRig_Printer.ini` next to the tool. Put `password=...` in that file if you want the tool to log in by itself.
   **Keep that file private.**
3. Choose **1 - Install or update the Firmware Mod**. It walks through five steps:

   | Step | What happens |
   |---|---|
   | Printer found | It reaches the printer (and sets up password-free SSH for this PC, once). |
   | Firmware | It checks the stock firmware version. |
   | Printer is idle | Nothing may be printing. |
   | Building | The source is uploaded and compiled on the printer, with a progress bar. The stock screen keeps running. |
   | Switch over | It asks: switch now, try for 3 minutes first, or not now. |

4. On the printer, run the touch check if it asks, and accept the print macros update when it offers it.

<p align="center"><img src="docs/images/pctool.png" alt="The WarRig PC tool" width="80%"></p>

---

## Try, update, remove

- **Try it for 3 minutes (option 2).** The stock screen stops, WarRig runs for three minutes, then the stock
  screen comes back by itself - even if the PC disconnects.
- **Update (option 1 again).** Only what changed is compiled; the screen restarts with the new build.
- **Remove (option 3).** The stock screen, the stock print macros, the services and the start-up settings go
  back to how they were and the keeper is removed. The WarRig files stay on the printer so you can install
  again; your prints and calibration are not touched.

---

## The PC tool

The top lines show the printer's status: online or printing, the stock firmware and whether it is tested,
the WarRig build and print macros, which screen is running, and when a newer build is ready to install.

| | Option | What it does |
|---|---|---|
| 1 | Install or update the Firmware Mod | Guided, as above. |
| 2 | Try it for 3 minutes | Stock screen comes back by itself. |
| 3 | Remove the Firmware Mod | Back to the stock screen and stock macros. |
| 4 | Full test and status | Checks everything, changes nothing - see below. |
| 5 | Put back my calibration from a backup | Input shaper, PID and bed mesh from a saved `printer.cfg`. |
| 6 | Remote access and phone alerts | Tailscale on the printer, alert topic, QR code, test alert. |
| 7 | Change the printer password | And save it for the tool. |
| 8 | Make a diagnostic log | Read-only log of the printer, macros, box and print-start decisions. |
| 9 | Make a USB installer | Install / uninstall packages built from this printer's WarRig. |
| A | Advanced | Box load timing, box feed trace, faster box feed, unneeded services, clean-up, stock update files. |

Everything that changes the printer asks first. Each run is saved as a log in the `Results` folder.

---

## Full test

Option 4 tests the whole install in about 20 seconds and changes nothing. It checks this PC (package, network,
SSH login, internet), then the printer:

- **Program self check** - WarRig runs `warrig --check` with its own code: fonts load and draw, icons, all
  8 languages, the settings file, QR codes, the print-file folder, free space, and what the screen reads from
  Moonraker and Klipper (sensors, print macros revision, heater limits).
- **Services** - Klipper, Moonraker, the WarRig screen, the keeper, the freeze watchdog, any recorded crashes.
- **Print macros and box** - the macros file and its revision, the box and its commands for this firmware,
  `PRINT_START`, `G29`, the box and after-print commands, a saved bed mesh.
- **System** - disk, memory, CPU temperature, clock, network, internet, the last Klipper shutdown.
- **Link, remote, alerts** - the screen's shared info and heartbeat, the app and slicer, Tailscale, phone alerts.

```
[WarRig] PASS Screen                Firmware Mod running
[WarRig] PASS Fonts                 all 4 styles load and draw
[WarRig] PASS Nozzle sensor         24.8 C
[WarRig] WARN Print macros          revision 22 installed, 23 ready - accept the update on the screen
[WarRig] PASS Box                   1 box(es), box commands 01.01.03+
[WarRig] PASS Heater limits         nozzle 350, bed 120, chamber 40-65 C (from the printer's settings)
...
[WarRig] WRTEST SUMMARY 36 passed, 1 warnings, 0 failed
```

Warnings say what to do next. If something fails, make a diagnostic log (option 8) and keep both logs.

---

## Remote access and phone alerts

<img src="docs/images/screens/al1_companion.png" width="49%"> <img src="docs/images/screens/al2_ntfy.png" width="49%">

- **Tailscale (optional).** PC tool option 6 installs Tailscale's own build on the printer and opens the
  sign-in page in your browser. The printer then shows up on your private Tailscale network as `warrig-q2`,
  reachable from your PC and phone anywhere. It runs in user-space mode, so the printer's own network, DNS and
  firewall are not changed. Turn it off or remove it from the same screen.
- **Phone alerts (ntfy).** A random private topic is made on the screen (Settings > Wi-Fi > Remote access &
  phone alerts) or in the PC tool. Scan the **WarRig Companion** code to connect the app and its alerts in one
  go, or the **ntfy** code with the ntfy app on Android (on an iPhone, add the topic in the ntfy app by hand).
  Keep the topic private: anyone who has it can read the alerts. Today the PC tool can send a test alert; the
  printer sends print-done and print-watch alerts from a coming update.

---

## The WarRig ecosystem

<p align="center"><img src="docs/images/ecosystem.png" alt="WarRig ecosystem" width="100%"></p>

The printer is the hub. Through **WarRig Link** - records in Moonraker's own database, no extra service - the
screen shares its build, firmware, limits, the box, the last 50 events and its settings, and takes over
settings and next-print options written by the other programs:

- **WarRig Slicer** - a slicer for the Q2 and its box, with the WarRig print-start options built in.
  ([RuntimeRangerVS/WarRigSlicer](https://github.com/RuntimeRangerVS/WarRigSlicer))
- **WarRig Companion** - the Android app: watch and control the printer, camera, alerts.
  ([RuntimeRangerVS/WarRigCompanionApp](https://github.com/RuntimeRangerVS/WarRigCompanionApp))
- **PC tool** - install, update, remove, full test, logs, remote setup.

Next-print options (bed mesh, gantry, reload, after-print, colour to slot) are used once, never while a print
is running, and the screen answers each request with applied or refused and why. Support for the newest Link
records in the slicer and app is being rolled out.

---

## Print start and the print macros

WarRig's print macros are installed with it ("V1") and replace parts of the stock print start:

- **Bed mesh:** probe the print area, or load the saved mesh when you choose to skip (if there is none yet, one
  full-bed mesh is probed once and saved). A bug in how the stock-style `G29` read `SKIP=1` is fixed.
- **Probing with a cool nozzle:** the nozzle drops to 150 °C before probing and goes back up after - no dots of
  filament across the bed.
- **Gantry levelling (Z tilt)** on or off.
- **Reload:** a spool already in the head (checked with the toolhead sensor) is not unloaded and flushed again.
- **After the print:** leave the filament in the head, or the stock way back to the tube.
- **Plate temperatures:** the bed temperature follows the build plate you pick on the screen.
- At every start the printer reports what it decided (mesh, gantry, reload, after-print), and the screen warns
  if that differs from what the Start print page asked for.

The macros are adapted on install to the firmware's box commands and flush routine, and checked by Klipper -
if Klipper does not accept them, the stock macros stay.

---

## Safety

- **Locks while printing:** cleaning, cutting, parking, calibration, levelling, tuning, moves, homing,
  load / unload, box options, drying, updates and presets are locked; single temperatures, fans, speed,
  Z offset, pressure advance, flow and lights stay available.
- **Temperature limits from the printer:** nozzle up to 350 °C, bed 120 °C, chamber 65 °C (lower if the
  printer's own limits are lower); the chamber is off or 40-65 °C; box drying 45-65 °C. The same limits hold
  for settings from the app.
- **Stop asks twice;** Stop now (hold) is instant; emergency stop is always there.
- **Crash fallback:** three crashes in two minutes and the stock screen takes over until the next restart, with
  the crash saved in the logs. A frozen screen is restarted after 60 seconds.
- **Power-loss resume** for interrupted prints.
- **Nothing is deleted:** the stock screen and its files stay on the printer; changed files are backed up.

---

## Languages and looks

English, Deutsch, Français, Español, Italiano, Português, Nederlands and Polski - every page, sheet and
message. Theme colours (ember orange and others) with a colour wheel, brightness, screen sleep and beeper.

<img src="docs/images/screens/theme_panel.png" width="49%"> <img src="docs/images/screens/confirm_stop.png" width="49%">

---

## FAQ and troubleshooting

<details><summary><b>The installer says my firmware is not tested.</b></summary>

It stops on versions outside the table above. You can type `YES` to go ahead, but run the full test (option 4)
afterwards and keep the stock screen ready (option 3 removes WarRig).
</details>

<details><summary><b>How do I install a stock firmware update?</b></summary>

Remove WarRig (option 3), install the stock update the normal way, then install WarRig again (option 1). If an
update replaces `printer.cfg` while WarRig is installed, the keeper puts your calibration and the macros back
at the next start - on tested firmware only.
</details>

<details><summary><b>The screen went back to the stock screen by itself.</b></summary>

That is the crash fallback. Run the full test (option 4) and make a diagnostic log (option 8). The crash is
saved as `warrig_crash.txt` in the printer's logs folder.
</details>

<details><summary><b>The box lost contact while loading.</b></summary>

After an emergency stop the box may not answer until the printer is switched off at the power switch, left
for 10 seconds and switched on again. WarRig shows this advice when it happens.
</details>

<details><summary><b>A print started with a full bed mesh although I skipped it.</b></summary>

With no saved mesh, one full-bed mesh is probed once and saved; later prints load it. The screen shows what
the printer decided at every start.
</details>

<details><summary><b>Does WarRig need the internet or an account?</b></summary>

No. Everything at home goes through the printer. Tailscale (remote access) and ntfy (phone alerts) are
optional and only used if you set them up.
</details>

---

## Credits

WarRig uses, and thanks:

- [LVGL](https://lvgl.io) - the graphics library of the screen (MIT), including its QR code generator.
- [Inter](https://rsms.me/inter/) - the typeface (SIL Open Font License), shipped in `fonts/`.
- [Klipper](https://www.klipper3d.org) and [Moonraker](https://github.com/Arksine/moonraker) - already on the
  printer; WarRig talks to them and adds print macros, it does not change or ship them.
- [Tailscale](https://tailscale.com) - optional remote access, downloaded from Tailscale when you set it up.
- [ntfy](https://ntfy.sh) - optional phone alerts.

---

## Disclaimer

WarRig is an independent, unofficial Firmware Mod. QIDI, Q2 and QIDI Studio are names of their owners and are
used here only to say which printer WarRig is for. Installing it changes how your printer starts and prints;
you use it at your own risk. Keep the stock files (WarRig does not delete them), run the full test after
installing, and remove WarRig before asking QIDI for support.

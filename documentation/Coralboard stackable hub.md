---
tags:
---

# Coralboard™ stackable hub: case and mount

Why reinvent the wheel when you can turn it into a box?

The idea borrows from semi-truck dual wheels: two tires mounted side by side on each end of an axle. Here, that arrangement becomes a compact case that can take a mount plate on one end and stack on another.

The single-hub assembly is 123 mm in diameter and 40 mm tall, including both mount plates. It is fully tool-less for normal assembly and supports several common mounting and cooling options. All parts fit on a 260 × 260 mm print bed, and none need support material.

## What is in the print

### Bottom shell

The bottom shell houses the PCB, with standoffs and foot pads, and includes the A (I) and B (II) buttons. It forms the lower half of the battery tray and can hold a 30 mm axial fan when hubs are stacked.

- **Passthroughs:** USB-C, USB-A, CSI (routed down), DSI, SD card, and I2S2.
- **Clearance:** probe points (limited) and I2S3 and reverse JTAG (limited).

### Top shell

The top shell encloses the PCB and holds it with standoff caps. Without a top mount plate, it provides hole patterns for externally mounting a 60 mm or 80 mm axial fan. It forms the upper half of the battery tray.

- **Passthroughs:** 20-pin GPIO header, mikroBUS™ connector, I3C, CSI, and DSI (routed up).
- **Clearance:** M.2, JTAG interface, and battery port.
- **Shelf:** several slots let you attach custom items:
  - Two 4 × 14 mm slots, spaced 120° apart. They are partly covered by the mount plate.
  - One 4 × 10.1 mm slot, 30° from the other two and parallel to the horizontal. It remains exposed with the mount plate installed.
  - One 5 mm hole, centered vertically and offset from the horizontal. It also remains exposed with the mount plate installed.

The shells snap together. Alignment diamonds make blind assembly easier: the large diamonds on the side petals go at the sides; the small diamonds on the rear fangs help align the top and bottom shells. The rear fangs also retain the battery in its tray.

The battery tray has been tested with a small battery case. Battery shapes vary, and the PCB supports only certain battery types, so check your specific battery before relying on the tray.

The shell passthroughs do not account for a mount plate. The plate has a 42 mm center opening for cables, provided a 30 mm fan is not installed there.

### Mount plate

The same mount plate snaps onto either shell. Its cardinal symmetry makes it easier to orient against a surface. It has two phases, rotated 45° from each other:

- **Phase A:** VESA 75 mounting holes.
- **Phase B:** passthrough holes for zip ties or Velcro, or holes for stack pins. Stack pins can serve as feet or join hubs.

Align the plate clips with the large diamonds on the sides of the top shell. The clip design allows a couple of degrees of rotational play, so you can make small angle adjustments while ensuring the plate is seated.

The plate provides several mounting patterns:

- Paired M3 countersunk holes at each cardinal direction, with 9 mm and 21 mm spacing. Together these make eight holes on an 86.94 mm bolt circle.
- Axial holes on a 62.5 mm bolt circle. In either phase, they can form a square with 44.19 mm between holes.
  - In one phase, there are eight M4 countersunk holes, useful for DIN clips.
  - In the other phase, there are eight M5 countersunk holes, rotated 22.5° from vertical.

## Stacking and cooling

Stack pins fit between the mount plates of two hubs; the plates must be in phase for the pins to attach to both. You can also use them as raised feet to lift a hub off a surface.

The geometry allows a compression stack of up to 256 hubs. At 40 mm per hub, that would be 1,024 cm tall. Treat that as a geometric limit, not a tested tower height.

For a tension stack, use screws once you go beyond four hubs. Cables can apply torque to the clips and pry them open. The mount holes are available for fastening two plates together; use bolts no longer than 8 mm total length. There are also passthrough holes for longer bolts, spaced 71.5 mm apart on each cardinal direction. Bolts at the front, where the buttons and USB ports are, slightly restrict access to USB-A. A useful combination is passthrough bolts on the sides and stack pins at the front and back.

A 30 mm Raspberry Pi fan fits between two plates and screws in from the bottom-shell side. Other 30 mm axial fans may fit too: look for 24 mm hole spacing on a 33.94 mm circle, with 3.4 mm holes. Fan height is limited to about 8 mm, so check the dimensions before printing the stack.

Stacked vertically, the hubs look like neat little architectural towers. You could build a couple. You could even build a little city (expensive).

## Rolling

It is a wheel hub, after all, and it rolls surprisingly well. It also works as a cat toy (tested).

You could print a custom-size TPU tire and fit it around the case. If you do, please share a photo. Cable routing will take some thought, but USB cables can work. A tire will block the buttons, though. There may be potential as an RC wheel around 1:10 scale.

The tire would be airless and definitely leak, so I would not take it off-roading. Rolling with USB cables plugged in has not been tested; expect the cables to add rolling resistance. The recessed USB ports do protect the plugs from unwanted bending, and their 19 mm clearance leaves room to plug and unplug cables, even with my fat fingers. A rolling design could also make for neat USB cable management.

You can stack the hubs or keep them separate, then mount them on a mini tire rack.

## Printing

PETG is the material I designed and tested with. PLA, ABS, and ASA should also work, though the fit and feel may differ from what the design expects.

- **PLA:** Mount-hook breakage is unlikely, but possible. The buttons may feel stiffer and could snap, especially the A (I) button. The modeled PCB screw-hole size differs from the real board. I accounted for that as much as I could, including backstops that limit PCB travel and direct button force toward the back of the PCB.
- **ABS/ASA:** Mount plates and stack pins may have more friction. That is expected, and the material should handle it. The mount's clamping force may be slightly lower than with PETG. The buttons should work about the same as they do in PETG.
- **PC and similar blends:** Expect behavior broadly similar to ABS/ASA, with clamping force that may be higher than PETG.
- **Nylon and variants:** These may work very well, but watch for low clamping force and slippery stack pins. Stack pins rely mainly on friction, helped by their spring-wedge geometry. Once the mount plates are clamped together, the pins may hold well.
- **TPU and other flexible materials:** I would not use them for the hub, except for experimentation. TPU is a good candidate for a separate tire, though.

### Tested slicer settings

These settings were tested with the default profile on a Creality Hi and a 0.4 mm nozzle:

- **Filament:** CR PETG; 1.75 mm, 1.23 g/cm³; nozzle 250 °C, bed 80 °C.
- **Layer height:** 0.2 mm.
- **Wall loops:** 2; 3 may also work.
- **Top and bottom surfaces:** Concentric top pattern (3 shell layers); Archimedean chords bottom pattern (3 shell layers). These are my preferences; other settings may work even better for you.
- **Infill:** 15% sparse Gyroid. I like when the printer goes brrrrrt.
- **Seam position:** Nearest, to speed up travel and avoid lining up seams too much around holes.
- **Wipe on loops** and **Wipe before external loop:** On, to help with stringing and first-layer adhesion.
- **Z-contouring / Z-layer anti-aliasing:** On, for a smoother finish here and there.
- **Wall generation:** Arachne. This is personal preference; Classic should work about the same.

If the first layer does not stick, check your printer manufacturer's troubleshooting guide. Clean the bed, check your filament and bed temperatures, and make sure the filament is dry. Z-hop and retraction settings may also help, depending on your printer and filament.

## Files

- [CBHv3.3mf](../model/CBHv3.3mf) — default parameters; import as geometry only.
- [CBHv3 (Project).3mf](../model/CBHv3%20(Project).3mf) — preconfigured project; import as a project.
- [CBHv3 chart.pdf](CBHv3%20chart.pdf) — drawings of the components and their details.

Everything in one place: [Coralboard™ on GitHub](https://github.com/wolframIII/CBH)
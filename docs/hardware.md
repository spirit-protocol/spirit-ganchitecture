# Hardware

## What's on hand

| Item | Quantity | Source | Status |
|---|---|---|---|
| **VTV LED ticker panels** | 6 | VTV inventory (Paris Photo SOLIENNE precedent) | On-hand |
| Aluminum back structures for panels | 6 | VTV | On-hand |
| Frosted acrylic layer (per panel) | 6 | VTV | On-hand |
| Translucent white acrylic layer (per panel) | 6 | VTV | On-hand |
| Raspberry Pi 4 | (multiple) | Pablo's studio | On-hand |
| Raspberry Pi 5 | (multiple) | Pablo's studio | On-hand |
| Arduino | (multiple) | Pablo's studio | On-hand |
| ESP32 | (multiple) | Pablo's studio | On-hand |
| DMX controller | (some) | Pablo's studio | On-hand |
| Small screens (5", 7", 6.9") | Several | Pablo's studio | On-hand |
| TouchDesigner license (paid) | 1 | Vladimir (VTV) | Available |
| LED strip (1m sticks ×18 for 18 nodes) | TBD | TBD source — depends on what Pablo / VTV bring | **Open** |
| NFC reader | TBD | TBD — Pablo to source for the screen module | **Open** |

## The panels

Chinese-manufactured LED ticker panels. Each plays a fixed 0–9 video on hardware-locked timing. There is no programmable interface to the digit display — the panel just plays its video.

Each panel is assembled with:
- Aluminum back structure (rigid mount)
- Inner acrylic layer: frosted, diffuses the LED brightness
- Outer acrylic layer: translucent white, softens the digit edge so the message reads gently rather than as harsh LED matrix

Six panels stack into the central monolith. Configuration confirmed visually in Fran's renders (to be mirrored into [`../assets/renders/`](../assets/renders/)).

## The controller decision

We need to drive:
- **18 LED nodes** (one per visitor)
- **Master ambient sound + base light pulse**
- **Optional:** poll the Spirit hash service for active-session count

Three candidates:

| Option | Pros | Cons |
|---|---|---|
| **ESP32** | Tiny footprint, cheap, plenty of GPIO for the strip, native Wi-Fi for talking to the hash service, low power | Slightly less flexible for heavy audio synthesis; needs care for power if many LEDs |
| **Raspberry Pi 4 / 5** | Full Linux, easy debugging, plenty of headroom for audio + animation, mature toolchain | Larger, more power, overkill if all we do is on/off lights |
| **Arduino** | Simple, predictable | Limited Wi-Fi without shield; less headroom than ESP32 |

**Samer leans ESP32.** Reasoning: the controller's job is small and on/off-ish; ESP32 is the cleanest physical install in a basement that wants minimal visible kit. We can validate the ESP path against the actual 18-node strip when Samer is back in London week of May 19.

The Pi is a fine fallback if ESP power handling on the strip is fragile.

## Lighting binding

**DMX vs MIDI** — open question for Fran + Vlad. The strip is the room-level effect surface; the binding choice depends on what board / controller they prefer to wire through.

For the per-stick 18-node addressable design, the binding likely lives directly on the ESP/Pi rather than going through DMX — DMX adds a hop without obvious benefit when the controller is co-located with the strip. To confirm with Fran.

## The NFC + numbers screen

A small screen (5", 7", or 6.9" — pick one) mounted at visitor eye-line on the monolith. Behind it: an NFC reader.

Visitor sees numbers on the screen. The visible numbers are theatre — the screen plays a designed sequence to invite the tap. Behind it, the NFC reader does the actual pairing.

When the visitor's device taps:
- Phone: NFC chip on the phone hits the reader, opens the URL natively
- Laptop: laptops typically don't have NFC; for laptops we may surface a fallback QR or short-text URL nearby. To confirm with Pablo on UX.

## TouchDesigner

Vlad has a paid license. Free tier is fine if we are not outputting video. Given the architecture (no centralized video manipulation — the obelisk plays its locked loop, visitor devices are self-driven), TouchDesigner may not be needed in production. Useful as a build-time prototyping surface for the master ambient sound + light pulse.

## Power and venue

Per Pablo, the venue is a wet basement. Power capacity, network presence, and load-in path are **all pending confirmation** — open thread to Pablo in [`../STATE.md`](../STATE.md).

Treat power as a constraint until confirmed. ESP32 + LED strip + small screen draws are modest; the obelisk panels draw the most. If venue power is tight, sequence panel power-up and stagger draws.

## What we are not building

- We are not building a custom display driver for the obelisk panels. They play their loop. That's the piece.
- We are not running per-device audio through a central mixer. Devices play locally.
- We are not depending on internet connectivity inside the room. The local router and Samer's hosted hash service are the network.

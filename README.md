# Cube 2: Sauerbraten source port

**A client mod for Cube 2: Sauerbraten. Aims for a vanilla-like experience, but more polished.**

This mod can also be used as a server mod, although there are currently no
changes to speak of when running as a server.

*Currently based on Sauerbraten SVN revision 6217. Work is in progress to rebase
on the 2020 edition and include the latest official fixes and improvements.*

## Features

- Improved coloring for player numbers in the server browser (gray = empty,
  yellow = almost full, red = full).
- Colored pings in the server browser and scoreboard (greener = better).
- Improved coloring and capitalization for console messages.
- Strafe movement animation is now used when moving diagonally forwards.
- Tweaked default color for bot waypoints to make them more visible.
- Quad damage attack sound now plays continuously when firing the chaingun.
- Customizable color for bot waypoints (e.g. `/showwaypointscolour 0xffffff`).
- Customizable weapon trail colours (`/rockettrailcolour`, `/rifletrailcolour`, `/grenadetrailcolour`).
- `positionpacketdelay` and `disableenetlimits` variables ported from
  [sauer-sdl2](https://github.com/extra-a/sauer-sdl2).
  Both are set to values optimized for responsive, jitter-free gameplay by default.
- **Improved particle effects:**
  - Players landing from a high jump now create a smoke puff.
  - Entering and leaving water/lava now creates splash particles.
- **Improved dynamic light effects:**
  - Teleports and teledests now emit a blue dynamic light when used.
  - Jumppads now emit a green dynamic light when used.
  - Hitscan shots now emit a dynamic light at the point of impact.
- **HUD improvements:**
  - `/hudicons 0` variable to hide icons on the HUD (defaults to `1`).
  - Armor count is now colored depending on the current armor type.
  - Health and ammo are now hidden in instagib modes.
  - Health is now hidden while dead.
  - FPS counter is now colored depending on the framerate.
  - The respawn counter on the minimap now turns green when it reaches 0.
  - Game clock now becomes red (instead of yellow) when there is less than 1
    minute left, and yellow when there are less than 3 minutes left.
- **Tweaked variable defaults:**
  - `depthbits`  (`0` -< `24`) - Fixes Z-fighting in large maps on Intel IGPs.
  - `minimapsize` (`8` -> `10`) - Sharper minimap.
  - `showwaypointsradius` (`200` -> `500`) - See waypoints from further away.
  - `soundbufferlen` (`1024` -> `768`) - Lower sound latency.
  - `soundfreq` (`22050` -> `48000`) - Improved sound quality.
- **Tweaked variable limits:**
  - `avatarfov` (`10..150` -> `1..179`) - For triple-monitor/surround setups.
  - `avatarzoomfov` (`10..60` -> `1..179`) - Allows more subtle zoom.
  - `fov` (`10..150` -> `1..179`) - For triple-monitor/surround setups.
  - `minimapsize` (`7..10` -> `7..11`) - Even sharper minimap.
  - `shadowmapsize` (`7..11` -> `7..12`) - Sharper/better-looking shadowmaps.
  - `zoomfov` (`10..60` -> `1..179`) - Allows more subtle zoom.

## Installation

**No binaries are provided yet.** Therefore, you must build this project from
sources to run it.

- Clone this repository or
  [download a ZIP archive](https://github.com/Calinou/sauerbraten-source-port/archive/master.zip).
- Copy or symlink the `packages/` folder from your
  [Cube 2: Sauerbraten](http://sauerbraten.org) installation.
  (This must done because `packages/` can't legally be redistributed
  in modified versions of the game.)
- Compile a client and server binary. On Linux, enter `make -C src install` in a terminal while in
  the root folder of the cloned repository.
- Run the game by entering `./auerbraten_unix` in the root folder.

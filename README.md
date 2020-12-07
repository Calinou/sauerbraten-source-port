# Sauerbraten source port

## Features

- Improved coloring for player numbers in the server browser (gray = empty, yellow = almost full, red = full).
- Colored pings in the server browser and scoreboard (greener = better).
- Strafe movement animation is now used when moving diagonally forwards.
- Tweaked default color for bot waypoints to make them more visible.
- Customizable color for bot waypoints (e.g. `/showwaypointscolour 0xffffff`).
- Customizable weapon trail colours (`/rockettrailcolour`, `/rifletrailcolour`, `/grenadetrailcolour`).
- `positionpacketdelay` and `disableenetlimits` variables ported from
  [sauer-sdl2](https://github.com/extra-a/sauer-sdl2).
  Both are set to values optimized for responsive, jitter-free gameplay by default.
- **Tweaked variable defaults:**
  - `minimapsize` (`8` -> `10`)
- **Tweaked variable limits:**
  - `avatarfov` (`10..150` -> `1..179`)
  - `avatarzoomfov` (`10..60` -> `1..179`)
  - `fov` (`10..150` -> `1..179`)
  - `minimapsize` (`7..10` -> `7..11`)
  - `shadowmapsize` (`7..11` -> `7..12`)
  - `zoomfov` (`10..60` -> `1..179`)
- **HUD improvements:**
  - `/hudicons 0` variable to hide icons on the HUD (defaults to `1`).
  - Armor count is now colored depending on the current armor type.
  - Health and ammo are now hidden in instagib modes.
  - Health is now hidden while dead.
  - FPS counter is now colored depending on the framerate.
  - The respawn counter on the minimap now turns green when it reaches 0.
  - Game clock now becomes red (instead of yellow) when there is less than 1 minute left, and yellow when there are less than 3 minutes left.

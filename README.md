# Sauerbraten source port

## Features

- Colored pings in server browser and scoreboard (greener = better).
- Strafe movement animation is now used when moving diagonally forwards.
- Tweaked default color for bot waypoints to make them more visible.
- Customizable color for bot waypoints (e.g. `/showwaypointscolour 0xffffff`).
- Customizable weapon trail colours (`/rockettrailcolour`, `/rifletrailcolour`, `/grenadetrailcolour`).
- `positionpacketdelay` and `disableenetlimits` variables ported from
  [sauer-sdl2](https://github.com/extra-a/sauer-sdl2).
  Both are set to values optimized for responsive, jitter-free gameplay by default.
- Tweaked variable limits:
  - `avatarfov` (`10..150` -> `1..179`)
  - `avatarzoomfov` (`10..60` -> `1..179`)
  - `fov` (`10..150` -> `1..179`)
  - `shadowmapsize` (`7..11` -> `7..12`)
  - `zoomfov` (`10..60` -> `1..179`)

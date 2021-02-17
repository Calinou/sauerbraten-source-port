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
- New `^f9` console color code (light gray).
- Strafe movement animation is now used when moving diagonally forwards.
- Tweaked default color for bot waypoints to make them more visible.
- Quad damage attack sound now plays continuously when firing the chaingun.
- Customizable color for bot waypoints (e.g. `/showwaypointscolour 0xffffff`).
- Customizable weapon trail colours (`/rockettrailcolour`, `/rifletrailcolour`, `/grenadetrailcolour`).
- `positionpacketdelay` and `disableenetlimits` variables ported from
  [sauer-sdl2](https://github.com/extra-a/sauer-sdl2).
  Both are set to values optimized for responsive, jitter-free gameplay by default.
- Blob shadows are now displayed when shadow maps are enabled to fake ambient occlusion.
- Tweaked blob shadows to be more subtle and fade more progressively when jumping.
- **Improved hudgun swaying:**
  - Slightly decreased overall swaying speed.
  - Increased swaying speed when moving forward/backward to compensate.
  - Subtle swaying is now applied when not moving to make the player feel more alive.
  - The `/swayside`, `/swaystep` and `/swayup` variables are now persistent.
- **Improved particle effects:**
  - Players landing from a high jump now create a smoke puff (`/landingvfx 0` to disable).
  - Entering and leaving water/lava now creates splash particles (`/liquidvfx 0` to disable).
  - Teleports and teledests nwo emit blue sparks when used (`/teleportvfx 0` to disable).
  - Jumppads now emit green sparks when used (`/jumppadvfx 0` to disable).
- **Improved dynamic light effects:**
  - Teleports and teledests now emit a blue dynamic light when used (`/teleportvfx 0` to disable).
  - Jumppads now emit a green dynamic light when used (`/jumppadvfx 0` to disable).
  - Hitscan shots now emit a dynamic light at the point of impact (`/hitscanlight 0` to disable).
- **HUD improvements:**
  - `/hudicons 0` variable to hide icons on the HUD (defaults to `1`).
  - `/radardeadplayers 0` to hide dead player icons ("×") on the minimap.
  - `/crosshairforceadditive 1` variable to force additive blending for
    crosshairs that contain an alpha channel (defaults to `0`). If `0`, "mix"
    blending is used as in the vanilla game.
  - Crosshair health is now a smooth gradient (red-yellow-white). The crosshair
    will also progressively become greener if your health goes above 100.
  - Teammate crosshair is now displayed on top of the main crosshair so that you
    can still know your health status.
  - Tweaked the teammate crosshair color to be more visible.
  - Armor count is now colored depending on the current armor type.
  - Health and ammo are now hidden in instagib modes.
  - Health is now hidden while dead.
  - FPS counter is now colored depending on the framerate.
  - The respawn counter on the minimap now turns green when it reaches 0.
  - Blips on the minimap (flags, capture bases, in-game hold flag)
    now blink faster for easier recognition and following.
  - Game clock now becomes red (instead of yellow) when there is less than 1
    minute left, and yellow when there are less than 3 minutes left.
  - Own chat messages (standard and team) are now displayed in light gray to
    be easier to distinguish from other players' messages.
  - Chat messages containing your name (case-insensitive) are now displayed in
    orange ("highlight" messages).
    - If your name contains clan tags or is frequently shortened by other players,
      define `/chathighlightname` to use an additional highlight word
      (in addition to your player name). This word is also case-insensitive.
- **Tweaked variable defaults:**
  - `aniso` (`0` -> `16`) - 16× anisotropic filtering to make textures look
    better when viewed at oblique angles.
  - `conscale` (`0.33` -> `0.42`) - Larger console text.
  - `consize` (`5` -> `7`) - More console messages on screen.
  - `depthbits` (`0` -> `24`) - Fixes Z-fighting in large maps on Intel IGPs.
  - `fov` (`100` -> `107`) - Matches 16:9 displays (equivalent to `/fov 90` on 4:3).
  - `fsaa` (`-1` -> `4`) - 4× MSAA to combat aliasing on polygon edges.
  - `fullconsize` (`75` -> `85`) - Taller full console (`saycommand` line is still visible just below).
  - `guiclicktab` (`0` -> `1`) - Click to switch GUI tabs (instead of merely hovering them).
  - `miniconsize` (`5` -> `8`) - More chat messages on screen.
  - `minimapsize` (`8` -> `10`) - Sharper minimap.
  - `showwaypointsradius` (`200` -> `500`) - See waypoints from further away.
  - `soundbufferlen` (`1024` -> `768`) - Lower sound latency.
  - `soundfreq` (`22050` -> `48000`) - Improved sound quality.
- **Tweaked variable limits:**
  - `avatarfov` (`10..150` -> `1..179`) - For triple-monitor/surround setups.
  - `avatarzoomfov` (`10..60` -> `1..179`) - Allows more subtle zoom.
  - `conscale` (`0.001..1000.0` -> `0.3..2.0`) - Prevents the console from
    becoming unusable due to extremely low or high values.
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

## License

Copyright © 2001-2020 Wouter van Oortmerssen, Lee Salzman, Mike Dysart, Robert Pointon, and Quinton Reeves

Mod changes © 2020 Hugo Locurcio (see Git history)

Licensed under the Zlib license, see [LICENSE.txt](LICENSE.txt) for details.

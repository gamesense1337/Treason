# Treason Maxframes Config

An aggressive FPS-focused `autoexec.cfg` for **Treason**.

This config is intended for players who care more about framerate and frame-time consistency than visual quality. It reduces or disables shadows, ragdolls, physics props, gibs, decals, ropes, water effects, model effects, and several material features while preserving the useful network settings from the original config.

## Installation

1. Download `autoexec.cfg`.
2. Place it in your Treason config folder:

   ```text
   C:\Program Files (x86)\Steam\steamapps\common\Treason\treason\cfg
   ```

   If your Steam library is installed somewhere else, use the equivalent `steamapps\common\Treason\treason\cfg` folder in that library.

3. In Steam, open **Treason -> Properties -> General -> Launch Options**.
4. Recommended launch options:

   ```text
   -novid -nojoy -nosteamcontroller -particles 1
   ```

5. Launch the game. The console will print:

   ```text
   ReD's Maxframes config loaded.
   ```

## Launch options

The config keeps the original lightweight launch options:

```text
-novid -nojoy -nosteamcontroller -particles 1
```

`-novid` skips the startup video, while `-nojoy` and `-nosteamcontroller` avoid initializing controller-related support when it is not needed.

Source uses `-particles` to control the maximum number of beam trails. The engine has a minimum value, so `-particles 1` effectively requests the lowest supported limit rather than literally allowing one trail. If you notice missing or undesirable tracer/beam effects, remove `-particles 1` first.

## FPS cap

The config uses:

```text
fps_max 0
```

This leaves the framerate uncapped for maximum throughput and minimum engine-side frame limiting. If you would rather reduce GPU usage, heat, or fan noise, replace `0` with your preferred cap.

## Troubleshooting

### The config does not load

Make sure the filename is exactly:

```text
autoexec.cfg
```

and that Windows did not save it as `autoexec.cfg.txt`.

You can also open the developer console and run:

```text
exec autoexec
```

If the config loads successfully, the banner should be printed in the console.

### A command is reported as unknown

Treason is a customized Source-engine game and does not necessarily expose every cvar found in other Source branches. If the console reports an unknown command, include the exact command/error when reporting it so the config can be corrected without guessing.

### Something looks broken

First remove `-particles 1` from the launch options if tracer or beam effects are missing. For model or texture problems, temporarily comment out `r_lod 2` or `mat_picmip 0` and restart the game.

### I want better graphics back

Remove or rename `autoexec.cfg`, restart Treason, and restore your preferred video settings from the in-game options menu. Some material/video settings may require a restart or map reload before the change is fully visible.

## Credits

- Valve / Source community documentation — useful for validating old Source-engine cvars and removing outdated tweaks.

## License

MIT. See [LICENSE](LICENSE).

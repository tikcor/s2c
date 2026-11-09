# s2c: Source 2 Cinematics

A moviemaking toolkit for **Counter-Strike 2** and **Deadlock** demos: camera paths, recording, HUD control, ragdolls and visual effects, all from an in-game menu.

> **s2c is in early alpha.** Things will change and some things will break. Please report anything odd (see [Feedback](#feedback)).

Built on [HLAE](https://github.com/advancedfx/advancedfx) (advancedfx, MIT licence), with help from [Source: Moviemaker](https://github.com/Wockstajit/SourceMVM) (Wockstajit, MIT licence).

---

## Download

Get the latest version from **[Releases](https://github.com/tikcor/s2c/releases)**:

- **`s2c-x.x.x-setup.exe`**: the installer (recommended). No admin needed, and it adds a Start menu shortcut.
- **`s2c-x.x.x-portable.zip`**: unzip anywhere and run `S2C.exe`.

s2c checks for updates itself. When a new version is out, the launcher's Home page shows **Install update**. Your settings, presets and camera paths are kept.

**Windows may warn you on first run** ("Windows protected your PC"), because s2c isn't code-signed yet: click *More info → Run anyway*. Some antivirus programs flag the injector, as they do with HLAE; it's what loads s2c into the game.

**Recording to video needs ffmpeg:** in the launcher go to *Settings → ffmpeg → Download ffmpeg*. Image sequences work without it.

## Is it safe? (VAC)

s2c always launches the game with `-insecure`, so you can't join VAC-secured servers while using it and can't get VAC banned. Only use it for demos and moviemaking.

## Setup (CS2)

Not required, but strongly recommended.

1. **Make a moviemaking folder** for everything CS2 moviemaking, e.g. `E:\mvm\cs2 mvm`. On the launcher's CS2 page, turn on **Moviemaking config parent folder** and pick it. s2c creates a `cfg` folder inside it, so your moviemaking binds never touch your normal gaming config. Sub-folders for demos, recordings and screenshots are handy too; you can point s2c's menu at them.
2. **Add the cfg:** copy `mvm.cfg` from your s2c folder (or download [it here](cfg/mvm.cfg)) into that `cfg` folder. It unbinds the keys s2c uses (so the scroll wheel, number keys and so on don't do two things at once) and turns off a few distracting game displays.
3. **Launch options** (CS2 page): I use `-console +sv_lan 1 -novid +exec mvm.cfg`.
4. **Launch CS2 from s2c** and press **F10** to open the menu.

If you don't add `+exec mvm.cfg` to the launch options, type `exec mvm.cfg` in the console after the game starts.

**Clean launch:** turn on *Clean launch* on the CS2 page before launching to start with default settings for that launch. It switches itself off after.

## The windows

| Key | Window |
|---|---|
| **F9** | Demo controls: play, pause, speed and skipping |
| **F10** | Main menu: all the settings. Groups down the left, tabs along the top |
| **F11** | Timeline: the demo along the bottom, with your keyframes, markers and In / Out |
| **F12** | Camera preview: watch your camera path play while you work |

F12 is Steam's screenshot key by default: change Steam's or rebind s2c's.

**Stuck?** Each window has a help toggle in its corner that turns on tooltips for everything in it.

## Workflow

1. **Load a demo:** *Demo → Demos*.
2. **Find the moment:** Space pauses. Set **In (I)** and **Out (O)** around your clip and turn the **loop on (L)**: the demo replays just that part, so you can work on one moment without scrubbing back. Shift+I / Shift+O jump to either end. You can also cache the region for smoother playback inside it.
3. **Free camera:** **N**. Hold right mouse to look, WASD to move, R / F up and down.
4. **Camera path:** **C** adds a keyframe; move, **C** again. **P** shows the path, **F12** previews it. The number keys jump to that keyframe.
5. **Look:** the Scene, Environment and FX tabs. Start from a preset if you like.
6. **Record:** set it up in *Capture → Recording*, then **F6** to start / stop, or hit record on the timeline to render just your In to Out. Some things, like audio stems, need an extra pass, which s2c does for you.

**Ctrl+Z** undo, **Ctrl+Y** redo.

## Default keys

| Key | Does |
|---|---|
| F9 / F10 / F11 / F12 | Demo controls / menu / timeline / camera preview |
| G | Effects in the camera preview |
| F8 | "See through" windows |
| Space | Pause |
| F1 / F2 | Skip back far / near |
| F3 / F4 | Skip forward near / far |
| M | Marker |
| N | Free camera |
| Ctrl + wheel | Zoom |
| Shift + wheel | Fly speed |
| \ | Level the camera |
| Z / X | Roll the camera |
| C | Add a keyframe |
| P | Show the path |
| 1 to 0 | Select a keyframe |
| Backspace / Delete | Delete the selected keyframe (or object) |
| I / O | Loop start / end |
| L | Loop on / off |
| H | Clear the loop region |
| V | Attach camera keyframe |
| F5 | Clear a timeline layer (the selected keyframe's) |
| F6 | Record |

Every key can be changed, and there's much more you can bind: rounds, kills, speed, screenshots, keyframe easing, any console command. Go to *Setup → Hotkeys*, click a key and press a new one.

## Feedback

s2c needs a fair bit of work, but it's in a very usable state. Please tell me about:

- anything broken (screenshots help a lot);
- hotkeys that clash or don't work;
- hotkeys you think should be added, or should be on by default.

Open an [issue](https://github.com/tikcor/s2c/issues) or message me.

## Credits

- [HLAE / advancedfx](https://github.com/advancedfx/advancedfx): s2c is built on it (MIT licence).
- [Source: Moviemaker (SOURCE:MVM)](https://github.com/Wockstajit/SourceMVM) by Wockstajit: parts of s2c are based on it (MIT licence).
- Every licence for the code and data s2c includes ships with it, in its `LICENSES` folder.

# Overcam

Webcams from a Discord call, shown over your game.

Open a friend's video in Discord with **Pop Out**, and Overcam shows it as a small box on top
of your game. No injection into the game or Discord: it uses public Windows APIs only.

## Why

When you play with friends on a Discord call, you hear them, but their video sits in the
Discord window. In full screen that window is behind the game, and on a second monitor you
have to look away from the game to see it.

Overcam puts each friend's webcam in a small box over the game. You pick the place and the
size, and the box can be round or oval. The boxes stay on top, and with click-through on,
the mouse goes into the game.

## How it works

1. In Discord you pop out a video, and Discord opens it in a separate window.
2. Overcam finds that window, moves it out of your way and makes it almost fully transparent,
   so you do not see the video twice.
3. Overcam copies the picture with Windows Graphics Capture, the public API that OBS and the
   Windows Snipping Tool also use, and draws it in its own box over the game.
4. When you quit Overcam, the Discord windows go back to normal.

Overcam does not inject code into the game or into Discord, and it does not change Discord's
files, so anti-cheat finds nothing of it in the game process. Video stays on your PC. The only
network request is the update check on this GitHub page.

If you stream, your viewers do not see your friends. "Hide from recording and streams" is on
by default and leaves the boxes out of OBS, Discord Go Live and screenshots, while you still
see them on your monitor.

## Goals

- One exe of about 0.6 MB, with no installer, no background services and no admin rights.
- Only public Windows APIs, and nothing that touches the game, so your game account is safe.
- No taskbar button, boxes that never take focus from the game, and a hotkey for every action.
- Low load on the PC: video is drawn on its own thread and capped at 720p per box.

## Download

Get `Overcam.exe` from the [latest release](https://github.com/blueche91/overcam-releases/releases/latest)
and run it. It is a single file; settings are kept in `%APPDATA%\Overcam`.

Windows may show "Windows protected your PC" for a new app: click **More info**, then **Run anyway**.

## Use

1. In a Discord call, click **Pop Out** on a video.
2. Overcam picks the window up and shows it over your game.
3. Drag the box. Mouse wheel zooms, Ctrl+drag moves the picture.
4. **Ctrl+Alt+L**: clicks go through the box into the game.

Settings: **Ctrl+Alt+O** or a click on the tray icon. Up to 12 webcams, round or oval boxes,
follow face. Overcam updates itself from this page; updates are signed.

Windows 10 (1903+) or 11. "Hide from recording and streams" needs Windows 10 2004 or newer.
Games in exclusive full screen hide every window on top of them, so set the game to
borderless or windowed full screen.

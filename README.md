# GameBox - Offline Games App

12 classic mini-games in one tiny, fully offline Android app. No internet permission, no ads, no accounts - install and play anywhere.

**Download APK (v0.2.0):** https://drive.google.com/file/d/1mW8YIh0k7z3lJ0DTCwpsekXkhX6rlTAt/view (APK is ~0.06 MB. Google Drive shows a standard "Download anyway" prompt for APK files.)

**Source code:** [gamebox-v0.2.0-source.zip](gamebox-v0.2.0-source.zip)

## What's new in v0.2.0 (24 Oct 2026)

- **Proper navigation**: every game has a header with Home, Pause, Sound and How-to-Play. Pause menu offers Resume / Restart / Home. Games auto-pause when you leave the app.
- **Smooth performance**: all action games run on a delta-time game loop (smooth at any refresh rate) with devicePixelRatio-crisp canvas rendering. Screen stays awake while playing.
- **Better games**: Snake Rush speeds up as you eat, 2048 gets sliding tile animations and Undo, Tic Tac Toe has Easy/Normal/Hard AI (minimax) or 2 Players, Mine Sweeper first tap is always safe, Brick Breaker has levels, Sudoku has 3 difficulties with a unique-solution generator.
- Sound effects (tiny synthesized WebAudio, mutable) and haptics on supported devices.
- Layout verified at 320-390 CSS px in dark and light themes: no overlaps, no truncated titles.

## Games

2048, Snake Rush, Tic Tac Toe (vs computer), Memory Match, Mine Sweeper, Brick Breaker, Flappy Dot, Sudoku, Tower Stack, Mole Smash, Beat Echo, Paddle Clash.

All game code and cover art are original, written for this project.

## Features

- 100% offline: the app has no INTERNET permission at all
- Dark and light themes
- Favorite games list
- Best-score tracking per game (stored on-device)
- Share the app via the native Android share sheet
- English UI

## Screenshots

| Home (dark) | Home (light) | 2048 | Brick Breaker | Sudoku |
|---|---|---|---|---|
| ![home dark](2-gamebox-home-dark.png) | ![home light](3-gamebox-home-light.png) | ![2048](4-gamebox-2048.png) | ![breakout](5-gamebox-breakout.png) | ![sudoku](6-gamebox-sudoku.png) |

## Tech

Native Android (minSdk 24 / Android 7.0+) shell hosting a hardware-accelerated WebView. Games are vanilla HTML/CSS/JS in `app/src/main/assets/www` - no frameworks, no bundler.

Build: `gradle assembleRelease` (AGP 7.4.2, Gradle 7.6.4). v0.2.0 is signed with the same key as v0.1.0, so it installs as an upgrade over the earlier sample and Android keeps its local data (best scores, favorites, theme).

# GameBox - Offline Games App

12 classic mini-games in one tiny, fully offline Android app. No internet permission, no ads, no accounts - install and play anywhere.

**Download APK (v0.1.0 sample):** https://drive.google.com/file/d/1QJ4w_rvJa8HSyKMRCyvMDxCW9nNw6Wd7/view
(APK is ~0.04 MB. Google Drive shows a standard "Download anyway" prompt for APK files.)

## Games

2048, Snake Rush, Tic Tac Toe (vs computer), Memory Match, Mine Sweeper, Brick Breaker, Flappy Dot, Sudoku (unique-solution generator), Tower Stack, Mole Smash, Beat Echo, Paddle Clash.

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
| ![home dark](gamebox-home-dark.png) | ![home light](gamebox-home-light.png) | ![2048](gamebox-2048.png) | ![breakout](gamebox-breakout.png) | ![sudoku](gamebox-sudoku.png) |

## Tech stack

- Native Android shell: single Java `Activity` hosting a `WebView` (no AndroidX, no third-party libraries)
- Games: self-contained HTML5/CSS/JavaScript files bundled in `app/src/main/assets/www/`
- Min SDK 24 (Android 7.0), target/compile SDK 33
- Built with Gradle 7.6 + Android Gradle Plugin 7.4.2, JDK 17

## Build

1. Install Android SDK (platform 33, build-tools 33.0.2) and JDK 17.
2. Create `local.properties` with `sdk.dir=<your-sdk-path>`.
3. Debug build: `gradle :app:assembleDebug`
4. Release builds are signed with a private keystore that is not part of this repo.

## Source

The full Android Studio project (Gradle build files, Java shell, all game assets) is in **gamebox-source.zip** at the repo root. Download and unzip it, then follow the Build steps above.

## Project layout

```
app/src/main/java/com/akash/gamebox/MainActivity.java  # WebView shell + share bridge
app/src/main/assets/www/index.html                     # game library home
app/src/main/assets/www/games/*.html                   # the 12 games
app/src/main/assets/www/icons/*.svg                    # original cover art
```

# Exposure Tool

**Live App:** [https://exposuretool.netlify.app/](https://exposuretool.netlify.app/)

A professional exposure calculator and lightmeter companion for cinematographers and photographers. Supports multiple camera and film stock profiles with real dynamic range data.

## Features

- **7 Camera/Film Profiles:**
  - RED Komodo (12.5 stops, ISO metadata)
  - ARRI Alexa Mini (13.5 stops, EI metadata)
  - Leica M11 (14.5 stops at base ISO 64, real gain)
  - Kodak Vision3 50D, 250D, 500T (film stocks)
  - Kodak Double-X B&W (film stock)

- **3 Exposure Models:**
  - Digital-cinema: ISO/EI as metadata (RED, ARRI)
  - Digital-stills: ISO as real analog gain (Leica)
  - Film: Fixed rated speed with push/pull options

- **Motion/Stills Toggle:** Switch between FPS+shutter angle (motion) and direct shutter speeds (stills)

- **Real-time Analysis:**
  - Scene contrast vs sensor/film latitude
  - Highlight and shadow margin calculations
  - Profile-aware ISO/EI strategy suggestions
  - Dynamic range visualization with EV scale

## How to Use

1. **Select your camera/film profile** from the dropdown
2. **Take 3 lightmeter readings** (LV at ISO 100):
   - Brightest highlight you want to retain
   - Subject face/skin tone (18% gray)
   - Deepest shadow you want detail in
3. **Set your camera:** Aperture, ND, Shutter (FPS or speed), ISO/EI
4. **Read the analysis:**
   - Green = safe headroom
   - Yellow = tight but fits
   - Red = clipping/crushing

The tool calculates exposure delta, shows where your readings fall on the sensor/film window, and suggests optimal ISO/EI strategy based on scene characteristics (backlit, high contrast, dim, etc.).

## Technical Design

- **Single-file HTML app** — no build process, no dependencies
- **Profile-driven architecture** — each camera/film has its own DR curve, ISO behavior, and exposure model
- **Mobile-responsive** — works on phones, tablets, desktop
- **Offline-capable** — save to home screen, works without internet

## Deployment

Hosted on Netlify. Auto-deploys from `main` branch.

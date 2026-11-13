# S24-Ultra-Video-AI

A hybrid AI video-generation system built for the **Samsung Galaxy S24 Ultra**.

## Core requirements

- **Local / offline generation wherever technically possible** — the phone is the primary device.
- **No mandatory paid APIs or subscriptions.**
- **Minimum 10-second final video** — produced through chained segments if necessary.
- **Optional external compute** using the owner's own hardware, without requiring paid cloud APIs.
- **Futuristic Android interface.**

## Project structure

- `app/` — the Android application (Kotlin / Jetpack Compose)
- `compute-node/` — optional compute offload that runs on the owner's own hardware
- `docs/` — architecture and project documentation
- `assets/` — shared media assets and test fixtures

## Roles

- **Project owner & device tester:** Nishan
- **Architecture, implementation, review & troubleshooting:** ChatGPT (working branch: `chatgpt-video-build`)
- **Repository setup & GitHub coordination:** Juno

## Branches

- `main` — stable project state
- `chatgpt-video-build` — ChatGPT's development branch

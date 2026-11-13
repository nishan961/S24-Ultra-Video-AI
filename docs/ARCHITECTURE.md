# Architecture — S24-Ultra-Video-AI

## Goal

Generate a final video of **at least 10 seconds** on (or for) a Samsung Galaxy S24 Ultra,
local-first and offline wherever technically possible, with **no mandatory paid APIs
or subscriptions**.

## Design principles

1. **Hybrid generation.** On-device generation is the default path. Where a task exceeds
   what the phone can do, the system may offload to the owner's own hardware
   (see Optional external compute) — never to a paid cloud API by default.
2. **Chained segments.** If a single on-device generation pass cannot reach 10 seconds,
   the pipeline generates shorter segments and stitches them into one final video
   of 10 seconds or more, with consistent style/prompt conditioning across segments.
3. **Offline-first.** Core features must work with no network connection. Any network
   feature is optional and must degrade gracefully.
4. **Futuristic Android UI.** A modern, visually striking interface (Jetpack Compose)
   that makes generation progress, segment chaining, and export obvious at a glance.

## Components

- **Android app (`app/`)** — UI, generation orchestration, segment stitching, export.
- **On-device generation engine** — local model inference on the S24 Ultra
  (GPU/NPU-accelerated where available).
- **Optional compute node (`compute-node/`)** — a service the owner runs on his own
  hardware (e.g. a home PC) that the app may offload heavier segments to over the
  local network. Optional, never required.
- **Segment stitcher** — assembles chained segments into the final >= 10s video
  (consistent resolution, frame rate, and encoding).

## Open design questions (for the architecture phase)

- Which on-device model/runtime fits the S24 Ultra's GPU/NPU within memory limits?
- Segment length vs. quality trade-off for the chaining pipeline.
- Offload protocol between the app and the compute node (discovery, job format, results).

*Detailed design and implementation are owned by ChatGPT on the `chatgpt-video-build` branch.*

# The Bubble-Naut™ Adventures of Captain Tapioca: Issue #1

> **"Night of the Eyeball Boba!"** | *Zombie Astronaut Saga*
> **Creator:** GasMan | Gaston D. | **Date:** November 8, 2026

This repository is a lightweight **documentation bookmark** spun out from the private **Controllōrs Universe** R&D workspace. It captures the tools, workflow, and final specs behind the animated **4K 3D Claymation Comic Cover** without publishing proprietary source code, server scripts, or binary assets.

---

## Tools & References Used

| Tool | Role in Build | Link |
| :--- | :--- | :--- |
| **Meshy AI** | Textured 3D `.glb` characters & rigged animations (*Captain Tapioca*, *SlurpEye Boba*, & zero-G props) | **[Join Meshy for \$1 (Invite Link)](https://www.meshy.ai/?utm_source=meshy&utm_medium=referral-program&utm_content=DKB05C&share_type=invite-friends)** |
| **Google Antigravity** | Agentic IDE powering the WebGL2 shaders, audio beat sync, visual checks, & deterministic 4K export | [antigravity.google](https://antigravity.google/) |
| **Google Flow** | Polymer-clay cover plates across **Nano Banana Pro / Nano Banana 2** (Oct 6 concepts) and **Nano Banana 2.1** (Nov 8 isolated backdrop & HUD) | [flow.google](https://flow.google/) |
| **Google Flow Music** | Original soundtrack powering the `81.5 BPM` beat-locked eyeball blink animation | [flowmusic.google](https://flowmusic.google/) |
| **WebGL2 + FFmpeg** | Real-time skeletal skinning, custom plasticine lighting, & frame-locked `3840x3840` mastering | [WebGL2 Spec](https://registry.khronos.org/webgl/specs/latest/2.0/) / [ffmpeg.org](https://ffmpeg.org/) |

> **Note:** Sign up through the Meshy link above to get a **\$1 Meshy subscription**. Google Antigravity does not currently have a referral program and is available directly at [antigravity.google](https://antigravity.google/).

---

## Architecture Highlights

- **Clean Layer Separation:** Splits **Google Flow** sculpted polymer-clay HUD plates, isolated background craters, and live **Meshy AI** 3D meshes into distinct depth layers so 3D props never collide with baked 2D elements.
- **Clay Shader Harmonization:** Custom **WebGL2** shaders match the studio-lit clay plates using a warm key light, matte plasticine roughness, mint/taro rim highlights, and ACES Filmic tone mapping.
- **Music-Locked Animation (`81.5 BPM`):** Orbiting eyeballs beside *SlurpEye* lock their blink timing directly to the **Google Flow Music** beat grid in both live preview and offline export.
- **Deterministic 4K Mastering:** Pre-bakes synced `48 kHz` stereo audio and streams step-locked `3840x3840` frames directly into local **FFmpeg** for zero dropped frames (`30 fps`, `12s` loop, `0.33 MAE` wrap) alongside a `4K` PNG poster.

---

## Timeline Bookmark

- **Oct 6, 2026:** Original static launch (`Meshy AI` 3D rig + `Google Flow` **Nano Banana Pro / Nano Banana 2** `2K` concepts).
- **Nov 8, 2026:** Full animated `4K` claymation cover rebuild (`Google Flow` **Nano Banana 2.1** plates + `Google Flow Music` sync + custom `WebGL2` pipeline built in `Google Antigravity`).

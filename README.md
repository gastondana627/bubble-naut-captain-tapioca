# The Bubble-Naut™ Adventures of Captain Tapioca: Issue #1

> **"Night of the Eyeball Boba!"** | *Zombie Astronaut Saga*
> **Creator:** GasMan | Gaston D.
> **Origin:** Spun out from the Controllōrs Universe R&D playground | **November 8, 2026**

---

## About This Repository (Documentation Bookmark)

This repository is an **architecture & build-log bookmark** documenting the creation of an interactive, audio-reactive **4K 3D Claymation Comic Cover** (*Captain Tapioca: Issue #1*).

Because the runtime originated inside the private **Controllōrs** multi-character studio workspace, this repository intentionally contains **documentation only** (no proprietary WebGL2 runtime code, local server scripts, or 3D GLB/media binaries). If there is interest in the breakdown, WebGL2 shader harmonizer, or deterministic 4K browser-to-FFmpeg exporter, those pieces can be extracted and open-sourced separately later.

> 💡 *Tip if viewing on GitHub later:* Drag-and-drop showcase stills or the `12s` 4K loop clip directly into GitHub's web editor here so visitors can preview the live output without storing binary files in Git.

---

## Meshy, Google Flow & Google Antigravity

This project combines **Meshy** for 3D character/prop modeling & skeletal animation, **Google Flow** across two generations of **Nano Banana** image models for tactile claymation art direction, and **Google Antigravity** as the agentic engineering environment driving shader polish, audio-transient sync, visual verification, and deterministic 4K export.

- **Try Meshy for \$1 (Creator Invite Link):** Sign up using my Meshy referral link to get your **\$1 Meshy subscription** and start generating textured & rigged 3D `.glb` assets:
  **[Join Meshy for \$1](https://www.meshy.ai/?utm_source=meshy&utm_medium=referral-program&utm_content=DKB05C&share_type=invite-friends)**
- **Google Flow (Nano Banana Pro / 2 -> Nano Banana 2.1):** Powered both phases of the visual universe. The original Oct 6 comic-cover concept artwork and `2K` (`2752x1536`) typography studies were generated in Flow using **Nano Banana Pro / Nano Banana 2**. The Nov 8 production overhaul upgraded to **Nano Banana 2.1** inside Flow (guided via Flow workflow tooling on **Omni 1.2 Flash**) to isolate the clean cosmic crater plate, corner box badge, Comics Code stamp, barcode, sculpted masthead, starburst plaque, and saga ribbon.
- **Google Antigravity:** Used to architect the custom WebGL2 plasticine shaders, BPM blink lock, alpha-cutout alignment, and FFmpeg studio pipeline. Google Antigravity does not currently offer a user referral link or invite-friends program, and individual developers can start directly on its free tier at **[antigravity.google](https://antigravity.google/)**.

---

## References & Software Used

| Tool / Technology | Role in Build | Reference |
| :--- | :--- | :--- |
| **Google Antigravity** | Agentic IDE, WebGL2/Canvas2D engineering, headless CDP verification, & FFmpeg mastering pipeline | [antigravity.google](https://antigravity.google/) |
| **Meshy AI** | Textured 3D `.glb` generation & Mixamo bipedal skeletal animations (*Captain Tapioca*, *SlurpEye Boba*, *Lime Tofu*, *Sriracha Mascot*, *Shattered Tea*) | [Meshy (\$1 Subscription Invite)](https://www.meshy.ai/?utm_source=meshy&utm_medium=referral-program&utm_content=DKB05C&share_type=invite-friends) |
| **Google Flow (`Nano Banana Pro / 2` & `Nano Banana 2.1`)** | Two-stage polymer clay visual pipeline: Oct 6 `2K` concept & typography sheets (**Nano Banana Pro / Nano Banana 2**) followed by Nov 8 isolated cosmic craters, corner box, Authority seal, barcode, masthead, starburst plaque, & folded ribbon (**Nano Banana 2.1**, alongside **Omni 1.2 Flash** Flow tooling) | [flow.google](https://flow.google/) / [labs.google](https://labs.google/) |
| **WebGL2 (`GLSL ES 3.00`)** | Zero-dependency real-time skeletal skinning (`28` joints) & matte polymer-clay lighting shader | [Khronos WebGL2 Spec](https://registry.khronos.org/webgl/specs/latest/2.0/) |
| **SVG + Canvas2D + Web Audio API** | Procedural floating pearls, `81.50 / 163.00 BPM` beat-locked eyeblink eyelids, & `OfflineAudioContext` stereo soundtrack bounce | [MDN Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) |
| **FFmpeg & FFprobe** | Local frame-locked `3840x3840` H.264 / `48 kHz` AAC muxing & forensic stream inspection | [ffmpeg.org](https://ffmpeg.org/) |
| **Python (`http.server`)** | Lightweight local asset bridge & export session orchestrator | [docs.python.org](https://docs.python.org/3/library/http.server.html) |

---

## The Hybrid Creative-Engineering Stack

Rather than picking between static AI image generation or rigid real-time 3D alone, this build splits responsibilities across four specialized layers so every element plays to its strength:

| Layer | Role | Tooling / Approach |
| :--- | :--- | :--- |
| **Static Sculpted Clay Plates** | Tactile polymer clay universe framing (clean cosmic craters, comic bezel, corner box badge, Comics Code stamp, barcode, sculpted masthead, starburst plaque, bottom saga ribbon) | **Google Flow (`Nano Banana Pro / 2` -> `Nano Banana 2.1`)** + custom hole-preserving chroma alpha extraction |
| **Skinned 3D Cast & Zero-G Props** | *Captain Tapioca* (`28`-joint Mixamo biped rig), *SlurpEye Boba* (animated companion), *Lime Tofu*, *Sriracha Blood Mascot*, & *Shattered Boba Cup* | **Meshy AI** GLB assets rendered live via custom zero-dependency **WebGL2** skinning shaders |
| **Audio-Reactive Procedural Stage** | Animated foreground boba pearls, midground striped boba straw, and **beat-locked blinking eyeballs** next to SlurpEye | **SVG + Canvas2D + Web Audio API** transient grid (`81.50 / 163.00 BPM`) |
| **Studio 4K Mastering** | Frame-accurate `3840x3840` seamless `12.04s` MP4 loop with synced stereo soundtrack + lossless `4K` RGBA poster PNG | **OfflineAudioContext + Local FFmpeg Muxer** |

---

## Compositor Layer Architecture

To eliminate visual clashes between baked 2D art and animated 3D meshes, the stage composites five strict depth layers in both live browser preview and offline 4K export:

```text
Z-4  Foreground Sculpted Clay HUD Overlay (Google Flow RGBA Plates)
     ├── Masthead + Milk-Tea Splash ("THE BUBBLE-NAUT ADVENTURES OF CAPTAIN TAPIOCA")
     ├── Top-Left Issue #1 Box Badge & Top-Right Authority Stamp
     ├── Bottom-Left Barcode + Tilted (-2.4 deg) "ZOMBIE ASTRONAUT SAGA" Ribbon
     └── Bottom-Right Starburst ("TAPIOCA & SLURPEYE IN NIGHT OF THE EYEBALL BOBA!")

Z-3  Foreground Dynamic Canvas / SVG Layer + Outer Clay Frame
     ├── Sculpted Outer Frame & Debossed Creator Hallmark
     ├── Zero-G Orbiting Boba Pearls
     └── Beat-Locked Blinking Clay Eyeballs (81.50 / 163.00 BPM)

Z-2  Real-Time Hardware-Skinned 3D Stage (WebGL2 @ 2048x2048 SSAA)
     ├── Captain Tapioca (28-Joint Skeletal GLB + Multi-Clip Choreography)
     ├── SlurpEye Boba Companion (Animated GLB)
     └── Zero-G Lab Props (Lime Jelly Tofu, Sriracha Mascot, Shattered Tea)

Z-1  Midground Environmental Prop
     └── Matte-Shaded Diagonal Striped Boba Straw (Cleanly split for Mode 0 Cover vs. Mode 1 Pure 3D)

Z-0  Clean Cosmic Clay Background Plate (2048x2048)
     └── Polymer clay moon craters & purple/lavender swirls (zero baked 2D prop stencils)
```

---

## Key Technical Problems Solved

### 1. Solving the "Mixed-Media Discomfort" (2D vs. 3D Separation)
- **Stencil Conflict Fix:** Early passes had a 2D lime tofu stencil baked onto the background plate underneath the floating 3D Lime Tofu GLB (`Loop-7`). Regenerating a clean background plate from Flow removed the duplicate stencil so the 3D prop floats cleanly over empty polymer clay craters.
- **Shader & Lighting Harmonization:** Custom GLSL fragment shaders align real-time 3D GLBs with Flow's pre-lit clay photography:
  - Warm studio top-left key light (`#FFF4E0`)
  - Remapped plasticine surface roughness (`clayRough` clamped between `0.45` and `0.90`) to kill harsh PBR metallic glare and specular shimmer during camera orbit
  - Stepped claymation light-wrap + cool Mint (`#8CE9C6`) and Taro (`#C8A2F8`) Fresnel rim lighting
  - Soft silhouette contour + **ACES Filmic** tone-mapping blend
- **Progressive Clay HUD Replacement:** Replaced all flat SVG typography (masthead, starburst plaque, saga ribbon, barcode, corner box, authority stamp) with studio-lit polymer clay plates while preserving a matching Canvas2D draw pipeline (including rotated `-2.4°` ribbon transforms) for lossless exports.

### 2. Music-Locked Blinking Eyeballs (`81.50 / 163.00 BPM`)
- The pair of hero eyeballs orbiting beside SlurpEye lock directly to the peak transient & beat grid of **`Skeleton Strut.mp3`**:
  - During live interactive playback, blink progress tracks **`AudioContext.currentTime`** directly to stay drift-free with real audio output.
  - During deterministic offline 4K rendering, the blink clock binds strictly to exact simulation time `t` alongside `OfflineAudioContext` audio rendering.

### 3. Why Offline Frame-Locked Export Beat `MediaRecorder`
Browser `MediaRecorder` at `4K` resolution drops frames and drifts against live `WebGL2` skinning + audio clocks. Replacing it with a deterministic two-pass pipeline solved both:
1. **Exact Audio Pre-Bake:** Renders the `12.04s` `48 kHz` stereo soundtrack via `OfflineAudioContext` into WAV.
2. **Step-Locked Frame Streaming:** Advances `renderFrameAtTime(simElapsed)` across `361` exact timestamps (`frameIdx 0..360` at `30.000 fps`), composites all 5 DOM-identical layers on Canvas2D, streams frames to local FFmpeg, and encodes `3840x3840` H.264 + AAC.

### Interactive Stage Modes Built
- **Mode 0 (Comic Cover Edition):** Full clay bezel, sculpted Flow plates, 3D stage, and beat-synced eyeballs.
- **Mode 1 (Pure 3D Boba Stage):** Strips all comic chrome to showcase the live 3D characters, props, and reconstructed diagonal straw.
- **Mode 2 (FMU Broadcast Video Reel):** Embedded reference broadcast / `9:16` social cuts.
- **Mode 3 (28-Joint Mixamo BTS):** Real-time projected skeletal bone lines (`Head`, `Hips`, `Hands`, `Feet`) and camera telemetry over the live 3D model.

---

## Verified Final Build Benchmarks (`Nov 8, 2026` | Loop-10 Pass)

| Output Target | Specification | Measured Quality |
| :--- | :--- | :--- |
| **4K Video Loop** | `3840x3840` H.264 (`30 fps`, `361` frames, `22.57 Mbps`) + `48 kHz` stereo AAC (`12.040s`, `~34.0 MB`) | **Zero dropped frames**; identical CSS and Canvas2D parity across all 7 clay plates |
| **Motion Smoothness** | Full 361-frame MAE scan (`384x384` forensic check) | Max consecutive delta **`4.275 MAE`** across the entire `12.04s` loop |
| **Seamless Loop Wrap** | Delta between `frame 0` (`t=0.000s`) and `frame 360` (`t=12.000s`) | **`0.331 MAE`** (virtually imperceptible loop point) |
| **4K Static Poster** | `3840x3840` RGBA lossless PNG (`~22.6 MB`) | Verified 1:1 parity with live WebGL2/CSS viewport |

---

## Iteration Timeline Bookmark

- **Oct 6 Origin (`2K` Concept Launch):** Early *Bubble-Naut* hero renders and `2752x1536` typography sheets generated in **Google Flow** using **Nano Banana Pro / Nano Banana 2**, paired with the initial auto-rigged **Meshy AI** *Captain Tapioca* `.glb`.
- **Loops 1 to 6:** Controllōrs Universe prototype to Bubble-Naut spin-off scaffolding, multi-GLB WebGL2 loader, 4-act zero-G camera & FMU modes.
- **Loop 7:** Integrated SlurpEye + Sriracha + Lime Tofu 3D cast; added `81.50 / 163.00 BPM` audio-synced blinking eyeballs and upgraded comic HUD plaques.
- **Loop 8 (`Nano Banana 2.1` Pass 1):** Upgraded to **Google Flow (`Nano Banana 2.1` + `Omni 1.2 Flash` workflow tooling)** to eliminate the 2D-under-3D Tofu stencil conflict via a clean cosmic crater plate plus tactile clay corner box, Comics Code seal, and barcode; harmonized WebGL2 lighting & roughness.
- **Loop 9 to 10 (`Nano Banana 2.1` Final Pass):** Upgraded final vector UI zones (*Bubble-Naut Masthead*, *Zombie Astronaut Saga Ribbon*, *Eyeball Boba Starburst*) into keyed **Nano Banana 2.1** polymer clay plates with full straw continuity and verified deterministic 4K MP4 (`0.331 MAE` loop wrap) / PNG parity.

---

*Built with curiosity as part of the Controllōrs Universe creative engineering experiments (bookmarked Nov 8, 2026).*

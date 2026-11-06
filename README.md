# ⚡ BEATrip

> **Cinematic 2D Rhythm-Action Hybrid (Dodge-Parry-Pulse) & In-Engine NLE Level Editor in Godot 4.**
>
> *"An interactive music video where the player is not a victim of bullets, but the conductor of the drop."*

[![Engine](https://img.shields.io/badge/Engine-Godot%204.7.2-478cbf?logo=godotengine&logoColor=white)](https://godotengine.org)
[![Version](https://img.shields.io/badge/Version-v0.7.1-brightgreen)](#)
[![Aesthetic](https://img.shields.io/badge/Style-Vantablack%20Cyber--Minimalism-020204)](#)
[![Vector](https://img.shields.io/badge/Graphics-Native%20ThorVG%20SVG-orange)](#)
[![Target](https://img.shields.io/badge/Resolution-1080p%20%7C%201440p%20%7C%204K%20%7C%2021:9-success)](#)

---

## 📥 Download & Community (Public Hub)

Welcome to the official public repository for **BEATrip**! This hub serves as the central place for official game builds, changelogs, architectural overviews, and community feedback from players and charters.

* [**📦 Download Latest Build (Releases)**](../../releases) — Ready-to-play standalone builds for Windows.
* [**🐛 Report a Bug / Request a Feature (Issues)**](../../issues) — Issue tracker for bug reports and feature suggestions.
* [**💬 Community & Custom Levels (Discussions)**](../../discussions) — Share custom charts, ask NLE editor questions, and connect with the community.

---

## 🚀 Key Features

### 1. Combat Mechanics: From Prey to Predator

* **Dodge + Rhythm Parry + Reversal**: Free-form 2D spatial dodging combined with rhythm-synced parrying of unblockable attacks (<kbd>Space</kbd> / <kbd>LMB</kbd>).
* **Cinematic Feedback**: Tactile Hitstop ($80\text{--}120\text{ ms}$), full-screen color inversion, expanding Shockwave Rings, and projectile deflection back off-screen.
* **Risk & Reward (Graze System)**: Razor-thin near-misses recharge your shield and dash meter.

### 2. In-Engine NLE Level Editor (After Effects / Premiere Style)

* **Freeform Tracks & Multi-BPM**: Unrestricted object placement, piecewise-constant beat calculation, and a dynamic measure grid.
* **Multi-Threaded Waveform**: Background PCM audio decoding with binary disk caching.
* **Keyframing Engine**: Property stopwatches, dedicated keyframe sub-lanes (`▼`), interpolation curves (`Ease In/Out`), and DAW-style fade handles.
* **Photoshop-Style Free Transform**: 8 viewport resize handles featuring one-sided anchored stretching and corner rotation.
* **Native Undo / Redo**: Comprehensive state history (<kbd>Ctrl+Z</kbd> / <kbd>Ctrl+Y</kbd>) across all editor operations.
* **Categorized Inspector**: Parameter mini-icons, individual property resets (`⟲`), and global `Reset [⟲]` to defaults.
* **Asset Loading & Inline Renaming**: Native OS `FileDialog` integration and direct inline renaming of timeline objects.

### 3. Performance & Vector Pipeline

* **Zero Raster PNGs In-Game**: 100% procedural vector rendering (`_draw()`) and native `.svg` support powered by ThorVG, delivering infinite sharpness at any zoom level up to 4K and 21:9 ultrawide.
* **$O(K)$ Active Window Optimization**: Hybrid binary search for active frame events ($15.7\times$ speedup compared to linear iteration).

### 4. Level Bundle Architecture & Library

* **Self-Contained Level Packages**: Every level lives in an isolated directory (`res://levels/` and `user://levels/`) containing its own `level.json`, `meta.json` manifest, `audio.mp3`, and $512 \times 512$ `preview.png` cover art.
* **Full-Screen Level Library**: Visual level cards with cover art, filtering, live search, and a "+ Create New Level" workflow.
* **Ergonomic Saving**: Instant save (<kbd>Ctrl+S</kbd>) directly to the level bundle, slide-out "Project Saved!" toast notification, and an unsaved changes guard on <kbd>Esc</kbd>.
* **In-Game Diagnostic Console**: Built-in logger and terminal (<kbd>~</kbd> / <kbd>F12</kbd>) featuring search, severity filters, and one-click crash/report dump export.

### 5. Swiss Cyber-Brutalism Main Menu

* **Contrast Inversion Buttons (`InvertButton`)**: Smooth white fill sweep with instant typography color inversion to Vantablack (`#020204`) and a `+12px` kinetic shift.
* **Integrated OST Jukebox**: Top-docked dropdown audio player dynamically indexing level tracks, complete with seek bar, loop, and shuffle controls.
* **osu!lazer-Inspired Settings Drawer**: Two-column slide-out panel (`750px`), 5-category sidebar with square hover-inversion, continuous scroll feed with a `24px` scrollbar gutter, and real-time screen LOD blur.
* **Audio-Reactive 3-Layer Parallax**: Kinetic background arena featuring a deep perspective grid, FFT spectrum equalizer, and a pseudo-3D shard swarm.
* **Typographic Glitch Logo**: High-contrast pairing of heavy geometric *Inter 900* and sharp *Playfair Display Italic* serif with cascading glitch shaders.

---

## ❓ FAQ (Frequently Asked Questions)

### What is the core design philosophy of the game?

To craft a hyper-tactile, responsive, and uncompromising experience at the intersection of rhythm action and professional creative software:

* **Gameplay:** The fluidity, visual clarity, and low-latency responsiveness of *osu!*.
* **NLE Editor:** The workflow speed and timeline power of *Sony Vegas*, *Adobe Premiere*, and *FL Studio*. A clean, minimalist UI housing deep choreography tools under the hood.

### Is this a clone of JSAB (Just Shapes & Beats) or Project Arrhythmia (PA)?

Yes and no. The concept for **BEATrip** originated back in 2017 as a spiritual successor to *Beat da Beat*. While we share a community-driven DNA with *Project Arrhythmia*, **BEATrip** follows a distinct vision centered around active combat mechanics (rhythm parrying and counter-attacks), Swiss Cyber-Brutalist aesthetics, and—above all—a professional NLE editor architecture. It is not a clone, but a distinct evolution of the genre.

### Why vector graphics instead of pixel art or raster sprites?

The project initially started as a pixel-art shmup, but during development it became clear that pure vector rendering (via procedural drawing and ThorVG) unlocks unmatched creative freedom:

* Zero pixelation or blurriness during extreme camera zooms and $360^\circ$ rotations.
* Razor-sharp clarity on 1440p, 4K, and 21:9 ultrawide monitors.
* Tiny footprint: custom levels weigh kilobytes rather than десятки megabytes.
* Native support for importing custom `.svg` vector shapes.

### What about Story Mode?

Story Mode is the original spark that started **BEATrip**. However, building a complex campaign without first having a rock-solid level editor is a guaranteed path to solo-dev burnout. Therefore, the top priority is perfecting the in-engine NLE editor first, which will then serve as the foundation for building the 5-act Story Mode campaign.

### Will the game release on Steam?

Likely, yes. Launching on Steam is a major milestone that requires legal preparation and financial investment. I don't want to rush into Early Access until the core gameplay and NLE editor reach an uncompromising standard of polish, but a Steam release remains a primary long-term goal.

### Why is the project on GitHub if the source code is closed?

GitHub is the best platform for build distribution and structured community feedback. It provides a seamless workflow for tracking bug reports via **Issues** (paired with dumps from our built-in diagnostic console), hosting community conversations in **Discussions**, and delivering standalone builds via **Releases**.

Regarding the closed source code: I want to maintain architectural integrity and protect the project's ecosystem. While the core engine and level bundle format are actively evolving, open-sourcing the code prematurely would lead to instant fragmentation—spawning incompatible forks and splitting the charter community before it even matures.

**However (End-of-Life Open Source Pledge):** If I ever permanently cease development or am no longer able to maintain the project, I will gladly release the full source code to the community.

### Was this project built with AI? Why use it?

Yes, our code engineering pipeline actively leverages Multi-Agent AI Orchestration, and I am completely transparent about it. Two core principles govern how AI is used in **BEATrip**:

1. **100% Human Creativity:** AI is used *exclusively* for software engineering and code generation. All music, sound design, visual direction, level choreography, and game design are crafted by hand.
2. **Strict Engineering Discipline:** This is not "vibe-coded AI slop." Every module goes through strict *Human-in-the-loop* supervision, architectural review, and automated headless QA testing (200+ automated assertions across our test suites).

First and foremost, I am a musician and game designer. With limited free time for hobbyist development, building a custom vector engine and a full-featured NLE editor solo would take many years without AI assistance. I act as the Systems Architect and Team Lead—designing module specs, UX workflows, and technical invariants—while delegating routine code implementation to fast AI agents.

---

## 📖 Internal Architecture & QA Pipeline

**BEATrip** is engineered around a strict specification-driven workflow backed by over 200+ automated headless QA checks verifying audio buses, UI invariants, level bundling, and Undo/Redo state integrity:

* **`PROJECT.md`** — Single Source of Truth, codebase architectural map, and directory structure.
* **`TODO.md`** — Live roadmap and task tracker (completed phases, active sprints, icebox backlog).
* **`GDD.md`** — Game Design Document (4 core pillars, parry mechanics, 5-act story outline, soundtrack).
* **`IDENTITY_AND_VISUAL_SPEC.md`** — Visual style manifesto, the 90/7/3 color rule, and cinematic rendering stack.
* **`MENU_SPEC.md`** — Main menu specification (Swiss Brutalism, `InvertButton`, OST Jukebox).
* **`pipeline.md`** — Feature development lifecycle (Headless QA suites, screenshot verification, Dual Review).

<details>
<summary><b>🛠️ Automated Headless QA Suite Commands (Dev Environment)</b></summary>

<br>

Audio buses, dynamic pitch, and Jukebox verification (49 checks):
```bash
godot --headless -s res://tests/qa_audio_and_jukebox_test.gd
```

Main menu specification invariants (85 checks):
```bash
godot --headless -s res://tests/qa_main_menu_spec_test.gd
```

Level Bundle packaging & manifest integrity (49 checks):
```bash
godot --headless -s res://tests/qa_level_bundle_test.gd
```

Comprehensive Editor Stress Test suite:
```bash
godot --headless -s res://tests/qa_editor_stress.gd
```

Undo / Redo state history reliability test:
```bash
godot --headless -s res://tests/qa_undoredo_test.gd
```

</details>

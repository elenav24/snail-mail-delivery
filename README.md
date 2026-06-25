# 🐞 Ladybug Garden (Game Project 1)

A 2D physics-based precision platformer featuring momentum-based movement mechanics, variable gravity states, and dynamic event-driven game states. 

## Project Links
* **Live Playable Build:** **[snail.elenav.me](https://snail.elenav.me)**
* **Source Code:** **[GitHub Repository (Game Scripts)](https://github.com/elenav24/ladybug-garden-scripts)**

---

## Core Mechanics & Features

- **Momentum-Based Movement** — Implemented comprehensive horizontal vector shifts alongside a custom "glide" mechanic that modifies the dynamic fallback velocity when the primary jump key is sustained.
- **Stackable Status Effects** — Developed a temporal buffer system that dynamically updates runtime speed variables for 10 seconds upon collision triggers, supporting linear time-stacking for consecutive power-up collections.
- **State-Driven Environmental Interactions** — Engineered distinct physical layer configurations where objects dynamically shift behavior based on contact normal vectors (e.g., solid top-surface platforming vs. zero-friction side collisions).
- **Asynchronous Loop Control** — Designed decoupled game execution cycles to handle real-time pauses, scene reloading, and structural application teardowns cleanly.

---

## System Architecture & Class Breakdown

The codebase is organized using a highly decoupled component-driven architecture built over the native Unity runtime framework:

### Player & Physics Engineering
* **`PlayerMovement.cs`:** Governs horizontal kinematics and vertical impulse forces. Houses custom arithmetic logic to step down localized gravity constraints to simulate sustained gliding.
* **`CameraFollow.cs`:** Calculates interpolated target vectors per rendering frame to smoothly track the player across screen-space thresholds.
* **`DeathZone.cs`:** Acts as a bounding-box trigger matrix, executing an automated scene reset hook whenever positional coordinates fall outside defined boundary indexes.

### Game Lifecycle & UI Orchestration
* **`GameManager.cs` & `PauseMenu.cs`:** Manages operational canvas switching (Main Menu, Active Game, Pause State, and Win Screens). Features scalable control blocks to safely pause structural application systems and capture global escape keys.
* **`Goal.cs`:** Handles absolute end-of-level validation when connecting with target entities, systematically pausing global physics clocks while invoking final canvas states.
* **`FlowerBoost.cs`:** Operates as a decoupled script component attached to power-up matrices, orchestrating clean property updates directly into the player's core physics runtime variables.

---

## Tech Stack & Asset Pipeline

### Engine & Code Architecture
* **Engine:** Unity
* **Language:** C# (.NET Core Framework)
* **Design Pattern:** Component-Based Architecture / Event-Driven State Changes

### Design & Asset Production
* **Deployment Pipeline:** Unity WebGL Compiler hosted on static edge deployment
* **Sprite Assets:** Custom low-overhead pixel artwork generated via **Piskel** (Piskelapp)
* **Interface Design:** UI design frames, text matrices, and informational canvases drafted via **Canva** and compiled directly into native Unity UI assets

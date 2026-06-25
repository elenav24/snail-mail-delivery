# 🐌 Snail Mail Delivery Game

A 2D top-down precision platformer featuring state-driven inventory validation, temporal speed-modifiers, and emergent routing paths.

## Project Link
* **Live WebGL Build:** **[snail.elenav.me](https://snail.elenav.me)**

---

## Core Features & Architecture

- **Asynchronous Coroutines (`playerMovement.cs`):** Utilizes C# `IEnumerator` blocks to handle time-restricted velocity modifiers (1.5x Sugar Cube speed-boost / 0.5x Water Puddle friction damping).
- **Decoupled Animation Anchors:** Implemented an isolated nested parenting hierarchy to drive sinusoidal floating animations on the local Y-axis without polluting global world coordinates.
- **State-Driven Inventory Gating (`snailInventory.cs` & `Goal.cs`):** Manages boolean item collection states to dynamically toggle trigger colliders, audio layers, and rendering states at the goal mailbox.
- **Data Persistence Pipeline (`saveManager.cs`):** Uses `PlayerPrefs` to cache global runtime volume mixers and store level completion progress (Star Rankings) across system sessions.
- **UI Lifecycle Control (`pauseManager.cs` & `menuManager.cs`):** Freezes the global execution clock (`Time.timeScale`) and intercepts input arrays to route canvas overlays smoothly.

---

## Progression & Scene Breakdown

* **Main Menu:** Handles system configurations, audio mixer overrides, and level indexing.
* **Level 1 (Tutorial):** Sandbox designed to isolate core 8-directional kinematics and delivery mechanics.
* **Level 2 (Speed Dilation):** Introduces speed-boost optimization over an expanded grid layout.
* **Level 3 (Emergence):** Combines power-ups and water hazards to force user path optimization.

---

## Tech Stack & Credits

* **Engine & Language:** Unity | C# (.NET)
* **Design & Asset Production:** Piskel (Custom assets), Unity UI Canvas, Unity Tilemaps
* **Third-Party Assets:** Itch.io (Cozy UI Kit, Nature Tileset, Snail Pack), Uppbeat/Pixabay (Audio layers)

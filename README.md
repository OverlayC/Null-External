# Null-External

A lightweight, external Roblox utility focused on FPS games. Written in C# with a modular design — aim lock, trigger bot, silent aim, and ESP in one package.

> **Status:** Active development. Aim Lock is stable; Trigger and Silent Aim are in progress.

---

## Features

| Feature | Status | Notes |
|---|---|---|
| **Aim Lock (Head)** | ✅ Working | Per-tick head resolution — always targets the real `Head` part, with bbox/root fallbacks. No distance-based drift. |
| **Aim Lock (Body/Custom Part)** | 🚧 Planned | Selectable target part (Head, Torso, HumanoidRootPart, or custom) |
| **Aim Lock (Smoothing Presets)** | 🚧 Planned | Configurable smoothing curves (linear, exponential, ease-in-out) |
| **Aim Lock (FOV Circle)** | 🚧 Planned | On-screen FOV ring so you know the lock radius |
| **Aim Lock (Priority Modes)** | 🚧 Planned | Choose target by distance, screen proximity, lowest health, or crosshair angle |
| **Aim Lock (Visibility Check)** | 🚧 Planned | Skip targets behind walls using raycast-style checks |
| **Trigger Bot** | 🚧 In progress | Auto-fire when crosshair is on target |
| **Trigger Bot (Delay/Hitchance)** | 🚧 Planned | Configurable reaction delay and hitchance percentage |
| **Silent Aim** | 🚧 In progress | Redirect shots to target without moving camera |
| **Silent Aim (Hitbox Selector)** | 🚧 Planned | Choose which hitbox to redirect to (Head, Torso, Nearest) |
| **ESP** | ✅ Working* | Works on games using standard player/character replication. Does **not** support custom player systems (e.g. custom rigs, server-side character replacement). |
| **ESP (Boxes)** | 🚧 Planned | 2D/3D bounding boxes with configurable colors |
| **ESP (Skeleton)** | 🚧 Planned | Bone-based skeleton rendering (R6 and R15) |
| **ESP (Health Bars)** | 🚧 Planned | Health bars with numeric display |
| **ESP (Name Tags)** | 🚧 Planned | Player names and distance in studs |
| **ESP (Tracers)** | 🚧 Planned | Lines from screen center or bottom to target |
| **ESP (Chams)** | 🚧 Planned | Highlight through walls (Roblox `Highlight` instance injection) |
| **ESP (Team Check)** | 🚧 Planned | Filter out teammates in team-based games |
| **ESP (Distance Filter)** | 🚧 Planned | Only render players within a configurable range |
| **World Mods (Fullbright)** | 🚧 Planned | Disable shadows / ambient lighting |
| **World Mods (No Fog)** | 🚧 Planned | Remove fog for long-range visibility |
| **World Mods (FOV Changer)** | 🚧 Planned | Override camera FOV beyond Roblox limits |
| **Player List** | 🚧 Planned | In-app list of all players with per-player toggles |
| **Config System** | 🚧 Planned | Save/load settings to JSON |
| **Hotkey System** | 🚧 Planned | Rebindable hotkeys for every feature |
| **Stream Proof** | 🚧 Planned | Hide overlay from OBS/Discord/Medal capture |
| **Anti-Screenshot** | 🚧 Planned | Block Roblox screenshot APIs from capturing overlay |
| **Auto-Attach** | 🚧 Planned | Auto-detect and attach to Roblox on launch |
| **Fly / Noclip** | 🚧 Planned | Camera or character flight with adjustable speed (external physics override) |
| **Speed Hack (WalkSpeed)** | 🚧 Planned | External WalkSpeed write with configurable multiplier and toggle |
| **Jump Power Modifier** | 🚧 Planned | Adjust JumpPower / JumpHeight for higher jumps |
| **Teleport (Click-to-Move)** | 🚧 Planned | Click a world position or player to teleport your character there |
| **Anti-Aim** | 🚧 Planned | Randomised or spin-based camera jitter to break other aimbots |
| **Third-Person / Camera Unlock** | 🚧 Planned | Detach camera from character (freecam) for scouting |
| **Auto Rejoin** | 🚧 Planned | Rejoin the same server after disconnect/kick |
| **Server Hop** | 🚧 Planned | Hop to a new server of the same game |
| **Ping / FPS Overlay** | 🚧 Planned | Live performance stats in the overlay |
| **Discord RPC** | 🚧 Planned | Show current game and feature status in Discord rich presence |
| **Plugin System** | 🚧 Planned | Load external `.dll` modules at runtime for community-made features |

\* ESP relies on the standard `Players` → `Character` → `Head`/`HumanoidRootPart` hierarchy. Games that bypass this won't render correctly.

---

## Compatibility

### ✅ Currently works on
- Knife Duels
- Sniper Duels
- Arsenal *(maybe — needs testing)*

### ❌ Does not work on
- Rivals *(uses a custom player system)*

---

## Building

### Requirements
- [.NET SDK](https://dotnet.microsoft.com/download) (8.0 or later)
- Visual Studio 2022 **or** the `dotnet` CLI

### Build a standalone `.exe` (no .NET install required on target machine)

```bash
dotnet publish -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true

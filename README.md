# Null-External

A lightweight, external Roblox utility focused on FPS games. Written in C# with a modular design — aim lock, trigger bot, silent aim, and ESP in one package.

> **Status:** Active development. Aim Lock is stable; Trigger and Silent Aim are in progress.

---

## Features

| Feature | Status | Notes |
|---|---|---|
| **Aim Lock (Head)** | ✅ Working | Per-tick head resolution — always targets the real `Head` part, with bbox/root fallbacks. No distance-based drift. |
| **Trigger Bot** | 🚧 In progress | Coming soon |
| **Silent Aim** | 🚧 In progress | Coming soon |
| **ESP** | ✅ Working* | Works on games using standard player/character replication. Does **not** support custom player systems (e.g. custom rigs, server-side character replacement). |

\* ESP relies on the standard `Players` → `Character` → `Head`/`HumanoidRootPart` hierarchy. Games that bypass this won't render correctly or at all in most cases.

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
- Does Ask For **Admin** On Start

### Build a standalone `.exe` (no .NET install required on target machine)

```bash
dotnet publish -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true

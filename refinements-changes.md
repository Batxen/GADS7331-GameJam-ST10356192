## Refinements - Last 24 Hours

Date: 2026-03-27

### Gameplay Code Updates

- `Assets/Scripts/PlayerControls.cs`
  - Added more robust collision-aware movement for both player and drone using sweep casts and slide movement.
  - Added grounded checks and jump handling with configurable gravity, jump decay, and stick-to-ground behavior.
  - Improved dual-control flow (`Q` toggle) with smoother drone follow behavior and camera mode offsets.

- `Assets/Scripts/MirrorPuzzle.cs`
  - Added overlap verification via `Physics.OverlapBoxNonAlloc` to recover from missed trigger events.
  - Added mirrored movement delta processing by axis (`mirrorX`, `mirrorY`, `mirrorZ`).
  - Added collision-aware mirror movement with cast-based blocking and sliding to reduce clipping.
  - Added dynamic mirror collider syncing so mirror collider type/shape matches the player collider.

- `Assets/Scripts/ClonePuzzle.cs`
  - Added explicit overlap-state refresh to improve trigger reliability in multi-collider scenarios.
  - Added collision-aware clone movement and slide handling.
  - Added runtime collider replication from player to clone/mirror object to preserve physical behavior.

- `Assets/Scripts/HatchLogic.cs`
  - Refined hatch activation logic with clearer activator validation (drone and optional player).
  - Added coroutine-based axis-constrained raising with animation curve support.
  - Added one-time activation guard with optional replay behavior.

- `Assets/Scripts/HatchHold.cs`
  - Updated hold-trigger logic to track active colliders using sets for stable multi-collider behavior.
  - Added enter/exit-driven move interpolation between initial and offset positions.
  - Added support for drone and optional player activation paths.

### Content / Scene Integration

- Updated puzzle and test scene content in:
  - `Assets/Scenes/JamBuild.unity`
  - `Assets/Scenes/DemoBuild.unity`
- Updated puzzle prefabs/material setup in:
  - `Assets/Blueprints/SwitchToggle.prefab`
  - `Assets/Materials/*.mat`

### Project / Package Updates

- Unity package definitions updated:
  - `Packages/manifest.json`
  - `Packages/packages-lock.json`
- Rendering/build-related project settings updated:
  - `ProjectSettings/GraphicsSettings.asset`
  - `ProjectSettings/EditorBuildSettings.asset`
  - `Assets/Settings/PC_RPAsset.asset`

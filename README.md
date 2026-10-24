# CATACLYSM — SOLAR LANCE (Java/Fabric source prototype)

Target: Minecraft Java 1.20.1 / Fabric, including PojavLauncher where compatible.

**This is SOURCE, not a tested playable .jar.** This environment could not download Fabric/Minecraft dependencies, so Gradle compilation and in-game verification were impossible. No promise of cinematic quality or Android compatibility is made.

## Build
- Use JDK 17 and Gradle 8.7 with internet access.
- In this folder run: `gradle build`
- Result after successful compilation: `build/libs/cataclysm-solar-lance-0.1.0.jar` (use the remapped non-sources JAR).
- Install Fabric API 0.92.2+1.20.1 in Pojav's `mods` folder alongside the built mod.

## Test
- Give item: `/give @s cataclysm:solar_lance`
- Right-click/use it aiming at terrain. Client renders a staged 3D beam; server explosion occurs ~3.2 seconds later.
- Keep render distance at 6–8 chunks on mobile.

## Current limitations
- Singleplayer-oriented prototype. Client effects are initiated locally and are not synchronized to nearby players.
- No custom shaders, sound design, crater algorithm, camera animation, or dynamic lighting.
- Visual system uses additive geometry, not physically based volumetric lighting.
- Aiming over unloaded chunks or very far away can yield a target in the air.
- Not benchmarked; test in a separate world due to destructive explosion.

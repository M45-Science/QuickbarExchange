# M45 Quickbar Exchange (Format V2)

## Example
### V2 example string:
`eNqtwbENgDAMRcGFHg2CkiI/CZFjI0CiIfsPwhLcHcs63Zq3ENEpg5ooL1W0CzleaQ9KRGDCMjbomST6ie9k428fo+EebA==`

97 bytes for 20 items, or about 4.75 bytes per item once fully encoded.

### V1 example string:
`eNqtULFuQzEI/CEzVGrHLt079BOwH3VQMFjAi/r5ddIoUTKX4dAdAt3x+foGXx8v75FEAu1AkSXSHDtBoh4L/UynCEhHjWmeUEnyJu+6kXe31R8HMYUzycs3RgJrkJ+ZmHY44Nra7mLd5XhnMVAESKilc4NpQmXQxvt4Eiv3JyX2GonJpmXypAtAGvwZLI4sF4DgrigFW/KJYLqdeOW45nerdk56dSI4Zmmm67ImNBuVFdeLyn/XL5Vihso=`

253 bytes for 20 items or about 12.6 bytes per item.

![Example Quickbar GUI](https://raw.githubusercontent.com/M45-Science/M45-Quickbar-Exchange/refs/heads/main/example-bar.png)

You can find the reference `quickbar.lua` implementation [here](https://github.com/M45-Science/SoftMod/blob/Main/quickbar.lua).

---

## Quality Aliases

Inventory quality is shortened using single-character codes:

| Alias | Meaning     |
|-------|-------------|
| `u`   | uncommon    |
| `r`   | rare        |
| `e`   | epic        |
| `l`   | legendary   |

Items with **normal** quality leave out this suffix.
Forward compatable: quality strings not in the table will simply pass-through unaltered.

---

## Format Summary

`M45-QB2=name/alias[:quality/alias],name/alias[:quality/alias],...`

- Quality is appended when != normal.
- Padding with commas extends up to 100 slots, to retain the quickbar position.

---

This string represents:
- `AA` – first item, normal quality  
- `AB:l` – second item, legendary  
- `AC:u` – third item, uncommon  
- `AD` – fourth, normal  
- `AE:r` – fifth, rare  
- Remaining slots are empty.

---

# Item list:

```accumulator, active-provider-chest, advanced-circuit, agricultural-science-pack, agricultural-tower, arithmetic-combinator, artificial-jellynut-soil, artificial-yumako-soil, artillery-shell, artillery-targeting-remote, artillery-turret, artillery-wagon, artillery-wagon-cannon, assembling-machine-1, assembling-machine-2, assembling-machine-3, asteroid-collector, atomic-bomb, automation-science-pack, barrel, battery, battery-equipment, battery-mk2-equipment, battery-mk3-equipment, beacon, belt-immunity-equipment, big-electric-pole, big-mining-drill, biochamber, bioflux, biolab, biter-egg, blueprint, blueprint-book, boiler, buffer-chest, bulk-inserter, burner-generator, burner-inserter, burner-mining-drill, calcite, cannon-shell, captive-biter-spawner, capture-robot-rocket, car, carbon, carbon-fiber, carbonic-asteroid-chunk, cargo-bay, cargo-landing-pad, cargo-wagon, centrifuge, chemical-plant, chemical-science-pack, cliff-explosives, cluster-grenade, coal, coin, combat-shotgun, concrete, constant-combinator, construction-robot, copper-bacteria, copper-cable, copper-ore, copper-plate, copper-wire, copy-paste-tool, crude-oil-barrel, crusher, cryogenic-plant, cryogenic-science-pack, cut-paste-tool, decider-combinator, deconstruction-planner, defender-capsule, depleted-uranium-fuel-cell, destroyer-capsule, discharge-defense-equipment, discharge-defense-remote, display-panel, distractor-capsule, efficiency-module, efficiency-module-2, efficiency-module-3, electric-energy-interface, electric-engine-unit, electric-furnace, electric-mining-drill, electromagnetic-plant, electromagnetic-science-pack, electronic-circuit, empty-module-slot, energy-shield-equipment, energy-shield-mk2-equipment, engine-unit, exoskeleton-equipment, explosive-cannon-shell, explosive-rocket, explosive-uranium-cannon-shell, explosives, express-loader, express-splitter, express-transport-belt, express-underground-belt, fast-inserter, fast-loader, fast-splitter, fast-transport-belt, fast-underground-belt, firearm-magazine, fission-reactor-equipment, flamethrower, flamethrower-ammo, flamethrower-turret, fluid-wagon, fluoroketone-cold-barrel, fluoroketone-hot-barrel, flying-robot-frame, foundation, foundry, fusion-generator, fusion-power-cell, fusion-reactor, fusion-reactor-equipment, gate, green-wire, grenade, gun-turret, hazard-concrete, heat-exchanger, heat-interface, heat-pipe, heating-tower, heavy-armor, heavy-oil-barrel, holmium-ore, holmium-plate, ice, ice-platform, infinity-cargo-wagon, infinity-chest, infinity-pipe, inserter, iron-bacteria, iron-chest, iron-gear-wheel, iron-ore, iron-plate, iron-stick, item-unknown, jelly, jellynut, jellynut-seed, lab, land-mine, landfill, lane-splitter, laser-turret, light-armor, light-oil-barrel, lightning-collector, lightning-rod, linked-belt, linked-chest, lithium, lithium-plate, loader, locomotive, logistic-robot, logistic-science-pack, long-handed-inserter, low-density-structure, lubricant-barrel, mech-armor, medium-electric-pole, metallic-asteroid-chunk, metallurgic-science-pack, military-science-pack, modular-armor, night-vision-equipment, nuclear-fuel, nuclear-reactor, nutrients, offshore-pump, oil-refinery, one-way-valve, overflow-valve, overgrowth-jellynut-soil, overgrowth-yumako-soil, oxide-asteroid-chunk, parameter-0, parameter-1, parameter-2, parameter-3, parameter-4, parameter-5, parameter-6, parameter-7, parameter-8, parameter-9, passive-provider-chest, pentapod-egg, personal-laser-defense-equipment, personal-roboport-equipment, personal-roboport-mk2-equipment, petroleum-gas-barrel, piercing-rounds-magazine, piercing-shotgun-shell, pipe, pipe-to-ground, pistol, plastic-bar, poison-capsule, power-armor, power-armor-mk2, power-switch, processing-unit, production-science-pack, productivity-module, productivity-module-2, productivity-module-3, programmable-speaker, promethium-asteroid-chunk, promethium-science-pack, proxy-container, pump, pumpjack, quality-module, quality-module-2, quality-module-3, quantum-processor, radar, rail, rail-chain-signal, rail-ramp, rail-signal, rail-support, railgun, railgun-ammo, railgun-turret, raw-fish, recycler, red-wire, refined-concrete, refined-hazard-concrete, repair-pack, requester-chest, roboport, rocket, rocket-fuel, rocket-launcher, rocket-part, rocket-silo, rocket-turret, science, scrap, selection-tool, selector-combinator, shotgun, shotgun-shell, simple-entity-with-force, simple-entity-with-owner, slowdown-capsule, small-electric-pole, small-lamp, solar-panel, solar-panel-equipment, solid-fuel, space-platform-foundation, space-platform-hub, space-platform-starter-pack, space-science-pack, speed-module, speed-module-2, speed-module-3, spidertron, spidertron-remote, spidertron-rocket-launcher-1, spidertron-rocket-launcher-2, spidertron-rocket-launcher-3, spidertron-rocket-launcher-4, splitter, spoilage, stack-inserter, steam-engine, steam-turbine, steel-chest, steel-furnace, steel-plate, stone, stone-brick, stone-furnace, stone-wall, storage-chest, storage-tank, submachine-gun, substation, sulfur, sulfuric-acid-barrel, supercapacitor, superconductor, tank, tank-cannon, tank-flamethrower, tank-machine-gun, tesla-ammo, tesla-turret, teslagun, thruster, toolbelt-equipment, top-up-valve, train-stop, transport-belt, tree-seed, tungsten-carbide, tungsten-ore, tungsten-plate, turbo-loader, turbo-splitter, turbo-transport-belt, turbo-underground-belt, underground-belt, upgrade-planner, uranium-235, uranium-238, uranium-cannon-shell, uranium-fuel-cell, uranium-ore, uranium-rounds-magazine, utility-science-pack, vehicle-machine-gun, water-barrel, wood, wooden-chest, yumako, yumako-mash, yumako-seed```

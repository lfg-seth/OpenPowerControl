Label: wayfinder:map
Status: open
Repository: OpenPowerControl

# Chart a build-ready Open Power Control system

## Destination

Reach an approved, build-ready system specification and repository plan for a dependable two-node accessory power-control system and adaptable cabin HMI in the 4Runner. The result must be detailed enough to implement, bench-test, install, diagnose, and maintain without rediscovering the hardware or safety model.

## Notes

- Scope covers the engine-bay PCM, rear-cargo PCM, the dedicated vehicle CAN bus, and the sunglass-area switch-panel HMI.
- The two PCMs use the same custom 26-output PCB and Adafruit RP2040 CAN Bus Feather (product 5724). Prefer one PCM firmware image with explicit, inspectable node identity if the hardware supports it.
- The HMI currently starts from twelve SPDT on-off-on switch positions, but its domain model and protocol must permit toggles, momentaries, rotary inputs, indicators, and small displays without recasting the whole system.
- Loads include ordinary accessories, air-compressor control, and programmable coordinated flashing of factory/external lights. Treat unintended activation, stuck outputs, loss of communications, brownout, reset, and conflicting commands as first-class safety cases.
- Existing `OpenControlHead` code is the latest behavioral reference. `SunglassSwitchPanel` is a secondary historical reference. Neither is presumed to be the final architecture.
- PlatformIO is the preferred build workflow unless a concrete constraint justifies changing it.
- Known BOM clues include 20 BTS7004-1EPP devices, 3 BV2HC045EFU devices, 2 PCA9535 expanders, 4 ADS7830 ADCs, an INA219, and a TC74. Connections and channel semantics are not yet authoritative.
- Use `grilling` and `domain-modeling` for human decisions, `research` for primary-source hardware/protocol facts, and `prototype` when behavior needs a concrete artifact to react to.
- This map plans the work. Implementation begins after its decision frontier is exhausted and the destination is reached.

## Decisions so far

<!-- Resolved ticket pointers are appended here; detail lives in each ticket. -->

- [Name the system and its boundaries](issues/01-name-the-system-and-its-boundaries.md): The platform is Open Power Control (OPC), its power nodes are OPCMs, and its canonical language separates physical channels, vehicle Functions, independent Function State and Level, HMI Controls, higher-level behaviors, and external vehicle systems.

## Not yet specified

- The exact electrical and logical channel map for each installed PCM, including connector positions, loads, sense paths, current limits, and any unused outputs.
- Whether safe operation of the installed PCB requires electrical rework or a future PCB revision after its actual schematic/connectivity is reconstructed.
- The final physical HMI layout, control types, legends, illumination, feedback devices, and enclosure constraints; these depend on the operator model and available panel wiring.
- The authoring and storage workflow for lighting patterns, including whether a desktop simulator/editor is worth retaining or replacing.
- How much factory-vehicle state should influence commands (ignition, engine running, gear, voltage, OEM CAN, and similar interlocks) after authority and safety boundaries are settled.
- Firmware update, rollback, service-mode, and field-diagnostic workflows after the deployment and fault models are known.
- Compliance constraints for emergency-warning-light use in the vehicle's operating jurisdictions and how those constraints affect available modes.

## Out of scope

- The retrofitted Motorola O9 / Raspberry Pi 4 control head is intentionally deferred to a separate future effort.

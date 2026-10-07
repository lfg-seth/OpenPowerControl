Type: grilling
Status: resolved
Blocked by: none
Map: ../map.md

# Name the system and its boundaries

## Question

What canonical vocabulary should the repository use for the custom power-control module, physical output channels, vehicle loads, logical functions, HMI controls, commands, scenes/macros, and flashing patterns—and where are the boundaries between this system, factory vehicle wiring, and future controllers?

This must explicitly address the automotive ambiguity of “PCM,” which commonly means the factory powertrain control module but here means the custom power control module.

## Comments

we can call it obcm open body control module

- Naming constraint from discussion: reject “body” terminology because the system is not intended to present itself as the vehicle's factory body-control domain.

- Decision: the overall platform is **Open Power Control (OPC)**, and each physical power-control module is an **Open Power Control Module (OPCM)**.

- Decision: the reusable repository will be named `OpenPowerControl`; “Clifford” identifies the 4Runner installation rather than the platform.

- Decision: adopt OPC System, OPC Node, OPC HMI, Switch Panel, OPC Bus, OPC Protocol, Output Channel, Input Channel, Load, Function, Control, Request, and Actual State with the physical/logical distinctions proposed in discussion.

- Decision: OPC owns the OPCMs, OPC Bus and Protocol, HMI, configuration, patterns, diagnostics, tooling, tests, and interface/install documentation. Factory modules, OEM CAN, original vehicle wiring, and attached Loads are external systems whose OPC connections are documented.

- Decision: a Function has an independent Active/Inactive Function State and may have a selected, ordered Function Level. A separate Control may select the Level, which can change timing, participating lights, Scene, or Pattern; Off is not Level 0.

- Decision: a Mode is a named non-ordered condition that may affect multiple Functions, a Scene is a static combination of Function states, a Pattern is timed behavior, and a Pattern Definition is its stored description. Retire “macro” as ambiguous.

## Answer

The reusable platform is **Open Power Control (OPC)**, and each physical power-control board is an **Open Power Control Module (OPCM)**. The reusable repository is named `OpenPowerControl`; “Clifford” identifies this 4Runner installation.

The canonical physical/logical vocabulary is recorded in `CONTEXT.md`. Most importantly, Output Channels are physical circuits, Loads are attached devices, Functions are operator-visible capabilities, and Controls are physical HMI inputs. HMIs express Requests in terms of Functions rather than raw channel numbers.

A Function has an independent Active/Inactive Function State and may expose an ordered Function Level. For example, one Control may activate Rear Warning while a separate three-position or rotary Control selects its Level. The selected Level can alter timing, participating lights, Scene, or Pattern and remains selected while the Function is inactive; Off is not Level 0.

OPC includes its OPCMs, HMI, dedicated OPC Bus and Protocol, configuration, behavior definitions, diagnostics, tooling, tests, and interface/install documentation. Toyota modules, OEM CAN, original vehicle wiring, and connected Loads remain external systems, even though every OPC connection to them is documented. The deferred O9 controller may later participate as an OPC Node without changing these boundaries.

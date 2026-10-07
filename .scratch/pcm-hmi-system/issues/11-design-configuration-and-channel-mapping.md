Type: grilling
Status: open
Blocked by: 03, 05, 06, 07
Map: ../map.md

# Design configuration and channel mapping

## Question

What is the single source of truth that maps node identity, PCB outputs, installed loads, electrical limits, logical vehicle functions, HMI controls, interlocks, and pattern participants—and which parts belong at compile time versus validated runtime configuration?

The model must prevent front/rear source duplication, channel-number confusion, invalid combinations, and silent deployment of a configuration to the wrong node. Decide schema, validation, versioning, defaults, generated artifacts, and human-readable documentation views.

## Comments

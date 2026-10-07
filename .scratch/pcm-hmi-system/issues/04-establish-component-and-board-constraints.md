Type: research
Status: open
Blocked by: none
Map: ../map.md

# Establish component and board constraints

## Question

Using only primary manufacturer documentation, what firmware-visible capabilities, limits, diagnostics, timing constraints, reset/default behavior, and safety-relevant caveats of the Adafruit RP2040 CAN Bus Feather and BOM components constrain the system design?

At minimum cover MCP2515/CAN transceiver behavior on the Adafruit board, BTS7004-1EPP, BV2HC045EFU, PCA9535, ADS7830, INA219, and TC74. Separate facts intrinsic to each component from facts that cannot be known without the missing PCB connectivity.

## Comments

- Research dispatched on branch `research/component-board-constraints`; expected report: `docs/research/component-and-board-constraints.md`.

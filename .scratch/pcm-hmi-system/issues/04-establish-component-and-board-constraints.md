Type: research
Status: resolved
Blocked by: none
Map: ../map.md

# Establish component and board constraints

## Question

Using only primary manufacturer documentation, what firmware-visible capabilities, limits, diagnostics, timing constraints, reset/default behavior, and safety-relevant caveats of the Adafruit RP2040 CAN Bus Feather and BOM components constrain the system design?

At minimum cover MCP2515/CAN transceiver behavior on the Adafruit board, BTS7004-1EPP, BV2HC045EFU, PCA9535, ADS7830, INA219, and TC74. Separate facts intrinsic to each component from facts that cannot be known without the missing PCB connectivity.

## Comments

- Research dispatched on branch `research/component-board-constraints`; expected report: `docs/research/component-and-board-constraints.md`.

- Research was migrated into `OpenPowerControl` as commit `1ec5fca`.

## Answer

The primary-source findings are captured in [Component and board constraints](../../../docs/research/component-and-board-constraints.md).

The Adafruit 5724 uses an MCP25625 classic-CAN controller/transceiver with a 16 MHz CAN crystal and an enabled-by-default 120-ohm terminator. The BOM supports the inference of 26 protected high-side outputs, 32 expander GPIOs, and 32 ADC inputs, but it cannot establish their connectivity.

The switch families require different firmware behavior: BTS7004 faults latch off and expose analog diagnostics, while the BV2HC045-C is a dual-channel off-latch device with separately programmed protection timing/current behavior. Safe initialization must be proven at the physical switch inputs; PCA9535 ports reset as inputs with output latches containing ones.

The I2C design needs reconstruction before firmware assumptions are safe. The fixed-address TC74 is limited to 100 kHz and uses address `0x48`, which may conflict with an ADS7830 or INA219 depending on their straps. Actual addresses, bus topology, sense scaling, pull states, protection programming, and all channel mappings remain PCB facts to recover in “Reconstruct the installed hardware.”

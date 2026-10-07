Type: grilling
Status: open
Blocked by: 02, 03
Map: ../map.md

# Decide node identity and deployment

## Question

How should identical PCM hardware determine and expose its stable identity as engine-bay or rear-cargo hardware, and how should one firmware artifact acquire node-specific configuration without creating an easy path to accidental duplicate IDs or wrong channel maps?

Compare a dedicated strap/input, RP2040 pin state, stored configuration, build-time environments, and commissioning-time assignment. Include behavior for invalid/ambiguous identity and service replacement.

## Comments

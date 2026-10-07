Type: prototype
Status: open
Blocked by: 05, 07, 08
Map: ../map.md

# Design the lighting-pattern model

## Question

What small, deterministic pattern model can express the required steady, alternating, simultaneous, phased, and coordinated multi-PCM lighting behaviors while remaining safe to interrupt and simple enough for RP2040 firmware?

Prototype representative current patterns and difficult transitions. Decide timing resolution, synchronization tolerance, looping, grouping, composition, priority, cancellation, safe stop behavior, storage/versioning, validation limits, and whether patterns are distributed to PCMs or referenced from firmware/configuration.

## Comments

Type: grilling
Status: open
Blocked by: 04, 06, 08, 10, 11
Map: ../map.md

# Design the firmware and repository architecture

## Question

What repository and firmware module boundaries make the shared PCM firmware, HMI firmware, protocol, board support, configuration, tests, tools, and documentation easy to navigate and hard to misuse?

Decide whether to evolve or replace the Arduino/PlatformIO code, how PlatformIO environments and shared libraries should be organized, how hardware dependencies are isolated, what can run in host-side tests, and how historical code from `OpenControlHead` and `SunglassSwitchPanel` is preserved or retired without becoming a second source of truth.

## Comments

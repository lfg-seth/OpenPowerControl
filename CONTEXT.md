# Open Power Control

<!-- Canonical domain glossary for the reusable platform. -->

Open Power Control is the shared language for the custom vehicle power-control platform. It distinguishes the platform and its modules from the 4Runner's factory electronic control systems.

## Language

**Open Power Control (OPC)**:
The overall custom power-control platform, encompassing its modules, operator interfaces, and dedicated communications network.
_Avoid_: Open Body Control, OBC, PCM

**Open Power Control Module (OPCM)**:
One physical OPC power-control module, such as the engine-bay or rear-cargo module.
_Avoid_: Open Body Control Module, OBCM, PCM

**OPC System**:
One complete installation of the OPC platform in a vehicle.
_Avoid_: OPCM, when referring to the installation as a whole

**OPC Node**:
A device that participates on an OPC Bus using the OPC Protocol.
_Avoid_: Module, when the device is not an OPCM

**OPC HMI**:
An OPC Node through which an operator observes or requests vehicle Functions.
_Avoid_: Switch Panel, when referring to the general interface role

**Switch Panel**:
The sunglass-area physical implementation of an OPC HMI.
_Avoid_: OPC HMI, when specifically identifying this hardware

**OPC Bus**:
The dedicated CAN network connecting OPC Nodes.
_Avoid_: Vehicle CAN, factory CAN

**OPC Protocol**:
The messages and behavioral contract used by OPC Nodes on the OPC Bus.
_Avoid_: CAN, when referring to OPC-specific message semantics

**Output Channel**:
One physical protected power-output circuit on an OPCM.
_Avoid_: Function, load

**Input Channel**:
One physical sensed-input circuit belonging to an OPC Node.
_Avoid_: Control, function

**Load**:
A physical electrical device powered or switched by an Output Channel.
_Avoid_: Channel, function

**Function**:
An operator-visible vehicle capability independent of the physical channels that realize it.
_Avoid_: Channel, switch

**Function State**:
Whether a Function is Active or Inactive, independent of any selected Function Level.
_Avoid_: On/off Level, Level 0

**Function Level**:
An optional ordered behavioral selection within a Function that remains meaningful independently of whether the Function is Active.
_Avoid_: Mode, intensity when the choice can also change participating lights or behavior

**Control**:
A physical operator-input device such as a toggle, momentary button, or rotary encoder.
_Avoid_: Function, switch when referring to non-switch inputs

**Request**:
An OPC Node's expression of desired Function state.
_Avoid_: Command, until command authority is defined

**Actual State**:
The observed state reported by the OPC Node responsible for realizing a Function or channel.
_Avoid_: Requested state

**Mode**:
A named, non-ordered operating condition that may affect multiple Functions.
_Avoid_: Function Level

**Scene**:
A static combination of Function states.
_Avoid_: Pattern, macro

**Pattern**:
Timed behavior used to vary one or more Function states.
_Avoid_: Scene, macro

**Pattern Definition**:
The stored description from which a Pattern is executed.
_Avoid_: Pattern, when specifically referring to its configuration rather than its execution

## System Boundary

**Clifford Installation**:
The OPC System installed in the 4Runner, including its connection records for external vehicle circuits and Loads.
_Avoid_: Open Power Control, when referring only to this vehicle-specific installation

**External Vehicle System**:
A factory module, OEM CAN network, original vehicle circuit, or connected Load that OPC interfaces with but does not own.
_Avoid_: OPC Node, unless an explicit OPC gateway represents it

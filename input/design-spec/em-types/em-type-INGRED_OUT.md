# EM TYPE: INGRED_OUT

- Comment: 
- RoutingIn: true
- RoutingOut: false

## Instances and States

|  |  |  |  | TransferPump | Level | LowLevel | BottomValve |
|---|---|---|---|---|---|---|---|
|  |  |  | Comment | Transfer Pump | Level | Low Level detection | Bottom Valve |
|  |  |  | ModuleType | CM | CM | CM | CM |
|  |  |  | Name | TransferPump | Level | LowLevel | BottomValve |
|  |  |  | Type | ReversingMotor | AnalogMeasurement | DigitalMeasurement | SolenoidValve |
|  |  |  | EM Instances |  |  |  |  |
|  |  |  | INGRED_OUT_1 | P4711 | PT4712_01 | HV4750_01 | XV-001 |
|  |  |  | EM States |  |  |  |  |
| Src | Dest | # | State |  |  |  |  |
| 0 |  | 0 | Idle |  |  |  |  |
| 0 |  | 1 | PumpOut | forward |  |  | open |
| 0 |  | 2 | OpenValves |  |  |  | open |

## Setpoints

| Name | Suffix | DataType | Comment |
|------|--------|----------|---------|
| Source | _SRC | Int | Allows selecting the state based on the connected source equipment |
| Request | _REQ | Int | ID from the Phase Instance for Acquiring this EM |
| Destination | _DEST | Int | Allows selecting the state based on the connected destination equipment |

## Process Values

| Name | Suffix | DataType | Comment | Link |
|------|--------|----------|---------|------|
| Id | _ID | Int | ID of this EM instance. Can be used for example to change the route in other EM's |  |
| Level | _LEV | Real | Level of the tote or ingredient tank | Level.rOutEngUnitsValue |
| Owner | _OWN | Int | ID from the Phase Instance that has acquired and is now owning this EM |  |
| LowLevel | _L | Bool | Low level of the tote or ingredient tank | Level.bOutLow |

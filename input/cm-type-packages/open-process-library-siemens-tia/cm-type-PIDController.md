# CM TYPE: PIDController

- dexpi-mapping: PidController
- mtp-mapping: PIDCtrl

## Inputs
| Name                 | Suffix             | DataType | IO Type | Comment                                                       | Primary | IsError | Configurable | True Words        | False Words | Loopback | Enum | 
| -------------------- | ------------------ | -------- | ------- | ------------------------------------------------------------- | ------- | ------- | ------------ | ----------------- | ----------- | -------- | ---- | 
| id                   |                    | Int      |         | unique project-wide ID to uniquely identify and track objects | False   | False   | True         |                   |             |          |      | 
| activateManualSP     | .activateManualSP  | Bool     |         | Activates Fixed Manual Setpoint                               | False   | False   | False        | activateManualSP  |             |          |      | 
| activateDynamicSP    | .activateDynamicSP | Bool     |         | Activates Internal Dynamic Setpoint                           | False   | False   | False        | activateDynamicSP |             |          |      | 
| activateFixedSP      | .activateFixedSP   | Bool     |         | Activates Internal Fixed Setpoint                             | False   | False   | False        | activateFixedSP   |             |          |      | 
| fixedSP              | .fixedSP           | Real     |         | Fixed Setpoint from Program                                   | False   | False   | False        |                   |             |          |      | 
| rawValue             | .rawValue          | AI       |         | Raw Input Value                                               | False   | False   | False        |                   |             |          |      | 
| valueUnit            |                    | Int      |         | Value Unit                                                    | False   | False   | True         |                   |             |          |      | 
| manipulatedValueUnit |                    | Int      |         | Manipulated Value Unit                                        | False   | False   | True         |                   |             |          |      | 
| scaleMin             |                    | Real     |         | Scale Min for read value                                      | False   | False   | True         |                   |             |          |      | 
| scaleMax             |                    | Real     |         | Scale Max for read value                                      | False   | False   | True         |                   |             |          |      | 
| scaleMinMV           |                    | Real     |         | Scale Min for Manipulated Value                               | False   | False   | True         |                   |             |          |      | 
| scaleMaxMV           |                    | Real     |         | Scale Max for Manipulated Value                               | False   | False   | True         |                   |             |          |      | 
| proportional         |                    | Real     |         | Proportional Parameter                                        | False   | False   | True         |                   |             |          |      | 
| integration          |                    | Real     |         | Integration Parameter in s                                    | False   | False   | True         |                   |             |          |      | 
| derivation           |                    | Real     |         | Derivation Parameter in s                                     | False   | False   | True         |                   |             |          |      | 
| alarmHigh            |                    | Real     |         | Limit Value for Alarm High                                    | False   | False   | True         |                   |             |          |      | 
| warningHigh          |                    | Real     |         | Limit Value for Warning High                                  | False   | False   | True         |                   |             |          |      | 
| toleranceHigh        |                    | Real     |         | Limit Value for Tolerance High                                | False   | False   | True         |                   |             |          |      | 
| toleranceLow         |                    | Real     |         | Limit Value for Tolerance Low                                 | False   | False   | True         |                   |             |          |      | 
| warningLow           |                    | Real     |         | Limit Value for Warning Low                                   | False   | False   | True         |                   |             |          |      | 
| alarmLow             |                    | Real     |         | Limit Value for Alarm Low                                     | False   | False   | True         |                   |             |          |      | 
| alarmHighEn          |                    | Bool     |         | Alarm High Limit Enabled                                      | False   | False   | True         |                   |             |          |      | 
| warningHighEn        |                    | Bool     |         | Warning High Limit Enabled                                    | False   | False   | True         |                   |             |          |      | 
| toleranceHighEn      |                    | Bool     |         | Tolerance High Limit Enabled                                  | False   | False   | True         |                   |             |          |      | 
| toleranceLowEn       |                    | Bool     |         | Tolerance Low Limit Enabled                                   | False   | False   | True         |                   |             |          |      | 
| warningLowEn         |                    | Bool     |         | Warning Low Limit Enabled                                     | False   | False   | True         |                   |             |          |      | 
| alarmLowEn           |                    | Bool     |         | Alarm Low Limit Enabled                                       | False   | False   | True         |                   |             |          |      | 
| deadband             |                    | Real     |         | Deadband for alarms/warnings                                  | False   | False   | True         |                   |             |          |      | 
| externalFault        | .externalFault     | Bool     |         | Fault indication from outside                                 | False   | False   | False        |                   |             |          |      | 


## Outputs
| Name                | Suffix               | DataType | IO Type | Comment                                | Primary | IsError | Configurable | True Words | False Words | Loopback | Enum | 
| ------------------- | -------------------- | -------- | ------- | -------------------------------------- | ------- | ------- | ------------ | ---------- | ----------- | -------- | ---- | 
| setpointOut         | .setpointOut         | Real     |         | Active setpoint                        | False   | False   | False        |            |             |          |      | 
| valueOut            | .valueOut            | Real     |         | input Value for use in the program     | True    | False   | False        |            |             |          |      | 
| manipulatedValue    | .manipulatedValue    | Real     |         | manipulated value                      | False   | False   | False        |            |             |          |      | 
| remote              | .remote              | Bool     |         | 0: operator/local, 1: automatic/remote | False   | False   | False        |            |             |          |      | 
| operator            | .operator            | Bool     |         | Operator Mode                          | False   | False   | False        |            |             |          |      | 
| automatic           | .automatic           | Bool     |         | Automatic Mode                         | False   | False   | False        |            |             |          |      | 
| offline             | .offline             | Bool     |         | Offline Mode                           | False   | False   | False        |            |             |          |      | 
| error               | .error               | Bool     |         | Any error active                       | False   | True    | False        |            |             |          |      | 
| alarmHighStatus     | .alarmHighStatus     | Bool     |         | Alarm High Limit Active                | False   | False   | False        |            |             |          |      | 
| warningHighStatus   | .warningHighStatus   | Bool     |         | Warning High Limit Active              | False   | False   | False        |            |             |          |      | 
| toleranceHighStatus | .toleranceHighStatus | Bool     |         | Tolerance High Limit Active            | False   | False   | False        |            |             |          |      | 
| toleranceLowStatus  | .toleranceLowStatus  | Bool     |         | Tolerance Low Limit Active             | False   | False   | False        |            |             |          |      | 
| warningLowStatus    | .warningLowStatus    | Bool     |         | Warning Low Limit Active               | False   | False   | False        |            |             |          |      | 
| alarmLowStatus      | .alarmLowStatus      | Bool     |         | Alarm Low Limit Active                 | False   | False   | False        |            |             |          |      | 
| remoteSource        | .remoteSource        | Bool     |         | 0: operator/local, 1: automatic/remote | False   | False   | False        |            |             |          |      | 
| internalSourceAct   | .internalSourceAct   | Bool     |         |                                        | False   | False   | False        |            |             |          |      | 
| manualSourceAct     | .manualSourceAct     | Bool     |         |                                        | False   | False   | False        |            |             |          |      | 


## InOuts

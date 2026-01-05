# CM TYPE: SolenoidValve

- dexpi-mapping: 
- mtp-mapping: MonBinVlv

## Inputs
| Name           | Suffix          | DataType | IO Type | Comment                                                                   | Primary | IsError | Configurable | True Words | False Words | Loopback | Enum | 
| -------------- | --------------- | -------- | ------- | ------------------------------------------------------------------------- | ------- | ------- | ------------ | ---------- | ----------- | -------- | ---- | 
| id             | _ID             | Int      |         | unique project-wide ID to uniquely identify and track objects             | False   | False   | True         |            |             |          |      | 
| open           | .open           | Bool     |         | open command from PLC program                                             | False   | False   | False        | open       | close       |          |      | 
| outsideOpen    | .outsideOpen    | Bool     |         | open command from local panel                                             | False   | False   | False        |            |             |          |      | 
| outsideClose   | .outsideClose   | Bool     |         | close command from local panel                                            | False   | False   | False        |            |             |          |      | 
| feedbackOpen   | .feedbackOpen   | DI       |         | feedback open                                                             | False   | False   | False        |            |             |          |      | 
| feedbackClose  | .feedbackClose  | DI       |         | feedback close                                                            | False   | False   | False        |            |             |          |      | 
| hasFbOpen      |                 | Bool     |         | has open feedback                                                         | False   | False   | True         |            |             |          |      | 
| hasFbClose     |                 | Bool     |         | hase close feedback                                                       | False   | False   | True         |            |             |          |      | 
| safeOpen       |                 | Bool     |         | Safe Position is Open                                                     | False   | False   | True         |            |             |          |      | 
| safeHold       |                 | Bool     |         | Holds Position on interlock (priority over safeOpen)                      | False   | False   | True         |            |             |          |      | 
| monitor        |                 | Bool     |         | Enables errors on the feedback monitoring                                 | False   | False   | True         |            |             |          |      | 
| staticTimeout  |                 | Real     |         | Amount of time before a static monitoring error is triggered              | False   | False   | True         |            |             |          |      | 
| dynamicTimeout |                 | Real     |         | Amount of time before a dynamic monitoring error is triggered             | False   | False   | True         |            |             |          |      | 
| simulateDelay  |                 | Real     |         | Simulated delay to set the feedback signals, in s                         | False   | False   | True         |            |             |          |      | 
| interlockIn    | .interlockIn    | Bool     |         | forces safe position. 0 = interlock active                                | False   | False   | False        |            |             |          |      | 
| permitIn       | .permitIn       | Bool     |         | permission to control. Does not activate safe position. 0 = no permission | False   | False   | False        |            |             |          |      | 
| protectIn      | .protectIn      | Bool     |         | Protect, sets safe position, sets protectState. 0 = Protect active        | False   | False   | False        |            |             |          |      | 
| reset          | .reset          | Bool     |         | will try to reset itself                                                  | False   | False   | False        |            |             |          |      | 
| externalFault  | .externalFault  | Bool     |         | Loop failure-e.g. I/O card broken.                                        | False   | False   | False        |            |             |          |      | 
| surpressAlarms | .surpressAlarms | Bool     |         | surpresses alarms                                                         | False   | False   | False        |            |             |          |      | 
| setAuto        | .setAuto        | Bool     |         | sets auto mode                                                            | False   | False   | False        |            |             |          |      | 
| setManual      | .setManual      | Bool     |         | sets manual mode                                                          | False   | False   | False        |            |             |          |      | 
| setOutside     | .setOutside     | Bool     |         | sets outside mode                                                         | False   | False   | False        |            |             |          |      | 


## Outputs
| Name          | Suffix         | DataType | IO Type | Comment                                    | Primary | IsError | Configurable | True Words | False Words | Loopback | Enum | 
| ------------- | -------------- | -------- | ------- | ------------------------------------------ | ------- | ------- | ------------ | ---------- | ----------- | -------- | ---- | 
| openCommand   | .openCommand   | DO       |         | open command to device                     | False   | False   | False        |            |             |          |      | 
| pulseOpen     | .pulseOpen     | Bool     |         | one cycle pulse when starting open command | False   | False   | False        |            |             |          |      | 
| pulseClose    | .pulseClose    | Bool     |         | one cycle pulse when ending open command   | False   | False   | False        |            |             |          |      | 
| remote        | .remote        | Bool     |         | 0: operator/local, 1: automatic/remote     | False   | False   | False        |            |             |          |      | 
| operatorMode  | .operatorMode  | Bool     |         | Operator Mode                              | False   | False   | False        |            |             |          |      | 
| automaticMode | .automaticMode | Bool     |         | Automatic Mode                             | False   | False   | False        |            |             |          |      | 
| offlineMode   | .offlineMode   | Bool     |         | Offline Mode                               | False   | False   | False        |            |             |          |      | 
| outside       | .outside       | Bool     |         | Outside mode                               | False   | False   | False        |            |             |          |      | 
| error         | .error         | Bool     |         | Any error active                           | False   | False   | False        |            |             |          |      | 
| opened        | .opened        | Bool     |         | Valve is opened                            | False   | False   | False        | opened     |             |          |      | 
| closed        | .closed        | Bool     |         | Valve is closed                            | False   | False   | False        | closed     |             |          |      | 
| forceActive   | .forceActive   | Bool     |         | Any forcing or safeguarding active         | False   | False   | False        |            |             |          |      | 
| surpressed    | .surpressed    | Bool     |         | alarms surpressed                          | False   | False   | False        |            |             |          |      | 


## InOuts

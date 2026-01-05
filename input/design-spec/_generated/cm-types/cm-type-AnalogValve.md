# CM TYPE: AnalogValve

- dexpi-mapping: ControlValve
- mtp-mapping: MonAnaVlv

## Inputs
| Name                  | Suffix                 | DataType | IO Type | Comment                                                                   | Primary | IsError | Configurable | True Words            | False Words | Loopback | Enum | 
| --------------------- | ---------------------- | -------- | ------- | ------------------------------------------------------------------------- | ------- | ------- | ------------ | --------------------- | ----------- | -------- | ---- | 
| id                    |                        | Int      |         | unique project-wide ID to uniquely identify and track objects             | False   | False   | True         |                       |             |          |      | 
| activateManualSource  | .activateManualSource  | Bool     |         | activate manual source                                                    | False   | False   | False        | activateManualSource  |             |          |      | 
| activateDynamicSource | .activateDynamicSource | Bool     |         | activate dynamic program source                                           | False   | False   | False        | activateDynamicSource |             |          |      | 
| activateFixedSource   | .activateFixedSource   | Bool     |         | activate fixed program source                                             | False   | False   | False        | activateFixedSource   |             |          |      | 
| fixedSource           | .fixedSource           | Real     |         | Fixed source from program                                                 | True    | False   | False        |                       |             |          |      | 
| feedbackPosition      | .feedbackPosition      | AI       |         | Position feedback (0-100%)                                                | False   | False   | False        |                       |             |          |      | 
| scaleMin              |                        | Real     |         | Position scale min                                                        | False   | False   | True         |                       |             |          |      | 
| scaleMax              |                        | Real     |         | Position scale max                                                        | False   | False   | True         |                       |             |          |      | 
| feedbackOpen          | .feedbackOpen          | DI       |         | feedback open                                                             | False   | False   | False        |                       |             |          |      | 
| feedbackClose         | .feedbackClose         | DI       |         | feedback close                                                            | False   | False   | False        |                       |             |          |      | 
| hasFbOpen             |                        | Bool     |         | has open feedback                                                         | False   | False   | True         |                       |             |          |      | 
| hasFbClose            |                        | Bool     |         | hase close feedback                                                       | False   | False   | True         |                       |             |          |      | 
| safeOpen              |                        | Bool     |         | Safe Position is Open                                                     | False   | False   | True         |                       |             |          |      | 
| safeHold              |                        | Bool     |         | Holds Position on interlock (priority over safeOpen)                      | False   | False   | True         |                       |             |          |      | 
| simulateDelay         |                        | Real     |         | Simulated delay to set the feedback signals, in s                         | False   | False   | True         |                       |             |          |      | 
| interlockIn           | .interlockIn           | Bool     |         | forces safe position. 0 = interlock active                                | False   | False   | False        |                       |             |          |      | 
| permitIn              | .permitIn              | Bool     |         | permission to control. Does not activate safe position. 0 = no permission | False   | False   | False        |                       |             |          |      | 
| protectIn             | .protectIn             | Bool     |         | Protect, sets safe position, sets protectState. 0 = Protect active        | False   | False   | False        |                       |             |          |      | 
| reset                 | .reset                 | Bool     |         | will try to reset itself                                                  | False   | False   | False        |                       |             |          |      | 


## Outputs
| Name              | Suffix             | DataType | IO Type | Comment                                | Primary | IsError | Configurable | True Words | False Words | Loopback | Enum | 
| ----------------- | ------------------ | -------- | ------- | -------------------------------------- | ------- | ------- | ------------ | ---------- | ----------- | -------- | ---- | 
| positionOutDevice | .positionOutDevice | AO       |         | Command to device (0-100%)             | False   | False   | False        |            |             |          |      | 
| positionOut       | .positionOut       | Real     |         | Position Command for use in program    | False   | False   | False        |            |             |          |      | 
| remote            | .remote            | Bool     |         | 0: operator/local, 1: automatic/remote | False   | False   | False        |            |             |          |      | 
| operator          | .operator          | Bool     |         | Operator Mode                          | False   | False   | False        |            |             |          |      | 
| automatic         | .automatic         | Bool     |         | Automatic Mode                         | False   | False   | False        |            |             |          |      | 
| offline           | .offline           | Bool     |         | Offline Mode                           | False   | False   | False        |            |             |          |      | 
| error             | .error             | Bool     |         | Any error active                       | False   | True    | False        |            |             |          |      | 
| opened            | .opened            | Bool     |         | Valve is opened                        | False   | False   | False        | opened     |             |          |      | 
| closed            | .closed            | Bool     |         | Valve is closed                        | False   | False   | False        | closed     |             |          |      | 
| remoteSource      | .remoteSource      | Bool     |         | 0: operator/local, 1: automatic/remote | False   | False   | False        |            |             |          |      | 
| internalSourceAct | .internalSourceAct | Bool     |         |                                        | False   | False   | False        |            |             |          |      | 
| manualSourceAct   | .manualSourceAct   | Bool     |         |                                        | False   | False   | False        |            |             |          |      | 


## InOuts

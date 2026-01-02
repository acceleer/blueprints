# CM TYPE: VFD

- dexpi-mapping: 
- mtp-mapping: MonAnaDrv

## Inputs
| Name            | Suffix           | DataType | IO Type | Comment                                                                   | Primary | IsError | Configurable | True Words     | False Words | Loopback | Enum | 
| --------------- | ---------------- | -------- | ------- | ------------------------------------------------------------------------- | ------- | ------- | ------------ | -------------- | ----------- | -------- | ---- | 
| id              |                  | Int      |         | unique project-wide ID to uniquely identify and track objects             | False   | False   | True         |                |             |          |      | 
| forward         | .forward         | Bool     |         | Forward command from program                                              | False   | False   | False        | start, forward | stop        |          |      | 
| reverse         | .reverse         | Bool     |         | Reverse command from program                                              | False   | False   | False        | reverse        | stop        |          |      | 
| speed           | .speed           | Real     |         | Speed command from program                                                | False   | False   | False        |                |             |          |      | 
| speedUnit       |                  | Int      |         | Speed Unit (%, RPM, ...)                                                  | False   | False   | True         |                |             |          |      | 
| speedMin        |                  | Real     |         | Speed Min                                                                 | False   | False   | True         |                |             |          |      | 
| speedMax        |                  | Real     |         | Speed Max                                                                 | False   | False   | True         |                |             |          |      | 
| forwardFeedback | .forwardFeedback | DI       |         | Forward feedback signal from device                                       | False   | False   | False        |                |             |          |      | 
| reverseFeedback | .reverseFeedback | DI       |         | Reverse feedback signal from device                                       | False   | False   | False        |                |             |          |      | 
| speedFeedback   | .speedFeedback   | AI       |         | Speed feedback                                                            | False   | False   | False        |                |             |          |      | 
| speedScaleMin   |                  | Real     |         | Speed scale min                                                           | False   | False   | True         |                |             |          |      | 
| speedScaleMax   |                  | Real     |         | Speed scale max                                                           | False   | False   | True         |                |             |          |      | 
| hasFwdFeedback  |                  | Bool     |         | Has forward feedback                                                      | False   | False   | True         |                |             |          |      | 
| hasRevFeedback  |                  | Bool     |         | Has reverse feedback                                                      | False   | False   | True         |                |             |          |      | 
| enableForward   |                  | Bool     |         | Enable Forward                                                            | False   | False   | True         |                |             |          |      | 
| enableReverse   |                  | Bool     |         | Enable Reverse                                                            | False   | False   | True         |                |             |          |      | 
| trip            | .trip            | Bool     |         | Drive Protection Indicator. 0: tripped, 1: no error                       | False   | False   | False        |                |             |          |      | 
| safeHold        |                  | Bool     |         | Holds Energize on interlock                                               | False   | False   | True         |                |             |          |      | 
| monitor         |                  | Bool     |         | Enables errors on the feedback monitoring                                 | False   | False   | True         |                |             |          |      | 
| staticTimeout   |                  | Real     |         | Amount of time before a static monitoring error is triggered              | False   | False   | True         |                |             |          |      | 
| dynamicTimeout  |                  | Real     |         | Amount of time before a dynamic monitoring error is triggered             | False   | False   | True         |                |             |          |      | 
| simulateDelay   |                  | Real     |         | Simulated delay to set the feedback signals, in s                         | False   | False   | True         |                |             |          |      | 
| interlockIn     | .interlockIn     | Bool     |         | forces safe position. 0 = interlock active                                | False   | False   | False        |                |             |          |      | 
| permitIn        | .permitIn        | Bool     |         | permission to control. Does not activate safe position. 0 = no permission | False   | False   | False        |                |             |          |      | 
| protectIn       | .protectIn       | Bool     |         | Protect, sets safe position, sets protectState. 0 = Protect active        | False   | False   | False        |                |             |          |      | 
| reset           | .reset           | Bool     |         | will try to reset itself                                                  | False   | False   | False        |                |             |          |      | 


## Outputs
| Name              | Suffix             | DataType | IO Type | Comment                                | Primary | IsError | Configurable | True Words              | False Words | Loopback | Enum | 
| ----------------- | ------------------ | -------- | ------- | -------------------------------------- | ------- | ------- | ------------ | ----------------------- | ----------- | -------- | ---- | 
| fwdCommand        | .fwdCommand        | Bool     |         | Forward command to device              | False   | False   | False        |                         |             |          |      | 
| revCommand        | .revCommand        | Bool     |         | Reverse command to device              | False   | False   | False        |                         |             |          |      | 
| forwardActive     | .forwardActive     | Bool     |         | Motor running forward                  | False   | False   | False        | running, runningForward |             |          |      | 
| reverseActive     | .reverseActive     | Bool     |         | Motor running reverse                  | False   | False   | False        | runningReverse          |             |          |      | 
| actualSpeed       | .actualSpeed       | Real     |         | Actual motor speed                     | False   | False   | False        |                         |             |          |      | 
| remote            | .remote            | Bool     |         | 0: operator/local, 1: automatic/remote | False   | False   | False        |                         |             |          |      | 
| operator          | .operator          | Bool     |         | Operator Mode                          | False   | False   | False        |                         |             |          |      | 
| automatic         | .automatic         | Bool     |         | Automatic Mode                         | False   | False   | False        |                         |             |          |      | 
| offline           | .offline           | Bool     |         | Offline Mode                           | False   | False   | False        |                         |             |          |      | 
| remoteSource      | .remoteSource      | Bool     |         | 0: operator/local, 1: automatic/remote | False   | False   | False        |                         |             |          |      | 
| internalSourceAct | .internalSourceAct | Bool     |         |                                        | False   | False   | False        |                         |             |          |      | 
| manualSourceAct   | .manualSourceAct   | Bool     |         |                                        | False   | False   | False        |                         |             |          |      | 


## InOuts

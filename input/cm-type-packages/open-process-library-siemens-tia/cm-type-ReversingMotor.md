# CM TYPE: ReversingMotor

## Inputs
| Name            | Suffix           | DataType | IO Type | Comment                                                                   | Primary | IsError | Configurable | True Words     | False Words | Loopback | Enum | 
| --------------- | ---------------- | -------- | ------- | ------------------------------------------------------------------------- | ------- | ------- | ------------ | -------------- | ----------- | -------- | ---- | 
| id              |                  | Int      |         | unique project-wide ID to uniquely identify and track objects             | False   | False   | True         |                |             |          |      | 
| forward         | .forward         | Bool     |         | Forward command from program                                              | False   | False   | False        | start, forward | stop        |          |      | 
| reverse         | .reverse         | Bool     |         | Reverse command from program                                              | False   | False   | False        | reverse        | stop        |          |      | 
| forwardFeedback | .forwardFeedback | DI       |         | Forward feedback signal from device                                       | False   | False   | False        |                |             |          |      | 
| reverseFeedback | .reverseFeedback | DI       |         | Reverse feedback signal from device                                       | False   | False   | False        |                |             |          |      | 
| hasFwdFeedback  |                  | Bool     |         | Has forward feedback                                                      | False   | False   | True         |                |             |          |      | 
| hasRevFeedback  |                  | Bool     |         | Has reverse feedback                                                      | False   | False   | True         |                |             |          |      | 
| enableForward   |                  | Bool     |         | Enable Forward                                                            | False   | False   | True         |                |             |          |      | 
| enableReverse   |                  | Bool     |         | Enable Reverse                                                            | False   | False   | True         |                |             |          |      | 
| driveTrip       | .driveTrip       | Bool     |         | Drive Protection Indicator. 0: tripped, 1: no error                       | False   | False   | False        |                |             |          |      | 
| safeHold        |                  | Bool     |         | Holds Energize on interlock                                               | False   | False   | True         |                |             |          |      | 
| monitor         |                  | Bool     |         | Enables errors on the feedback monitoring                                 | False   | False   | True         |                |             |          |      | 
| staticTimeout   |                  | Real     |         | Amount of time before a static monitoring error is triggered              | False   | False   | True         |                |             |          |      | 
| dynamicTimeout  |                  | Real     |         | Amount of time before a dynamic monitoring error is triggered             | False   | False   | True         |                |             |          |      | 
| simulateDelay   |                  | Bool     |         | Simulated delay to set the feedback signals, in s                         | False   | False   | True         |                |             |          |      | 
| interlockIn     | .interlockIn     | Bool     |         | forces safe position. 0 = interlock active                                | False   | False   | False        |                |             |          |      | 
| permitIn        | .permitIn        | Bool     |         | permission to control. Does not activate safe position. 0 = no permission | False   | False   | False        |                |             |          |      | 
| protectIn       | .protectIn       | Bool     |         | Protect, sets safe position, sets protectState. 0 = Protect active        | False   | False   | False        |                |             |          |      | 
| reset           | .reset           | Bool     |         | will try to reset itself                                                  | False   | False   | False        |                |             |          |      | 


## Outputs
| Name          | Suffix         | DataType | IO Type | Comment                   | Primary | IsError | Configurable | True Words             | False Words | Loopback | Enum | 
| ------------- | -------------- | -------- | ------- | ------------------------- | ------- | ------- | ------------ | ---------------------- | ----------- | -------- | ---- | 
| fwdCommand    | .fwdCommand    | DO       |         | Forward command to device | False   | False   | False        |                        |             |          |      | 
| revCommand    | .revCommand    | DO       |         | Reverse command to device | False   | False   | False        |                        |             |          |      | 
| forwardActive | .forwardActive | Bool     |         | Motor running forward     | False   | False   | False        | running, forwardActive |             |          |      | 
| reverseActive | .reverseActive | Bool     |         | Motor running reverse     | False   | False   | False        | reverseActive          |             |          |      | 
| stopped       | .stopped       | Bool     |         | Motor stopped             | False   | False   | False        | stopped                |             |          |      | 


## InOuts

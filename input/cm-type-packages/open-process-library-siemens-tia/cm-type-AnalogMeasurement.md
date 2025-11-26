# CM TYPE: AnalogMeasurement

## Inputs
| Name            | Suffix    | DataType | IO Type | Comment                                                       | Primary | IsError | Configurable | True Words | False Words | Loopback | Enum | 
| --------------- | --------- | -------- | ------- | ------------------------------------------------------------- | ------- | ------- | ------------ | ---------- | ----------- | -------- | ---- | 
| id              | _ID       | Int      |         | unique project-wide ID to uniquely identify and track objects | False   | False   | True         |            |             |          |      | 
| rawValue        | .rawValue | AI       |         | Raw Input Value                                               | False   | False   | False        |            |             |          |      | 
| valueUnit       | _VU       | Int      |         | Value Unit                                                    | False   | False   | True         |            |             |          |      | 
| scaleMin        | _ScMin    | Real     |         | Scale Min Limit                                               | False   | False   | True         |            |             |          |      | 
| scaleMax        | _ScMax    | Real     |         | Scale Max Limit                                               | False   | False   | True         |            |             |          |      | 
| alarmHigh       |           | Real     |         | Limit Value for Alarm High                                    | False   | False   | True         |            |             |          |      | 
| warningHigh     |           | Real     |         | Limit Value for Warning High                                  | False   | False   | True         |            |             |          |      | 
| toleranceHigh   |           | Real     |         | Limit Value for Tolerance High                                | False   | False   | True         |            |             |          |      | 
| toleranceLow    |           | Real     |         | Limit Value for Tolerance Low                                 | False   | False   | True         |            |             |          |      | 
| warningLow      |           | Real     |         | Limit Value for Warning Low                                   | False   | False   | True         |            |             |          |      | 
| alarmLow        |           | Real     |         | Limit Value for Alarm Low                                     | False   | False   | True         |            |             |          |      | 
| alarmHighEn     | _AHEn     | Bool     |         | Alarm High Limit Enabled                                      | False   | False   | True         |            |             |          |      | 
| warningHighEn   | _WHEn     | Bool     |         | Warning High Limit Enabled                                    | False   | False   | True         |            |             |          |      | 
| toleranceHighEn | _THEn     | Bool     |         | Tolerance High Limit Enabled                                  | False   | False   | True         |            |             |          |      | 
| toleranceLowEn  | _TLEn     | Bool     |         | Tolerance Low Limit Enabled                                   | False   | False   | True         |            |             |          |      | 
| warningLowEn    | _WLEn     | Bool     |         | Warning Low Limit Enabled                                     | False   | False   | True         |            |             |          |      | 
| alarmLowEn      | _ALEn     | Bool     |         | Alarm Low Limit Enabled                                       | False   | False   | True         |            |             |          |      | 
| deadband        |           | Real     |         | Deadband for alarms/warnings                                  | False   | False   | True         |            |             |          |      | 


## Outputs
| Name                | Suffix               | DataType | IO Type | Comment                     | Primary | IsError | Configurable | True Words | False Words | Loopback | Enum | 
| ------------------- | -------------------- | -------- | ------- | --------------------------- | ------- | ------- | ------------ | ---------- | ----------- | -------- | ---- | 
| vOut                | .vOut                | Real     |         | Value                       | True    | False   | False        |            |             |          |      | 
| error               | .error               | Bool     |         | Any error active            | False   | True    | False        |            |             |          |      | 
| alarmHighStatus     | .alarmHighStatus     | Bool     |         | Alarm High Limit Active     | False   | False   | False        |            |             |          |      | 
| warningHighStatus   | .warningHighStatus   | Bool     |         | Warning High Limit Active   | False   | False   | False        |            |             |          |      | 
| toleranceHighStatus | .toleranceHighStatus | Bool     |         | Tolerance High Limit Active | False   | False   | False        |            |             |          |      | 
| toleranceLowStatus  | .toleranceLowStatus  | Bool     |         | Tolerance Low Limit Active  | False   | False   | False        |            |             |          |      | 
| warningLowStatus    | .warningLowStatus    | Bool     |         | Warning Low Limit Active    | False   | False   | False        |            |             |          |      | 
| alarmLowStatus      | .alarmLowStatus      | Bool     |         | Alarm Low Limit Active      | False   | False   | False        |            |             |          |      | 


## InOuts

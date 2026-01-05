# CM TYPE: DigitalMeasurement

- dexpi-mapping: HandValve
- mtp-mapping: BinMon

## Inputs
| Name  | Suffix | DataType | IO Type | Comment                                                       | Primary | IsError | Configurable | True Words | False Words | Loopback | Enum | 
| ----- | ------ | -------- | ------- | ------------------------------------------------------------- | ------- | ------- | ------------ | ---------- | ----------- | -------- | ---- | 
| id    |        | Int      |         | unique project-wide ID to uniquely identify and track objects | False   | False   | True         |            |             |          |      | 
| value | .value | DI       |         | Value coming from device                                      | False   | False   | False        |            |             |          |      | 


## Outputs
| Name        | Suffix       | DataType | IO Type | Comment                                   | Primary | IsError | Configurable | True Words | False Words | Loopback | Enum | 
| ----------- | ------------ | -------- | ------- | ----------------------------------------- | ------- | ------- | ------------ | ---------- | ----------- | -------- | ---- | 
| valueOut    | .valueOut    | Bool     |         | Value for use in program                  | True    | False   | False        |            |             |          |      | 
| risingEdge  | .risingEdge  | Bool     |         | Input value transitioned from low to high | False   | False   | False        |            |             |          |      | 
| fallingEdge | .fallingEdge | Bool     |         | Input value transitioned from high to low | False   | False   | False        |            |             |          |      | 


## InOuts

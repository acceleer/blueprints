# PHASE TYPE: Filling

## Description


## Linked Modules


## Inputs
| Name    | DataType | Comment                                                                            | DefaultFromInstance | Unit | Enum | 
| ------- | -------- | ---------------------------------------------------------------------------------- | ------------------- | ---- | ---- | 
| PhaseId | Int      | Unqiue ID of the Phase Instance in the entire project. Can be used to acquire EM's | True                |      |      | 
| UnitId  | Int      | Unqiue ID of the Unit Instance that this Phase Instance belongs to.                | True                |      |      | 


## Outputs
| Name              | DataType | Comment                                                                              | DefaultFromInstance | Unit | Enum | 
| ----------------- | -------- | ------------------------------------------------------------------------------------ | ------------------- | ---- | ---- | 
| ModuleError       | Bool     | Error signal collecting all errors from the connected Control and Equipment Modules. | False               |      |      | 
| StartTime         | Real     | Start time, registered when jumping from Idle to Running                             | False               |      |      | 
| CurrentTime       | Real     | Current time (now), updated each controller cycle                                    | False               |      |      | 
| start_conditions  | Bool     | True if all start conditions are ok. For usage in the 'Idle' transition              | False               |      |      | 
| StepTime          | Real     | StepTime in s                                                                        | False               |      |      | 
| StepTimeSetpoint  | Real     | Steptime Setpoint in s. Will automatically count down in StepTimeRemaining           | False               |      |      | 
| StepTimeWatchdog  | Real     | for monitoring if StepTime passes this watchdog                                      | False               |      |      | 
| StepTimeRemaining | Real     | remaining steptime if steptime_setpoint has been set in the step                     | False               |      |      | 


## InOuts


## Internal Values
| Name            | DataType | Comment         | DefaultFromInstance | Unit | Enum | 
| --------------- | -------- | --------------- | ------------------- | ---- | ---- | 
| command_start   | Bool     | Start command   | False               |      |      | 
| command_reset   | Bool     | Reset command   | False               |      |      | 
| command_resume  | Bool     | Resume command  | False               |      |      | 
| command_restart | Bool     | Restart command | False               |      |      | 
| command_abort   | Bool     | Abort command   | False               |      |      | 
| command_unhold  | Bool     | Unhold command  | False               |      |      | 


## HMI Parameters


## Recipe Parameters
| Name     | DataType | Comment | Min | Default | Max | Unit | Enum | 
| -------- | -------- | ------- | --- | ------- | --- | ---- | ---- | 
| Quantity | Real     |         |     |         |     |      |      | 


## Report Parameters


## Timers


## Cyclic Actions


## Sequences

## Idle State

| Step | Actions | Conditions                         | Target | 
| ---- | ------- | ---------------------------------- | ------ | 
| 0    | # Idle  | command_start and start_conditions | 10     |

## Starting State

| Step | Actions    | Conditions | Target | 
| ---- | ---------- | ---------- | ------ | 
| 10   | # Starting |            | 1000   |

## Execute State

| Step | Actions   | Conditions | Target | 
| ---- | --------- | ---------- | ------ | 
| 1000 | # Execute |            | 2000   |

## Pausing State

| Step | Actions   | Conditions | Target | 
| ---- | --------- | ---------- | ------ | 
| 4000 | # Pausing |            | 4500   |

## Paused State

| Step | Actions  | Conditions                          | Target | 
| ---- | -------- | ----------------------------------- | ------ | 
| 4500 | # Paused | command_resume and start_conditions | 4600   |

## Resuming State

| Step | Actions    | Conditions | Target | 
| ---- | ---------- | ---------- | ------ | 
| 4600 | # Resuming |            | 1000   |

## Completing State

| Step | Actions      | Conditions | Target | 
| ---- | ------------ | ---------- | ------ | 
| 2000 | # Completing |            | 2100   |

## Completed State

| Step | Actions     | Conditions    | Target | 
| ---- | ----------- | ------------- | ------ | 
| 2100 | # Completed | command_reset | 3000   |

## Holding State

| Step | Actions   | Conditions | Target | 
| ---- | --------- | ---------- | ------ | 
| 5000 | # Holding |            | 5500   |

## Held State

| Step | Actions | Conditions                          | Target | 
| ---- | ------- | ----------------------------------- | ------ | 
| 5500 | # Held  | command_unhold and start_conditions | 5600   |

## Unholding State

| Step | Actions     | Conditions | Target | 
| ---- | ----------- | ---------- | ------ | 
| 5600 | # Unholding |            | 1000   |

## Stopping State

| Step | Actions    | Conditions | Target | 
| ---- | ---------- | ---------- | ------ | 
| 6000 | # Stopping |            | 6500   |

## Stopped State

| Step | Actions   | Conditions    | Target | 
| ---- | --------- | ------------- | ------ | 
| 6500 | # Stopped | command_reset | 3000   |

## Aborting State

| Step | Actions    | Conditions | Target | 
| ---- | ---------- | ---------- | ------ | 
| 7000 | # Aborting |            | 7500   |

## Aborted State

| Step | Actions   | Conditions    | Target | 
| ---- | --------- | ------------- | ------ | 
| 7500 | # Aborted | command_reset | 3000   |

## Resetting State

| Step | Actions     | Conditions | Target | 
| ---- | ----------- | ---------- | ------ | 
| 3000 | # Resetting |            | 0      |


## Hold & Start Conditions


## Warnings, Alarms & Messages

# PHASE TYPE: DemoPhase

## Description
This demo phase demonstrates all the possibilities of a phase design, including
  a demonstration of how we can use a human-readable grammar to describe every
  possible functionality needed in a phase.

## Linked Modules
| Name         | Type              | Dynamic | Connection Type | Comment                          | 
| ------------ | ----------------- | ------- | --------------- | -------------------------------- | 
| P4712        | ReversingMotor    |         | CM              | Pump for dosing liquit from tank | 
| PICSA4712_02 | AnalogMeasurement |         | CM              | Pressure sensor product          | 
| PV4712_02    | AnalogValve       |         | CM              | Circulation valve                | 
| UC4712_03    | PIDController     |         | CM              | Pressure control loop            | 
| DosingValve  | SolenoidValve     |         | CM              | Dosing Valve                     | 


## Inputs
| Name       | DataType | Comment                                                                            | DefaultFromInstance | Unit | Enum | 
| ---------- | -------- | ---------------------------------------------------------------------------------- | ------------------- | ---- | ---- | 
| PhaseId    | Int      | Unqiue ID of the Phase Instance in the entire project. Can be used to acquire EM's | True                |      |      | 
| UnitId     | Int      | Unqiue ID of the Unit Instance that this Phase Instance belongs to.                | True                |      |      | 
| TestInput1 | Int      | TestInput1 comment                                                                 | False               |      |      | 


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
| TestOutput1       | Int      | TestOutput1 comment                                                                  | False               |      |      | 


## InOuts
| Name       | DataType | Comment            | DefaultFromInstance | Unit | Enum | 
| ---------- | -------- | ------------------ | ------------------- | ---- | ---- | 
| TestInOut1 | Int      | TestInOut1 comment | False               |      |      | 


## Internal Values
| Name            | DataType | Comment                  | DefaultFromInstance | Unit | Enum | 
| --------------- | -------- | ------------------------ | ------------------- | ---- | ---- | 
| command_start   | Bool     | Start command            | False               |      |      | 
| command_reset   | Bool     | Reset command            | False               |      |      | 
| command_resume  | Bool     | Resume command           | False               |      |      | 
| command_restart | Bool     | Restart command          | False               |      |      | 
| command_abort   | Bool     | Abort command            | False               |      |      | 
| command_unhold  | Bool     | Unhold command           | False               |      |      | 
| TestInternal1   | Int      | TestInternal1 comment    | False               |      |      | 
| TargetLevel     | Real     | Calculated before dosing | False               |      |      | 
| StartLevel      | Real     | Stored before dosing     | False               |      |      | 
| a               | Real     |                          | False               |      |      | 
| b               | Real     |                          | False               |      |      | 
| c               | Real     |                          | False               |      |      | 
| d               | Real     |                          | False               |      |      | 


## HMI Parameters
| Name              | DataType | Comment                                                                              | Min | Default | Max | Unit | Enum | 
| ----------------- | -------- | ------------------------------------------------------------------------------------ | --- | ------- | --- | ---- | ---- | 
| TestHmiParameter1 | Int      | TestHmiParameter1 comment                                                            |     |         |     |      |      | 
| DosingOffset      | Real     | Offset to stop the dosing a little bit earlier in order to reach the target quantity |     |         |     |      |      | 


## Recipe Parameters
| Name                 | DataType | Comment                      | Min | Default | Max | Unit | Enum | 
| -------------------- | -------- | ---------------------------- | --- | ------- | --- | ---- | ---- | 
| TestRecipeParameter1 | Int      | TestRecipeParameter1 comment |     |         |     |      |      | 
| DosingQuantity       | Real     | Quantity to be dosed         |     |         |     |      |      | 


## Report Parameters
| Name                 | DataType | Comment                      | Unit | Enum | 
| -------------------- | -------- | ---------------------------- | ---- | ---- | 
| TestReportParameter1 | Int      | TestReportParameter1 comment |      |      | 


## Timers


## Cyclic Actions


## Sequences

## Idle State

| Step | Actions | Conditions                         | Target | 
| ---- | ------- | ---------------------------------- | ------ | 
| 0    | # Idle  | command_start and start_conditions | 10     |

## Starting State

| Step | Actions                                            | Conditions                                         | Target | 
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ | 
| 10   | # Variables can be assigned new values through     | # Transitions can be comparisons of mathematical   | 20     |
|      |   mathematical formula's                           |   formula's                                        |        |
|      | // simple calculation                              | a > b * (c + d)                                    |        |
|      | TargetLevel = StartLevel + DosingQuantity -        | -------------------------------------------------- | ------ |
|      |   DosingOffset                                     | # One step can have multiple transitions to        | 30     |
|      | // use of brackets                                 |   different target steps                           |        |
|      | a = b * (c + d)                                    | a > 100                                            |        |
|      |                                                    | -------------------------------------------------- | ------ |
|      |                                                    | # Condition with boolean logic                     | 20     |
|      |                                                    | a > 100 or b > 200                                 |        |
|      |                                                    | -------------------------------------------------- | ------ |
|      |                                                    | # Conditions can be written over multiple lines    | 20     |
|      |                                                    |   for clarity                                      |        |
|      |                                                    | a > 100                                            |        |
|      |                                                    | or b > 200                                         |        |
|      |                                                    | -------------------------------------------------- | ------ |
|      |                                                    | # Complex boolean logic can be indented for        | 20     |
|      |                                                    |   clarity                                          |        |
|      |                                                    | a > 100                                            |        |
|      |                                                    | and (                                              |        |
|      |                                                    | b > 200                                            |        |
|      |                                                    | or c > 130                                         |        |
|      |                                                    | )                                                  |        |
|      |                                                    | -------------------------------------------------- | ------ |
|      |                                                    | # Comments can be added after each line to clarify | 20     |
|      |                                                    | a > 100 // a needs to be bigger than 100           |        |
|      |                                                    | and (                                              |        |
|      |                                                    | b > 200 // if b is bigger than 200                 |        |
|      |                                                    | or c > 130 // or if c is bigger than 130           |        |
|      |                                                    | )                                                  |        |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 20   | # Control Modules can be controlled like this:     | # The status of Control Modules can be checked     | 30     |
|      | # [verb] [ControlModuleName]                       |   like this:                                       |        |
|      | # The verbs are configured in the CM Type Package. | # [ControlModuleName] [status]                     |        |
|      | # ControlModuleName can be an abstract name,       | # The statuses are configured in the CM Type       |        |
|      |   because one PhaseType can have multiple Phase    |   Package                                          |        |
|      |   Instances with diffent Control Module Instancees | # For example check if a valve is opened:          |        |
|      |   connected                                        | DosingValve opened                                 |        |
|      | // open a valve                                    | -------------------------------------------------- | ------ |
|      | open DosingValve                                   | # Check if a valve is closed:                      | 30     |
|      | // close a valve                                   | DosingValve closed                                 |        |
|      | close DosingValve                                  | -------------------------------------------------- | ------ |
|      |                                                    | # Example of a condition combining a status check  | 30     |
|      |                                                    |   with a value comparison:                         |        |
|      |                                                    | DosingValve opened                                 |        |
|      |                                                    | and a > 100                                        |        |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 30   | # // Variables on Control Modules can be accessed  | DosingValve.automaticMode = true                   | 1000   |
|      |   directly                                         |                                                    |        |
|      | # (tip: the preference goes to configuring and     |                                                    |        |
|      |   using verbs and states if this makes things more |                                                    |        |
|      |   readable for non-automation engineers)           |                                                    |        |
|      | DosingValve.reset = true                           |                                                    |        |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 40   | # todo: AnalogMeasurement examples                 |                                                    | 50     |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 50   | # todo: AnalogValve examples                       |                                                    | 60     |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 60   | # todo: DigitalMeasurement examples                |                                                    | 70     |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 70   | # todo: PIDController examples                     |                                                    | 80     |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 80   | # todo: ReversingMotor examples                    |                                                    | 90     |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 90   | # todo: VFD examples                               |                                                    | 100    |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 100  | # Actions can be conditionally executed:           |                                                    | 110    |
|      | # [action] if [condition]                          |                                                    |        |
|      | open DosingValve if a > 100                        |                                                    |        |
| ---- | -------------------------------------------------- | -------------------------------------------------- | ------ |
| 110  | # Conditional actions can also have a delay: the   | # conditions in the transitions can also have      | 1000   |
|      |   condition needs to be active for a delaytime     |   delays, just like in the actions                 |        |
|      |   before the action is  executed                   | # NOTE: the delay can only be added at the end and |        |
|      | # [action] if [condition] for [delay][timeUnit]    |   applies to the entire condition.                 |        |
|      | # [timeUnit] options: ms, s, min, h, days          | # If separate delays are needed for parts of a     |        |
|      | # If delay is a variable then [timeUnit] is not    |   condition then make separate actions to          |        |
|      |   needed (it will be deducted from the unit        |   intermediate variables.                          |        |
|      |   configured at the variable)                      | DosingValve opened for 5s                          |        |
|      | # tip: hover over the action line to see the       |                                                    |        |
|      |   DelayMultiplier to calculate milliseconds, as    |                                                    |        |
|      |   well as the timer number that will be used when  |                                                    |        |
|      |   generating the code                              |                                                    |        |
|      | open DosingValve if a > 100 for 5s                 |                                                    |        |

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
| No | Condition                 | Start | Hold | Steps         | 
| -- | ------------------------- | ----- | ---- | ------------- | 
| 1  | # example start condition | x     |      |               |
|    | StartLevel > 10           |       |      |               |
| -- | ------------------------- | ----- | ---- | ------------- | 
| 2  | # example hold condition  |       | x    | 10, 20, 30-40 |
|    | StartLevel > 20           |       |      |               |


## Warnings, Alarms & Messages
| No | Condition                      | Warning | Alarm | Message | Steps          | 
| -- | ------------------------------ | ------- | ----- | ------- | -------------- | 
| 1  | # example warning              | x       |       |         | 70, 80, 90-100 |
|    | > warning message for operator |         |       |         |                |
|    | a> 100                         |         |       |         |                |
| -- | ------------------------------ | ------- | ----- | ------- | -------------- | 
| 2  | # example alarm                |         | x     |         |                |
|    | > alarm message for operator   |         |       |         |                |
|    | a > 200                        |         |       |         |                |
| -- | ------------------------------ | ------- | ----- | ------- | -------------- | 
| 3  | # example message              |         |       | x       |                |
|    | > normal message for operator  |         |       |         |                |
|    | a > 300                        |         |       |         |                |

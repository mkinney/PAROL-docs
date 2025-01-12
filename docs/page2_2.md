 
# Robot specifications

## Specs 

* Payload: 1 Kg
* Weight: 5.5 Kg
* Reach: 400 mm with the standard gripper
* Degrees of freedom: 6 rotating joints
* Material: 3D printed PETG plastic
* Power consumption: 40W
* Repeatability: 0.1 mm
* Precision: 
* Rotation range: 
- 1 – 250 deg
- 2 – 141 deg
- 3 – 180 deg
- 4 – 212 deg
- 5 – 180 deg
- 6 - ∞
* Motors: Steppers
* Gearboxes: precision planetary and bets
* Position sensing: Limit switches for open loop version, magnetic encoders for closed-loop version
* Drivers: Open-loop stepper drivers for open loop version, custom FOC Stepper drivers for closed-loop
* Number of isolated inputs: 2
* Number of isolated outputs: 2
* Number of CAN buses: 2
* Communication with master PC: USB 
* Pneumatic connectors: 2

## Dimensions

<p align="center">
<img src="../assets/Dimensions.png" alt="drawing" width="800"/> <br />
</p>

Dimensions using default pneumatic gripper!

|      |         |
| ----------- | ------------------------------------ |
| a1       |  110.50 mm | 
| a2      | 23.42 mm | 
| a3    | 180.00 mm |
| a4       | 43.50 mm  | 
| a5       | 176.35 mm| 
| a6    | 62.8 mm|
| a7    | 45.25 mm|

!!! Note annotate "Dimensions can change!"

    For example when you change grippers or put robot on aditional base. <br />
    If that happens you need to change your parameters in DH table, otherwise you kinematic diagram will be wrong  <br />


## Kinematic diagram 

!!! Note annotate "Dimensions can change!"

    For example when you change grippers or put robot on aditional base. <br />
    If that happens you need to change your parameters in DH table, otherwise you kinematic diagram will be wrong  <br />


<p align="center">
<img src="../assets/Kinematic_diagram.png" alt="drawing" width="800"/> <br />
</p>

* Digram for the robot using standard pneumatic gripper

## Denavit-Hartenberg parameters


<p align="center">
<img src="../assets/Joints.png" alt="drawing" width="800"/> <br />
</p>

!!! Warning annotate "Standby position"

    **THIS IS THE POSITION OF THE ROBOT DEFINED BY THE DH TABLE BELOW!** <br />
    ** This position is also called standby positon! ** <br />
    ** In this position joint angles are as follows: ** <br />
    ** Joint 1 -> 0 degress **  <br />
    ** Joint 2 -> -90 degress **  <br />
    ** Joint 3 -> 180 degrees ** <br />
    ** Joint 4 -> 0 degrees ** <br />
    ** Joint 5 -> 0 degrees ** <br />
    ** Joint 6 -> 180 degrees ** <br />


<p align="center">
<img src="../assets/DH_table.png" alt="drawing" width="800"/> <br />
</p>

## Joint reduction ratios and microstepping 

Reduction ratios for each joint are as follows:

* Joint 1 -> Belt reduction: 6.4 : 1
* Joint 2 -> Planetary gearbox: 20 : 1
* Joint 3 -> Planetary gaerbox: 20 : 1 x Belt reduction 38 : 42 = 18.0952381
* Joint 4 -> Belt reduction: 4 : 1
* Joint 5 -> Belt reduction: 4 : 1
* Joint 6 -> Planterary gearbox: 10 : 1

Robot uses stepper motors. Microstepping is on all motors equal to 32. <br />
With 32 microstepping regular 200 steps per revolution stepper motor needs 6400 steps for one revolution.

## Joint limits

!!! Note annotate "TIP"

    Joint limits can change depending on type of gripper or base!  <br />
    When using the robot make sure you use proper joint limits for your aplicaiton!  <br />

Robot joint positive rotations are in the directions shown on the image!

<p align="center">
<img src="../assets/rotations1.png" alt="drawing" width="800"/> <br />
</p>

!!! Note annotate "TIP"

    Values are in degrees!

| Joint      | Limit in negative direction        | Standby position| Limit in positive direction |
| ----------- | ------------------------------------ | -- | ------------------------------------ |
| J1       | -123.046875 | 0 | 123.046875 |
| J2       | 145.0088 | -90 | -3.375 |
| J3    | 107.866     | 180 | 287.8675 |
| J4       | -105.46975 | 0 | 105.46975|
| J5       | -90 | 0 |90 |
| J6    | 0 | 180 | 360 |
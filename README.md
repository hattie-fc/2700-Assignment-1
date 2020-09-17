# 2700-Assignment-1: Discus Trajectory

## Description
This project computes the trajectory of a discus throw based on initial input parameters.
The project aims at determining the optimum initial flight path angle, gamma, for which the throw distance is maximised. This parameter is the main variable.
Included are two programs:
1. discus_trajectory.py 
2. validation_analyticalsolution.py

## 1. discus_trajectory.py
This is a program to compute the trajectory of a discus from when it leaves the thrower's hand until it hits the ground.
The program takes the following input parameters: 
- intial x-position, x_0 (m)
- initial y-position, y_0 (m)
- initial velocity, v_0 (m/s)
- gravitational acceleration, g (m/s^2)
- discus mass, m (kg)
- density of air, p (kg/m^3)
- lift coefficient, C_l
- drag coefficient, C_d
- reference area, A_ref (m^2)
- timestep, dt (s)

### Usage
To use this program, enter the required values for the input parameters. 
The program has a set of defult parameters listed in lines 13-23, however these can be adjusted by replacing the defult value. For example, to compute the trajectory of the women's discus throw, initial velocity, discus mass and reference area should be set to 30m/s, 1kg and 0.025m^2 respectively. These are the defult values. However, to compute the trajectory of the men's discus throw, initial velocity, disccus mass and reference area should be changed to 25m/s, 2kg and 0.038m^2 respectively. 

Next, the main variable - the initial flight path angle, gamma - can be adjusted to observe how the trajectory changes. This parameter is listed on line 34.  

### Outputs 
The program can be adjusted to output specific results. Lines 81-84 contain four print statements which may be commented in or out depending on what information is desired from the program. These constist of:
- line 81: # print(f"xs={xs} \t ys={ys}") # x & y displacement
- line 82: # print(f"vxs={vxs} \t vys={vys}") # x & y velocity
- line 83: # print(f"Distance is {distance} m")
- line 84: # print(f"Time of flight is {time} seconds")

While in the above format, the program outputs only a plot of trajectory and velocity. If discrete data points are desired for displacement and velocity, lines 81 and 82 can be enabled by removing the hashtag (#). This will print the data as a list. If data for distance and time of flight are desired, lines 83 and 84 respectively can be inabled in the same manner. For example: 
- line 83: # print(f"Distance is {distance} m")  ---> no output printed
- line 83:  print(f"Distance is {distance} m")  ---> output printed

Two plots are automatically outputed to graph the displacement and velocity of the discus throw. These are labelled accordingly for ease of interpretation. 

## validation_analyticalsolution.py
This program is used to test the validity of the program file discus_trajectory.py by comparing the outputs from both files. 
To test validity, it is necessary to run both validation_analyticalsolution.py and file discus_trajectory.py with the same input parameters. These input parameters can be adjusted in the same way as described above in the section 'Usage' for discus_trajectory.py. However, initial flight path angle, gamma, is located in line 23 under """variables""". All parameters, including gamma, should be the same in each file. 

### Usage
Before running the programs, line 23 in discus_trajectory.py should be adjusted so that the timestep is 1 second. For example: 
- before adjustment: dt = 0.0009 # timestep, s
- after adjustment: dt = 1 # timestep, s
The timestep in validation_analyticalsolution.py does not need to be changed. 
Additionally, line 81 in discus_trajectory.py should be enabled (remove hashtag) so that the displacement data points are printed. 

### Outputs
Run both files. Note the outputs. These should consists of a small set of data points in a list and should match with each file. 
If the outputs match each other, then the program file discus_trajectory.py can be considered a valid model. 

## Authors and Acknowledgements
Author: Harriet Carlile

Date: 17.09.20

### References: 
- Bedford, A., & Fowler, W. T. (2001). Engineering Mechanics: Dynamics Principles. Prentice Hall. Retrieved September 2020
- University of Queensland. (2020). Assignment 1: Computational Mechanics. Brisbane. Retrieved September 2020, from https://learn.uq.edu.au/bbcswebdav/pid-5330794-dt-content-rid-29661812_1/courses/MECH2700S_7060_61359/mech2700-2020-assignment-1.pdf

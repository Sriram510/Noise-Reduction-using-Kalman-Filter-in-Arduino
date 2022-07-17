# Noise-Reduction-using-Kalman-Filter-in-Arduino

### Introduction to Kalman Filters:
###### Kalman filtering is an algorithm that provides estimates of some unknown variables given the measurements observed over time. Kalman filters have been demonstrating its usefulness in various applications. Kalman filters have relatively simple form and require small computational power. However, it is still not easy for people who are not familiar with estimation theory to understand and implement the Kalman filters. Whereas there exist some excellent literatures such as [this](https://automaticaddison.com/extended-kalman-filter-ekf-with-python-code-example/) which explains how a kalman filter works and implementing one in python addressing theory behind the Kalman filter, this chapter focuses on a more practical perspective.
### Getting raw data from MPU9250
<img src="https://user-images.githubusercontent.com/90887611/178131777-2074dd50-6018-470b-9844-9887e182cbc6.jpeg" width="250" height="300" />

###### Step 1. MPU9250 was hooked up to the  mircocontroller(mCU) using I2C connection i.e(SCL->SCL port of the mCU,SDA->SDA port of the mCU).
<img src="https://user-images.githubusercontent.com/90887611/178132033-b2dcf82d-fbd6-4877-9647-3b3fd42ea8b1.jpeg" width="400" height="250" />

###### Step 2. MPU9250 library for arduino was downloaded using the Arduino IDE library manager from [Hideakitai](https://github.com/hideakitai/MPU9250).
###### Step 3. Magnetic declination of the current location was changed in the library file before IMU calibration.
###### Step 4. IMU biases, scaling factor etc, were obtained in serial moniter using calibration.ino example file.
###### Step 5. Kalman Filter for Arduino library from [rfetick](https://github.com/rfetick/Kalman) was used to implement the filter.
###### Step 6. State transition and observation matrices for roll,pitch and yaw were given as arguments for state space model.
###### Step 7. Process noise and sensor noise covariance matrices were given to predict and update the states and give an optimal estimation of three orientations.
#### ***SENSOR NOISE: The distribution of points of uncertainty in sensor measurements or put it simply the standard deviation of the sensor meausrements.***
#### ***PROCESS NOISE: It gives information about how fast proccessed information change according to changes in sensor measurements i.e the reaction time or 1/inertia so the more the inertia the more proccesed signal resist to changes in sensor measurements***.

## RESULTS:-
#### Measurements without the filter
![imu_w-o_kalman](https://user-images.githubusercontent.com/90887611/179392198-8513f1d0-f76b-4415-a7d4-5bcd14137c78.png)

#### Measurements with the filter with higher process noise matrix
![imu_w_kalman](https://user-images.githubusercontent.com/90887611/179392505-f0cd37d2-7ce1-4bcf-9345-652b115c37a6.png)
#### Measure with filter using lower process noise matrix
![imu_w_kalman2](https://user-images.githubusercontent.com/90887611/179392245-63885e50-d20a-4a05-ae29-7baa50b91a10.png)
#### Measure with filter using much lower process noise matrix

![imu_w_kalman2](https://user-images.githubusercontent.com/90887611/179392609-44710dad-cf4a-47f8-86d8-377879caa304.png)

### CONCLUSION:-
#### Implementation of kalman filter to reduce noise in the sensor readings was successfull, though sensor fusion using kalman filter was not used and the results were pretty satisfactory. 

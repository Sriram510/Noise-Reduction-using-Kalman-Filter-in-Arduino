# Noise-Reduction-using-Kalman-Filter-in-Arduino

### Introduction to Kalman Filters:
###### Kalman filtering is an algorithm that provides estimates of some unknown variables given the measurements observed over time. Kalman filters have been demonstrating its usefulness in various applications. Kalman filters have relatively simple form and require small computational power. However, it is still not easy for people who are not familiar with estimation theory to understand and implement the Kalman filters. Whereas there exist some excellent literatures such as [this](https://automaticaddison.com/extended-kalman-filter-ekf-with-python-code-example/) which explains how a kalman filter works and implementing one in python addressing theory behind the Kalman filter, this chapter focuses on a more practical perspective.
### Getting raw data from MPU9250
###### Step 1. MPU9250 was hooked up to the  mircocontroller(mCU) using I2C connection i.e(SCL->SCL port of the mCU,SDA->SDA port of the mCU).

# Self-Driving Car Engineer Nanodegree

## Project: **Extended Kalman Filter**

The goals / steps of this project are the following:

* Build an Extended Kalman Filter for tracking a pedestrian.

* Familiarize myself with C++ coding.

* Test that the EKF on a provided simulator.

* Summarize the results with a written report.


## Rubric Points

---
### Project Overview

The present work has used a simulator to provide Lidar and Radar measurement data from the position and speed of a moving pedestrian. It was implemented an [Extended Kalman Filter](https://en.wikipedia.org/wiki/Extended_Kalman_filter) in order to estimate a future position and speed of the pedestrian following each measurement. When Lidar data was provided, a Standard Kalman Filter was run. When Radar data was provided, an Extended Kalman Filter was used.

The key metrics optimized were [RMSE](https://en.wikipedia.org/wiki/Root-mean-square_deviation) values for both position and speed of the tracked pedestrian. The maximum RMSE values acceptable for this project for [Dataset 1](https://github.com/udacity/CarND-Extended-Kalman-Filter-Project/blob/master/data/obj_pose-laser-radar-synthetic-input.txt) are:

- `0.11` for `Px` and `Py`.
- `0.52` for `Vx` and `Vy`.

### Results

#### 1. Sensor Fusion (Lidar and Radar)

The folowing table lists the results for both datasets:

| RMSE | Dataset 1 | Dataset 2 |
|------|-----------|-----------|
|  Px  |  0.0973   |  0.0729   |
|  Py  |  0.0855   |  0.0965   |
|  Vx  |  0.4513   |  0.4216   |
|  Vy  |  0.4399   |  0.4932   |

Figures 1 and 2

Figure 1: Dataset 1               |Figure 2: Dataset 2
:--------------------------------:|:--------------------------------:
<img src="./images/Dataset1.png"> |<img src="./images/Dataset2.png">


I tested the Extended Kalman Filter with the fusion of Lidar and Radar sensors. The fused sensors have positional root mean squared errors on the order of 0.09, while the velocity errors are on the order of 0.45. Here is an image of the output visualized with green being the filter estimation, and red and blue being the lidar and radar sensor data. Later I tested the filter with only radar or only lidar to see how the different sensors contribute to the errors.


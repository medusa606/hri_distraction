# hri_distraction

## Overview



## The Study

### Participants

### Control & Experiment Tests

## The Equipment

The Baxter Robot
Force Torque gauge (robot right EE only)
Participant Gaze Tracker
Xsens Skeletal Tracker
Scene camera


## Data

Breakdown of all the data channels gathered
Synchronisation of channels
Name and number each channel
Link to matlab dataframe

## Results

This is a Matlab plot showing data gathered from a human-robot interaction (HRI) trial focusing on how people may become distracted while interacting with a robot and what safety related consequences this may lead to. The top left is a video of the scene showing a participant receiving dressing assistance from a Baxter robot. The participant is also undertaking a cognitive test (on the TV screen) and the result are shown in the upper right figure.

![](HRI.gif)

A skeletal tracker was used to capture the pose of the participant and the gaze azumith direction is shown as a red dotted line on the floor. Additional data plots show the left and right end effector height of the robot and the force observed in all three axes. The figure at the bottom tracks a number of other features of the scenario, such as where the participant is looking, which can be used to look at correlations between distraction and the recorded events.

To compile this large dataset of 42 participants each with around 40 minutes of recording required joining and regularising several different sources of data recordings including researcher coded data based on video observations, data captured from the ROS message environment, video cameras, a gaze tracking device, the participant skeletal tracking suite and force gauges from the robot.

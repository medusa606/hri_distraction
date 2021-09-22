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

## Time Synchronisation of Data Channels

Data for this experiment was captured in 

* Video of experimental scene (ground truth)
* Pose Data: Baxter and Xsens Skeletal Tracker
* Gaze Tracking & Behaviour Coding including cognitive test

Due to software lags, poor time synchronisation between the start of the recordings for each data channel was present. This resulted in small differences in the relative start time for each channel. Therefore an offset time for each channel has to be applied in order to align each channel correctly.

To do this we use the experimental video camera as the reference time and align all data channels to this reference. Therefore we apply an offset to each channel for each participant to ensure synchronisation. These offset values were derived from monitoring the data with respect to the video and applying an offset value, either negative to precede the video or positive to succeed the start of the video. 

### Video of experimental scene

We are using this as the ground truth so no offset is required for this channel.

### Pose Data: Baxter and Xsens Skeletal Tracker

Time Offset

This time offset correction is best achieved by observing a fast motion of the participant, e.g. lifting the hand to the jacket or turning the head, and checking alignment with the video time index. The offset data for each participant is stored in xsens_offset.mat as this applies to the xsens data capture system.

Skeletal Orientation

An oddity with the Xsens system is that the system automatically aligns the orientation of the skeleton with magnetic north regardless of the actual orientation of the person wearing the suit. During the experiment we attempted to rectify this by performing a calibration of the suit whilst the participant was oriented facing north. However, the suit was highly non-deterministic and often the calibration would not work resulting in an orientation offset, i.e. facing the wrong direction with respect to the robot. The errors were usually small, e.g. 10-20 degrees

### Gaze Tracking & Behaviour Coding

This can be easily verified by observing the first shape on the cognitive load test and aligning this time point to the first shape in the classified behaviour data. The offset data for this channel is stored in coding_offset.mat.



## Results

This is a Matlab plot showing data gathered from a human-robot interaction (HRI) trial focusing on how people may become distracted while interacting with a robot and what safety related consequences this may lead to. The top left is a video of the scene showing a participant receiving dressing assistance from a Baxter robot. The participant is also undertaking a cognitive test (on the TV screen) and the result are shown in the upper right figure.

![](HRI.gif)

A skeletal tracker was used to capture the pose of the participant and the gaze azumith direction is shown as a red dotted line on the floor. Additional data plots show the left and right end effector height of the robot and the force observed in all three axes. The figure at the bottom tracks a number of other features of the scenario, such as where the participant is looking, which can be used to look at correlations between distraction and the recorded events.

To compile this large dataset of 42 participants each with around 40 minutes of recording required joining and regularising several different sources of data recordings including researcher coded data based on video observations, data captured from the ROS message environment, video cameras, a gaze tracking device, the participant skeletal tracking suite and force gauges from the robot.

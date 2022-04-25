# Human Robot Interaction Study on Distraction

## Overview

This is a repository for the data collected in a large HRI study undertaken at the Bristol Robotics Lab, UK. THe study was undertaken to look at distraction of people while they are assisted in a dressing task by a robot. In the study 42 participants were assisted with jacket dressing by a Baxter robot whilst being distracted. We looked for physical cues that might indicate distraction in the task with the intention of these physical traits being useful for detection of distraction in other operational robotic applications.

## The Study

In the study we focused on what physical cues people may display when they become distracted with the hope this would better inform future HRI tasks and improve safety outcomes for end users of such applications. The chart below shows a sample of the results.

![](HRI.gif)

This is a Matlab plot showing an example of the data gathered from the study. The top left is a video of the scene showing a participant receiving dressing assistance from a Baxter robot. The participant is also undertaking a cognitive loading test (on the TV screen) and the result are shown in the upper right figure.

A skeletal tracker was used to capture the pose of the participant and the gaze azumith direction is shown as a red dotted line on the floor. Additional data plots show the left and right end effector height of the robot and the force observed in all three axes. The figure at the bottom tracks a number of other features of the scenario, such as where the participant is looking, which can be used to look at correlations between distraction and the recorded events.

The experiment was split into two parts. The first was to record the dressing task without any distraction, where the dressing sequence was repeated 5 times and in each case the robot moved the jacket up to the shoulders and then dropped it back down again. The second half of the test repeated the dressing sequence but this time with a COT (Cognitive Overload Test), displayed on the screen in front of them. In addition to the COT, the participant was further distracted by the researcher.

### Participants

The dataset is comprised of recordings from 42 participants each with around 40 minutes of data. The participants were volunteers from the Bristol Robotics Lab and UWE Frenchay campus. Consent forms were signed prior to participation. There were 14 males and 28 females.

### Control & Experiment Tests

Data was captured from several different input sources including video observations, data captured from the ROS message environment including robot pose, video cameras, a gaze tracking device, the participant skeletal tracking suite and force gauges from the robot. Post analysis of the video footage from the gaze tracking glasses was codified with the visual fixation of the participant. 

## The Equipment

Baxter robot
Force torque gauge (robot right EE only)
Gaze tracking glasses
Xsens skeletal tracker
Scene camera
TV screen with cognitive test
More distraction props: Telephone, Remote-Controlled Mouse

## Data

Breakdown of all the data channels gathered
Synchronisation of channels
Name and number each channel
Link to matlab dataframe

## Synchronisation of Data Channels

Data for this experiment was captured in 

* Video of experimental scene (ground truth)
* Pose Data: Baxter and Xsens Skeletal Tracker
* Gaze Tracking & Behaviour Coding including cognitive test

Due to software lags, poor time synchronisation between the start of the recordings for each data channel was present. This resulted in small differences in the relative start time for each channel. Therefore an offset time for each channel has to be applied in order to align each channel correctly. To do this we use the experimental video camera as the reference time and align all data channels to this reference. Therefore we apply an offset to each channel for each participant to ensure synchronisation. These offset values were derived from monitoring the data with respect to the video and applying an offset value, either negative to precede the video or positive to succeed the start of the video. 

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



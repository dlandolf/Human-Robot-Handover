## Introduction
Using a robotic camera arm (equipped with a ZED stereo camera) mounted on a YuMi robot (a fixed base robot with two arms), the goal is to achieve natural human-robot collaboration. This includes handovers of objects and teaching the robot motions by demonstrating them with the user's own arms. To do so, visual human pose estimation and gesture recognition together with modern trajectory optimization algorithms are combined. Depending on the recognized gesture, different actions are taken. Human-like robot motions were implemented to give the user a feedback and an intuitive feeling on what the robot is currently doing.

## Demonstration Videos
### Handovers
[![Demo Video](previewHandoverVideo.jpg)](https://drive.google.com/file/d/1yyncGYVv7DoV692pkiEP54egaygbp7yu/view?usp=sharing "Demo Video")

### Teach and repeat motions
[![Demo Video Teaching](previewVideoTeach.jpg)](https://drive.google.com/file/d/1R-EjH70Cn7Vwk-38XOn4Rzy0uknQqzFN/view?usp=sharing "Demo Video Teaching")

## Overview of performed steps
<img src="overviewIntroduction.png" />

## Node Graph Demonstration
The current state of the robot is highlighted in the node graph. It can also be used to customize the flow of events by enabling / disabling states, by deleting links which will disable the respective state transition
or by creating new links (for example after the handover is performed, stop the application etc.).

<img src="imguiDemo.gif" />

## Content

This repo is a demonstration of my master's thesis, but it is not possible to make the code publicly available.

It includes the following tasks:
- **Body tracking**: Use body tracking algorithms to generate motion commands for a robotic camera arm such that the person being tracked remains inside the field of view of the camera. 
- **Gesture recognition**: Implement different modalities of gesture recognition, building on existing body tracking software to detect gestures such as the intention of a handover or hand signs to control the robot.
- **Robot motion**: Using trajectory optimization, generate collision-free motions needed for a handover (e.g. approach, retreat, follow, grasp, release) that are triggered depending on the gesture that is recognized and the teaching of new motions. Human-like robot motions were also implemented.
- **GUI**: A GUI and a Node Graph that are used to control and customize the behavior of the robot

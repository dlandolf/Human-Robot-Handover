## Introduction
Using a robotic camera arm mounted on a Yumi robot (a robot with 2 arms), the goal is to achieve natural human-robot handovers. To do so, different gesture recognition modalities (vision based and data driven) together with modern trajectory optimization algorithms are combined.

### Handover Demonstration

<img src="handoverDemo.gif" />

The camera arm first follows the face and starts to follow the hand that raises above the nose.
Then, a "Handover" gesture is performed (the open hand is reached out towards the robot), which means the person wants the robot to initialize a handover.
At that moment, the hand location is determined (using stereo vision). This location is indicated as a small red sphere in front of the robot in the visualization.
As a next step, a Trajectory Optimization is done, which avoids crashing into the hand of the human and ensures that the robot arm slowly approaches the hand from above and moves back to its initial position after the handover is performed.
The "Fist" gesture at the end tells the robot and the camera arm to stop their movements ("emergency stop").

### Camera Arm Demonstration

The camera arm first tracks and follows the face, and after raising one hand it starts to follow the respective hand.

<img src="cameraArmDemo.gif" />

### Node Graph Demonstration
The current state of the robot is highlighted in the node graph. It can also be used to customize the flow of events by enabling / disabling states, by deleting links which will disable the respective state transition
or by creating new links (for example after the handover is performed, stop the application etc.).

<img src="imguiDemo.gif" />


## Content

This repo is a demonstration of my master's thesis, but it is not possible to make the code publicly available.

It includes the following tasks:
- **Body tracking**: Use body tracking algorithms to generate motion commands for a robotic camera arm such that the person being tracked remains inside the field of view of the camera. 
- **Gesture recognition**: Implement different modalities of gesture recognition, building on existing body tracking software to detect gestures such as the intention of a handover or hand signs to control the robot.
- **Robot motion**: Using trajectory optimization, generate collision-free motions needed for a handover (e.g. approach, retreat, follow, grasp, release) that are triggered depending on the gesture that is recognized.
- **GUI**: A GUI and a Node Graph that are used to control and customize the behavior of the robot


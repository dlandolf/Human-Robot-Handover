## Introduction

This repo is a demonstration of my master's thesis, but it is not possible to make the code publicly available.

The goal is to  combine  different  gesture recognition  modalities  (vision  based  and  data  driven)  together  with  modern  trajectory  optimization algorithms to perform natural handovers from a robot to a human.

This includes the following tasks:
- **Body tracking**: Use body tracking algorithms to generate motion commands for a robotic camera arm such that the person being tracked remains inside the field of view of the camera. 
- **Gesture recognition**: Implement different modalities of gesture recognition, building on existing body tracking software to detect gestures such as the intention of a handover or hand signs to control the robot.
- **Robot motion**: Using trajectory optimization, generate collision-free motions needed for a handover (e.g. approach, retreat, follow, grasp, release) that are triggered depending on the gesture that is recognized.
- **GUI**: A GUI and a Node Graph that are used to control and customize the behavior of the robot

### Handover Demonstration

The Camera Arm first follows the face and starts to follow the hand that raises above the nose.
Then, a "Handover" gesture is performed (the open hand is reached out towards the robot), which means the person wants something from the robot.
At that moment, the hand location is determined (using stereo vision), which is indicated as small red sphere in the demo.
As a next step, a Trajectory Optimization is done, which avoids crashing into the hand of the human and ensures that the robot arm slowly approaches the hand from above and moves back to its initial position after the handover is performed.
The "Fist" gesture at the end tells the robot and the camera arm to stop their movements ("emergency stop").

The current state of the robot is highlighted in the node graph, which can also be used to customize the flow of events as shown in the last section.

<img src="handover_Small.gif" />

### Camera Arm Demonstration

The camera arm first tracks and follows the face, and after raising one hand it starts to follow the respective hand. In the end the "Fist" gesture tells the robot to stop.

<img src="cameraArmDemo_Small.gif" />

### Node Graph Demonstration

Some states in the node graph can be disabled / enabled if needed, links between states can be deleted which will disable the respective state transition or new links can be created in order to change the flow of events (for example after the handover is performed, stop the application etc.)

<img src="imguiDemo.gif" />
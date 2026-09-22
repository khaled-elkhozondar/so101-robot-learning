# Hardware

## System Overview

This project uses the Waveshare SO-ARM101 dual-arm kit in a leader-follower configuration.

The system consists of:

- A 6-DOF leader arm using ST3215 SE encoder-only servos
- A 6-DOF follower arm using powered ST3215 smart servos
- Two Waveshare Bus Servo Adapter boards
- Two USB cameras providing top and side views
- A powered USB hub
- Two 12 V, 5 A power supplies

During teleoperation, I physically move the leader arm. Its joint positions are read by the computer and sent as target positions to the follower arm.

During autonomous operation, the leader is removed from the control loop. The trained ACT policy uses the two camera observations and the follower's current joint state to predict the follower's next actions.
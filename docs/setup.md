# Software and Setup

## Development Environment

The project was developed on Ubuntu 24.04 using:

- Python 3.12
- Miniforge / Conda
- LeRobot 0.6.2
- PyTorch 2.11
- NVIDIA CUDA
- Git and GitHub

The robot software is based on Hugging Face LeRobot, with Feetech servo communication used for the SO-101 hardware.

## Robot Configuration

The follower and leader each use six joints:

| ID | Joint |
|---|---|
| 1 | Shoulder pan |
| 2 | Shoulder lift |
| 3 | Elbow flex |
| 4 | Wrist flex |
| 5 | Wrist roll |
| 6 | Gripper |

Each arm uses a shared servo bus. Servos on the same bus share communication wiring and baud rate but require unique IDs.

## Camera Configuration

Two USB cameras provide complementary observations:

- **Top camera:** global object and workspace position
- **Side camera:** approach and grasp geometry

Both cameras were configured at 640 × 480 resolution and 30 FPS.

## Control Modes

### Teleoperation

The leader arm provides joint-position targets to the follower:

Leader → Computer → Follower

### Autonomous Control

For autonomous operation, the leader is removed from the control loop:

Cameras + follower joint state → ACT policy → follower joint targets
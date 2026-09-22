# Experiments

## Task

The autonomous task was:

> Pick up a black rectangular perfume bottle and place it in a yellow bowl.

The bowl remained fixed while the bottle was tested across five regions of the workspace.

## Dataset 1

The first dataset contained 30 demonstrations.

The trained ACT policy struggled with grasp precision and object localization. Of the five tested workspace positions, only the middle position showed partial success; the other four positions resulted in misses.

This established a baseline and showed that successful teleoperation demonstrations alone did not guarantee reliable autonomous grasping.

## Dataset 2

The second dataset contained 50 demonstrations distributed across five workspace regions.

Performance improved substantially. The policy consistently approached the bottle, but several positions produced a systematic failure: the lower part of the gripper contacted the bottle instead of positioning the jaws around it.

Training for additional steps improved motion quality but did not fully eliminate the spatial grasp error.

## Failure Analysis

The repeated nature of the failure suggested that this was not simply random policy behavior.

Inspection of the recorded camera observations showed that the side camera could become heavily occluded by the arm and gripper during important parts of the grasp.

This led to the hypothesis that the policy lacked sufficiently clear visual information about grasp geometry in some regions of the workspace.

## Dataset 3

The side camera was repositioned to provide a wider and less occluded view.

Before recording the final dataset, a five-demonstration test dataset was captured with one demonstration from each workspace region. Contact-sheet inspection was used to verify visibility around the grasp phase.

The final Dataset 3 contained 50 demonstrations across the same five workspace regions.

At 10,000 training steps, motion was noticeably smoother, although some grasp-position errors remained.

Training was then continued to 30,000 steps.

At 30,000 steps, the policy successfully completed the task from all five tested workspace positions. The remaining observed failure mode was occasional contact with the removable bottle cap at one extreme position.

## Key Lesson

Increasing training time alone was not the complete solution.

Improving observation quality and reducing camera occlusion produced better data for the policy to learn from. The experiment demonstrated the importance of perception, dataset quality, controlled evaluation, and systematic failure analysis in robot learning.
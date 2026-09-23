# Evaluation

## Five-Position Evaluation

The policy was evaluated at five predefined bottle positions around the workspace.

| Policy | Position 1 | Position 2 | Position 3 | Position 4 | Position 5 |
|---|---|---|---|---|---|
| Dataset 1 — 30k | Miss | Miss | Partial success | Miss | Miss |
| Dataset 2 — 10k | Miss | Contact / miss | Partial success | Contact / miss | Success |
| Dataset 2 — 30k | Grasp alignment failure | Success | Variable | Grasp alignment failure | Success |
| Dataset 3 — 10k | Success | Contact / miss | Incorrect grasp alignment | Success | Success* |
| Dataset 3 — 30k | Success | Success | Success | Success | Success* |

\* Position 5 occasionally produced contact with the removable bottle cap.

## Final Result

Dataset 3 trained for 30,000 steps successfully completed pick-and-place from all five positions in the final evaluation.

The final policy also showed noticeably smoother and more fluid motion than earlier policies.

This five-position test is a small controlled evaluation rather than a statistically rigorous success-rate benchmark. Repeated trials per position would be required to estimate reliability more accurately.

## Experimental Progression

The three datasets show a clear progression in the development process:

**Dataset 1:** Initial baseline with poor generalisation across the workspace.

**Dataset 2:** Improved spatial localisation and reaching, but systematic grasp-alignment failures remained.

**Dataset 3:** Improved side-camera observability followed by a newly recorded dataset. After continued training to 30,000 steps, the policy completed the task from all five evaluated positions.

The key result was not simply that more training improved the robot. The experiments showed that a systematic perception problem could persist despite additional training, motivating a change to the observation setup and a new dataset.

## Remaining Limitations

- Position 5 occasionally produced contact with the removable bottle cap.
- Evaluation used the same object and general workspace as demonstration collection.
- Robustness to substantial lighting, object orientation, background, and camera changes was not systematically tested.
- Only one manipulation task was trained.
- Five test positions are insufficient to estimate a statistically meaningful overall success rate.

## Future Work

A future V2 could extend the system with:

- repeated-trial success-rate evaluation,
- unseen object positions and orientations,
- camera-ablation experiments,
- additional manipulation tasks,
- improved closed-loop policy execution,
- vision-language or language-conditioned control,
- drawing/tool-use experiments,
- ROS 2 and additional sensors.
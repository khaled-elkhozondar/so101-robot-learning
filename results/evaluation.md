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

This five-position test is a small controlled evaluation rather than a statistically rigorous success-rate benchmark. Repeated trials per position would be required to estimate reliability more accurately.

## Remaining Limitations

- Occasional interaction with the removable bottle cap at the extreme workspace position
- Evaluation was performed on the same object and general workspace used during demonstration collection
- Robustness to major lighting, object-orientation, background, and camera changes was not systematically tested
- The policy was trained for one manipulation task rather than general-purpose manipulation
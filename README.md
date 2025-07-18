# Soccer_player_mapping



---------------------------------------------
🎯 OBJECTIVE

The primary objective is to develop a robust system for sports analytics. It focuses on detecting, tracking, and consistently mapping player IDs across multiple camera views. This system aims to provide a unified view of player activity for deeper insights into game dynamics.

---------------------------------------------


---------------------------------------------
🛠️ SETUP INSTRUCTIONS

Step 1: Download and upload these files in a new folder :
- broadcast.mp4
- tacticam.mp4
- best.pt (YOLO model weights)

Step 2: Install dependencies

Run the requiremennts.txt file in terminal

---------------------------------------------
🚀 HOW IT WORKS

1. DETECTION & TRACKING
- YOLOv8 detects players frame by frame.
- SORT assigns unique IDs to each player in both videos.

2. FEATURE EXTRACTION
- Visual: RGB color histogram from player crops
- Spatial: Center coordinates of bounding boxes
- Temporal: Motion vectors (delta of position across frames)

3. PLAYER MATCHING
- Cosine similarity is computed across all features.
- tacticam_id → broadcast_id mapping is created.

4. ID VISUALIZATION
- Mapped IDs are drawn onto both videos.
- Output videos:
    • tacticam_mapped_output.mp4
    • broadcast_mapped_output.mp4

---------------------------------------------
📈 TECHNIQUES USED

Detection: YOLOv8 (custom-trained)
Tracking: SORT
Feature Extraction: RGB Histogram + Position + Motion
Matching: Cosine similarity of combined features

---------------------------------------------
🧪 RESULTS

✓ 27 players tracked in broadcast
✓ 28 players tracked in tacticam
✓ Output videos display consistent player IDs across both feeds

---------------------------------------------
⚠️ CHALLENGES

- Lighting and angle differences caused visual noise
- Players occluded or only visible in one camera
- SORT ID switching in crowded scenes

---------------------------------------------
💡 FUTURE WORK

- Try Deep SORT or Re-ID networks
- Sync camera time more precisely
- Use jersey OCR or pose estimation for stronger ID confidence

---------------------------------------------
--------------------------------------------
📎 SUBMISSION NOTES

- This project is self-contained and reproducible
- Code runs in `cross_camera_player_mapping.ipynb`
- Make sure videos and model weights are added manually

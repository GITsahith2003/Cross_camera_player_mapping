# 📊 Report: Soccer Player Mapping


---

## 🎯 Objective

The primary objective is to develop a robust system for sports analytics. It focuses on detecting, tracking, and consistently mapping player IDs across multiple camera views. This system aims to provide a unified view of player activity for deeper insights into game dynamics.
---

## 🔍 Approach & Methodology

1. **Player Detection & Tracking**
   - Used YOLOv8 (custom-trained) to detect players.
   - Applied SORT tracker to assign unique IDs within each video.
   - Tracked players across first 100 frames in both videos.

2. **Feature Extraction**
   - **Visual:** Color histogram (RGB) of player crops.
   - **Spatial:** Center coordinates of bounding boxes.
   - **Temporal:** Player movement (average velocity over frames).

3. **ID Matching**
   - Combined visual, spatial, and motion-based features.
   - Calculated similarity scores using cosine distance.
   - Matched each tacticam ID to the best broadcast ID.

4. **ID Reassignment & Visualization**
   - Reassigned consistent player IDs in both videos.
   - Visualized the results by overlaying bounding boxes and IDs.
   - Output: `tacticam_mapped_output.mp4` and `broadcast_mapped_output.mp4`

---

## 🧪 Techniques & Outcomes

| Technique Used         | Outcome                                      |
|------------------------|----------------------------------------------|
| YOLOv8 + SORT          | Smooth detection and tracking per video      |
| Color Histogram        | Helped differentiate players visually        |
| Motion Vectors         | Useful when appearance was similar           |
| Combined Similarity    | Produced the most reliable ID matches        |

---

## ⚠️ Challenges Encountered

- Varying lighting and jersey overlap made visual matching noisy.
- Players not always present in both views at the same time.
- SORT occasionally switched IDs for occluded players.

---

## ✅ Current Status

- Successfully tracked and mapped 27 players in `broadcast` and 28 in `tacticam`.
- Generated consistent player IDs across both feeds.
- Output visualization videos created.

---

## 🔜 Future Improvements

- Use Deep SORT or Re-ID networks for stronger feature embeddings.
- Add frame-by-frame synchronization across cameras.
- Include jersey number detection or pose estimation to refine matching.

---

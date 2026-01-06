## Effect of IoU Threshold on Object Detection Counts (YOLOv5)

This table compares the number and types of objects detected across different **IoU thresholds** used during Non-Maximum Suppression (NMS). It highlights how varying IoU values influence duplicate suppression, recall, and object counts, especially in crowded scenes.

| Image   |                   IoU = 0.30 |                   IoU = 0.45 |                       IoU = 0.70 |
| ------- | ---------------------------: | ---------------------------: | -------------------------------: |
| easy1   |                    8 persons |                    9 persons |                        9 persons |
| easy2   |     7 persons, 1 dog, 1 ball |     8 persons, 1 dog, 1 ball |         7 persons, 1 dog, 1 ball |
| easy3   |           5 persons, 2 balls |           6 persons, 2 balls |               5 persons, 2 balls |
| easy4   | 3 persons, skateboard, phone | 3 persons, skateboard, phone | **4 persons**, skateboard, phone |
| easy5   |               4 persons, bus |               4 persons, bus |                   4 persons, bus |
| easy6   |         2 persons, **1 tie** |        2 persons, **2 ties** |             2 persons, **1 tie** |
| hard1   |                    9 persons |                    9 persons |                        9 persons |
| hard2   |            9 persons, 1 ball |       **11 persons**, 1 ball |           **12 persons**, 1 ball |
| hard3   |          9 persons, suitcase |     **10 persons**, suitcase |         **10 persons**, suitcase |
| medium1 |                   16 persons |         **17 persons**, kite |                   **17 persons** |
| medium2 |                    8 persons |               **11 persons** |                       10 persons |
| medium3 |                    6 persons |                    6 persons |                        6 persons |
| medium4 |      6 persons, **3 chairs** |      6 persons, **4 chairs** |          **7 persons**, 3 chairs |

### Notes

* Lower IoU thresholds (e.g., 0.30) apply more aggressive suppression, often reducing duplicate detections but risking missed objects.
* Higher IoU thresholds (e.g., 0.70) preserve more overlapping boxes, increasing recall but also the likelihood of duplicates.
* The default IoU (0.45) represents a compromise, though it may still over-count in dense scenes.

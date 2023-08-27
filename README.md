# Multi Camera Visitor Tracking Sytem

## Objective

We aim to develop a system for measuring visitor wait times in specific scenarios. This system will help assess engagement levels, identify inefficiencies, and monitor interactions between customers and staff.

## Description

- Creating a visual representation of a designated area in front of the counter or showcase, referred to as a Region of Interest (ROI), and tracking the duration of people's presence within this area. The aim is to enhance and refine this process for optimal efficiency.

#### Test Case Description

- Input: Video (mp4) + ROI coordinates.
- Output: Video (mp4)

#### Find the attached link 

- Input Video: <https://drive.google.com/file/d/1NVN3a58yhML6cBKkDIMobUmcLnzfS_jT/view?usp=sharing>
- ROI: (1920,800) , straight line with x,y coordinates respectively
- Output Video: <https://drive.google.com/file/d/1eGRl-5cjn_vN0T5Ip0Ktn19ihlPJzia4/view?usp=drive_link>
  
## Approach

- Initial approach involves using a YOLO V8 model trained on COCO-dataset, also involving the usage of open-cv and ultralytics module.
- We initially plan to carry out object detection using YOLO on the entire frame.
- Then we write a script which counts the number of people entering and exiting the ROI in real time.
- The detailed approach is explained in the code.
   

## Points of Improvement

1. **Precision and Accuracy**: While YOLO V8 is a powerful model, it may not be the most accurate for visitor tracking, especially in scenarios with crowded or complex backgrounds. Consider experimenting with more advanced object detection models such as Faster R-CNN, RetinaNet, or EfficientDet, which might offer better accuracy.

2. **Tracking Algorithm**: Enhance the tracking algorithm to handle occlusions, overlapping, and quick movements more effectively. Incorporating a tracking algorithm like DeepSORT (Deep Learning for Object Tracking with Simultaneous Detection and Tracking) could improve the overall tracking accuracy and consistency.

3. **ROI Refinement**: Fine-tune the definition of the Region of Interest (ROI) based on the specific scenario. Adaptive ROIs that can be adjusted dynamically could account for variations in visitor behavior and optimize the tracking process.

4. **False Positive/Negative Handling**: Implement techniques to reduce false positives and negatives during object detection. This could involve applying confidence thresholds, non-maximum suppression, or post-processing methods to filter out erroneous detections.

5. **Real-time Performance**: Evaluate the system's performance in real-time scenarios. Ensure that the processing speed of the chosen model and tracking algorithm is sufficient to handle video streams with varying frame rates.

## USING state-of-the-art (SOTA) models

1. **Object Detection**: Consider adopting models like EfficientDet or Detectron2's RetinaNet. These models offer advanced architecture designs and have shown superior accuracy and efficiency compared to YOLO in recent benchmarks.

2. **Tracking**: Instead of relying solely on traditional tracking algorithms, incorporate deep learning-based trackers such as FairMOT or Tracktor, which leverage the temporal information for better tracking, especially in crowded scenes.

3. **Feature Fusion**: Explore models that integrate both object detection and tracking in an end-to-end manner. This can potentially improve the system's robustness by allowing better incorporation of temporal information during detection and tracking stages.


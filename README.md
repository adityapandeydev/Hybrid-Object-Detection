# Hybrid Object Detection Models

This repository contains two Python scripts demonstrating the use of hybrid object detection models combining YOLOv5 and Faster R-CNN. These models are fine-tuned to detect vehicles but can be adapted for other object detection tasks.

## Overview

1. **initial.py**
   - Implements a pipeline where YOLOv5 is used for initial object detection, followed by Faster R-CNN for enhanced detection within the cropped regions identified by YOLO.
   - Focuses on processing images from a custom dataset and visualizing the results.

2. **main.py**
   - Demonstrates a more integrated hybrid approach combining YOLOv5 and Faster R-CNN.
   - Includes:
     - IoU-based merging of detections from both models.
     - Application of Non-Maximum Suppression (NMS) to refine final detections.
     - Visualization of results from YOLO, Faster R-CNN, and the hybrid model side by side.

## Requirements

- Python 3.7 or above
- Required libraries:
  - `torch`
  - `ultralytics`
  - `torchvision`
  - `opencv-python`

Install the required libraries using:
```bash
pip install torch ultralytics torchvision opencv-python
```

## Usage

1. **Setup:**
   - Ensure you have the pretrained YOLOv5 model file (`yolov5su.pt`) and a custom dataset of images.
   - Update the `dataset_dir` path in `initial.py` and the `image_path` in `main.py` to point to your dataset.

2. **Run Scripts:**
   - Execute `initial.py` for a basic detection pipeline:
     ```bash
     python initial.py
     ```
   - Execute `main.py` for hybrid detection with IoU-based merging and NMS:
     ```bash
     python main.py
     ```

3. **Visualization:**
   - View the results in separate windows displaying outputs from YOLO, Faster R-CNN, and the hybrid model.

## Key Features

- **YOLOv5**:
  - Fast, real-time object detection with bounding boxes and confidence scores.
- **Faster R-CNN**:
  - Accurate region-based detection for refining YOLO results.
- **Hybrid Approach**:
  - Combines the strengths of both models using IoU for merging and NMS for final detection refinement.

## Notes

- Ensure the image files are properly loaded; paths should be valid.
- You may adjust the confidence threshold and IoU values in `main.py` for optimal results.

## Acknowledgements

- YOLOv5 by [Ultralytics](https://github.com/ultralytics/yolov5).
- Faster R-CNN from PyTorch's `torchvision` library.

Feel free to modify the scripts to suit your use case!


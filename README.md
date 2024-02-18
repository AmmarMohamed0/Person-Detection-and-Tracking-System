# Person Detection and Tracking System

## Overview
This project implements a real-time person detection and tracking system using computer vision techniques. It detects people in a given video feed, tracks their movements, and counts the number of people within a specified region of interest (ROI).

## Code Explanation

### Dependencies
- **Python 3**: The programming language used for development.
- **OpenCV**: Open Source Computer Vision Library for image processing tasks.
- **PyTorch**: Deep learning framework used for object detection with the YOLOv5 model.
- **NumPy**: Library for numerical computing in Python.

### Installation
1. Clone this repository to your local machine.
2. Install the required dependencies using pip:

## Code Structure

The codebase consists of the following main components:

1. **`person_detection_tracking.py`**: This is the main Python script responsible for implementing person detection, tracking, and counting logic. It contains the primary execution logic and coordinates the interaction between the object detection model, object tracker, and video feed.

2. **`tracker.py`**: This file contains the implementation of the Tracker class, which is responsible for tracking objects (in this case, people) across consecutive frames of the video feed. It assigns a unique identifier to each tracked object and predicts its position in the subsequent frames.

3. **`cctv.mp4`**: This is an example video file used for testing the system. You can replace it with your own video feed for real-world applications.

## How it Works

The system operates as follows:

1. **Person Detection**:
   - The YOLOv5 object detection model is used to detect people in each frame of the video feed. It outputs bounding boxes around detected individuals.

2. **Object Tracking**:
   - Detected person coordinates from the object detection step are fed into the object tracker implemented in `tracker.py`.
   - The object tracker maintains the state of each detected person across frames by associating them with a unique ID and predicting their positions.

3. **Region of Interest (ROI)**:
   - A region of interest (ROI) is predefined within the video frame. This ROI represents the area where people are being monitored or counted. It is defined using polygonal lines.

4. **Counting People**:
   - The system keeps track of the number of people within the ROI.
   - Whenever a person is detected within the ROI, their unique ID is added to a set (`count`) to prevent duplicate counting.
   - The count of unique IDs in the set represents the number of people within the ROI at any given time.
   - This count is displayed on the video feed in real-time.

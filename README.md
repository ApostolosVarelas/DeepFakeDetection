# Deep Fake Detection System

A deep learning-based system for detecting deepfake videos using frame-level analysis with various state-of-the-art models.

## Dataset

The system uses the FaceForensics dataset available on Kaggle:  
:link: [FaceForensics Dataset](https://www.kaggle.com/datasets/greatgamedota/faceforensics)

## Models Implemented

- ResNet50
- Xception
- Swin Transformer

## System Logic

1. **Video Processing**:
   - Split input video into equally spaced frames (fixed interval) to maximize temporal coverage.
   - Ensures uniform sampling across the entire video duration
2. **Detection**:
   - Train and predict on individual frames
   - Combine frame-level predictions to make video-level prediction

## Frame Processing Methods

Two approaches for processing video frames:

1. **No Splitting**:
   - Uses complete frame
2. **Face Crop**:
   - Detects and crops only the face region in each frame

## Experiments Conducted

The system was evaluated with four experimental configurations:

1. Train on face-frames → Test on face-frames
2. Train on face-frames → Test on complete-frames
3. Train on complete-frames → Test on complete-frames
4. Train on complete-frames → Test on face-frames

## Evaluation Metrics

The system was evaluated using multiple metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- Matthews Correlation Coefficient (MCC)
- Average Precision
- Equal Error Rate (EER)

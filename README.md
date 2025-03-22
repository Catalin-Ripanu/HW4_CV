# Panorama Image Stitching with Feature Detection

This repository implements advanced panorama creation techniques using feature detection, image matching, and homography-based stitching. The project focuses on creating high-quality panoramas from sequences of overlapping images using computer vision techniques.

## Features

### Image Extraction and Processing
- Extracts multiple images from a single source file using contour detection
- Maintains original image quality and color fidelity through proper RGB color space handling
- Supports automatic resizing to target dimensions (1080x1920)
- Implements intelligent sorting of extracted images based on spatial position

### Feature Detection and Matching
- Implements SIFT (Scale-Invariant Feature Transform) for robust feature detection
- Uses FLANN-based feature matching with ratio test filtering
- Provides optimized matching parameters for better panorama alignment
- Supports large sets of overlapping images

### Panorama Stitching
- Automated panorama creation from multiple input images
- Features include:
  - SIFT feature detection and description
  - FLANN-based feature matching
  - Homography computation using RANSAC
  - Perspective warping and blending
- Supports various panorama types:
  - Full sequence stitching
  - Mid-sequence extraction
  - Reverse sequence stitching

## Requirements
- Python 3.x
- OpenCV (cv2)
- NumPy
- Matplotlib
- SciPy

## Implementation Details

### Image Extraction
- Uses contour detection to identify individual images
- Implements intelligent sorting based on spatial position
- Maintains color fidelity through proper color space conversion (BGR to RGB)
- Supports automatic resizing while preserving aspect ratio

### Corner Detection
- Harris Corner Detection parameters:
  - HARRIS_K = 0.04 (Harris corner response parameter)
  - Dynamic neighborhood sizing based on image count
  - Threshold = 0.01 (for corner response filtering)
  - Non-maximum suppression radius = 1

### Panorama Stitching
- Feature Detection:
  - Uses SIFT (Scale-Invariant Feature Transform)
  - Adaptive feature matching with ratio test
  - RANSAC-based homography estimation
- Image Blending:
  - Perspective warping with computed homographies
  - Maximum intensity blending for seamless transitions
  - Automatic cropping of empty borders

## Output
- Generates visualizations for corner detection comparisons
- Creates panorama images with automatic cropping
- Saves results in both PNG and SVG formats
- Provides interactive display of results using matplotlib

## Limitations and Considerations
- Input images should have sufficient overlap for panorama stitching
- Corner detection parameters may need adjustment for different image types
- Memory usage scales with image size and count
- Processing time depends on image complexity and feature count


## Mouth Open Close Detection

# Mouth Open Detection Using Face Recognition

This project detects whether a person's mouth is open using face recognition techniques in real-time (via webcam) and for local images. The program leverages the `face_recognition` library and OpenCV to capture facial landmarks and calculates mouth and lip heights to determine if the mouth is open.

## Features

- Real-time mouth open detection using webcam.
- Local image mouth open detection.
- Basic face recognition and labeling of faces.
- Uses OpenCV for video processing and face_recognition for face landmark detection.
  
## Installation

### Prerequisites

Make sure you have Python 3 installed. The necessary libraries are listed below.

### Install Required Packages

1. Clone the repository:

   ```bash
   git clone https://github.com/VRAJ-07/Mouth_Open_Close_Detection
   cd Mouth_Open_Close_Detection
   ```

2. Install the required Python packages using `pip`:

   ```bash
   pip install face_recognition opencv-python numpy Pillow
   ```

> **Note**: The `face_recognition` library requires `dlib` to be installed, which may require additional setup for certain operating systems like macOS or Windows.

3. Install any other missing dependencies manually as needed:

   ```bash
   pip install Click
   ```

## Usage

### Live Capture (Real-time Webcam Detection)

To use the mouth open detection in real-time via webcam:

1. Run the `mouth_open_detection_webcam.py` script:

   ```bash
   python mouth_open_detection_webcam.py
   ```

2. The program will launch the default webcam and detect if any detected person's mouth is open or closed. Press `q` to quit.

### Local Images (Image Processing)

1. Run the `mouth_open_detection_images.py` script:

   ```bash
   python mouth_open_detection_images.py
   ```

2. Select an image file using the provided file dialog box. The program will process the image and print whether the mouth is open or closed for the detected faces.

## Mouth Open Algorithm

The `is_mouth_open` function in both the webcam and image scripts works as follows:

- The `face_recognition` library is used to detect facial landmarks, specifically the top and bottom lips.
- The heights of the top lip and bottom lip are calculated, along with the mouth's height.
- If the mouth height is greater than a specified ratio (default `0.5`) of the smaller lip height, the program detects the mouth as open.

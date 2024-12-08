# Automatic-Attendance-System-using-Face-Recognition

This project implements an **Automated Attendance System** that uses face recognition to mark attendance in an Excel spreadsheet. It captures live video feed, detects faces in real-time, identifies known individuals, and records their presence in an Excel file.

## Features
- **Face Recognition**:
  - Uses the `face_recognition` library for accurate face detection and identification.
  - Matches faces in the live feed against a predefined database of known faces.
- **Excel Integration**:
  - Automatically logs attendance in an Excel file with the name of the detected individual and their attendance status.
- **Real-time Processing**:
  - Processes video input in real-time using OpenCV.
- **Dynamic Detection**:
  - Avoids duplicate entries by ensuring each individual is marked present only once per session.

## How It Works
1. **Face Database**:
   - Preload face encodings from images stored in a folder (e.g., `images/`).
   - Each image file's name is used as the identifier (e.g., `John_Doe.jpg` → `John_Doe`).

2. **Real-Time Detection**:
   - Captures video from the webcam.
   - Detects and identifies faces using the `face_recognition` library.

3. **Attendance Logging**:
   - If a detected face matches a known encoding, the individual's name is added to an Excel sheet along with their attendance status (`1` for present).
   - Ensures no duplicate entries for the same session.

4. **Excel Output**:
   - Saves attendance records in an `output.xlsx` file for easy access and further processing.

## Requirements
### Libraries
- Python 3.8+
- Required Python Libraries:
  - `face_recognition`
  - `cv2` (OpenCV)
  - `numpy`
  - `openpyxl`

### Installation
1. Install Python dependencies:
   ```bash
   pip install face_recognition opencv-python numpy openpyxl

2. Install dlib (required by face_recognition):
   ```bash
   pip install dlib
3. Install CMAKE software:
    - Windows:
      1. Download CMake from https://cmake.org/download/.
      2. Install and add CMake to your system's PATH during setup.
      3. Verify installation:
        ```bash
            cmake --version
    - Linux (Ubuntu/Debian):
        ```bash
            sudo apt-get install cmake
    - macOS: 
        ```bash
            brew install cmake

### Usage
1. Prepare Face Encodings:
    - Place the images of known individuals in a folder named images/.
    - Ensure each image file is named with the individual's identifier (e.g., John_Doe.jpg).

2. Run the Script:
    - Execute the main script:
      ```bash
      python attendance_system.py

3. Mark Attendance:
    - The script will:
      - Open a webcam feed.
      - Detect and identify faces in real-time.
      - Log attendance in output.xlsx.

4. Exit the Script:
    - Press the Esc key to terminate the video feed and save the Excel file.
  
### Future Enhancements
  - Add a GUI for easier user interaction.
  - Integrate with cloud services for remote attendance tracking.
  - Implement support for multiple sessions and timestamped entries.

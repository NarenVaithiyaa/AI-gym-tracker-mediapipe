# Real-Time Pose Estimation

A real-time human pose estimation application using MediaPipe and OpenCV. This project detects and visualizes human pose landmarks from webcam feed in real-time.

## Features

- 🎥 Real-time pose detection from webcam
- 🦴 33-point pose landmark detection
- 🎨 Visual skeleton overlay with customizable colors
- ⚡ High-performance processing using MediaPipe
- 🖥️ Cross-platform compatibility

## Demo

The application captures video from your webcam and overlays detected pose landmarks and connections in real-time. Press 'Ctrl + C' to quit the application.

## Requirements

- Python 3.7+
- Webcam/Camera
- Windows/macOS/Linux

## Installation

1. Clone this repository:
```bash
git clone https://github.com/NarenVaithiyaa/AI-gym-tracker-mediapipe.git
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
```

3. Activate the virtual environment:
   - **Windows:**
     ```bash
     venv\Scripts\activate
     ```
   - **macOS/Linux:**
     ```bash
     source venv/bin/activate
     ```

4. Install the required dependencies:
```bash
pip install -r requirements.txt
```

## Usage

Run the pose estimation application:

```bash
python pose_est.py
```

### Controls
- **Ctrl + C'**: Quit the application
- The application will automatically detect poses when a person is visible in the camera frame

## Dependencies

- `mediapipe==0.10.14` - Google's MediaPipe framework for pose detection
- `opencv-python` - Computer vision library for video capture and display
- `numpy` - Numerical computing library
- `protobuf==3.20.3` - Protocol buffers for data serialization

## How It Works

1. **Video Capture**: The application captures frames from your default camera
2. **Preprocessing**: Converts BGR (OpenCV format) to RGB (MediaPipe format)
3. **Pose Detection**: Uses MediaPipe's Pose model to detect 33 pose landmarks
4. **Visualization**: Draws detected landmarks and connections on the frame
5. **Display**: Shows the processed frame with pose overlay

## Pose Landmarks

The application detects 33 key body landmarks including:
- Face (nose, eyes, ears)
- Upper body (shoulders, elbows, wrists)
- Lower body (hips, knees, ankles)
- Additional points for improved accuracy

## Configuration

You can modify the pose detection parameters in `pose_est.py`:

```python
mp_pose.Pose(
    min_detection_confidence=0.5,  # Minimum confidence for pose detection
    min_tracking_confidence=0.5    # Minimum confidence for pose tracking
)
```

### Color Customization

Customize landmark and connection colors:

```python
mp_drawing.DrawingSpec(color=(245,117,66), thickness=2, circle_radius=2)  # Landmarks
mp_drawing.DrawingSpec(color=(245,66,230), thickness=2, circle_radius=2)  # Connections
```

## Troubleshooting

### Common Issues

1. **Camera not found**: Ensure your webcam is connected and not being used by another application
2. **Poor detection**: Ensure good lighting and that the full body is visible in the frame
3. **Performance issues**: Try reducing the video resolution or adjusting confidence thresholds

### Error Messages

- **"Cannot open camera"**: Check if your camera is working and not in use by another app
- **Import errors**: Ensure all dependencies are installed correctly
- **Protobuf conflicts**: There might be version conflicts - the app should still work despite warnings

## Performance

- **FPS**: Typically 15-30 FPS depending on hardware
- **Latency**: Low latency real-time processing
- **CPU Usage**: Optimized for CPU inference using TensorFlow Lite

## Contributing

1. Fork the repository 
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [MediaPipe](https://mediapipe.dev/) by Google for the pose estimation model
- [OpenCV](https://opencv.org/) for computer vision utilities
- MediaPipe team for providing excellent documentation and examples

## Future Enhancements

- [ ] Save pose data to file
- [ ] Multiple person detection
- [ ] Pose classification (sitting, standing, etc.)
- [ ] Exercise counting functionality
- [ ] Video file input support
- [ ] REST API interface

---

⭐ If you found this project helpful, please give it a star!

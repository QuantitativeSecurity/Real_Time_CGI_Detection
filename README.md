Real-time Blue Object Detector

This script uses the OpenCV library to capture video from the default camera and detect blue objects in real-time. It achieves this by converting the captured frames into the HSV (Hue, Saturation, Value) color space and then filtering out blue colors using a predefined range.
Features:

    Real-time Detection: The script captures video frames from the default camera and processes them in real-time to detect blue objects.
    HSV Color Filtering: Converts the BGR color space of the captured frame to HSV and uses it for more accurate color detection.
    Interactive Display: Shows the detected blue objects in a window, allowing users to visualize the detection results.

Usage:

    Ensure you have the opencv-python library installed. You can install it via pip:

    pip install opencv-python

    Run the script. A window named 'Result' will appear, showing the real-time detection of blue objects.
    To stop the script and close the window, press the 'q' key on your keyboard.

Code Structure:

    cap = cv2.VideoCapture(0): Initializes the video capture from the default camera.
    hsv = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV): Converts the BGR frame to the HSV color space.
    mask = cv2.inRange(hsv, lower_blue, upper_blue): Creates a binary mask where blue colors within the specified range are white, and all other colors are black.
    result = cv2.bitwise_and(frame, frame, mask=mask): Uses the binary mask to keep only the blue parts of the original frame.
    cv2.imshow('Result', result): Displays the result in a window.
    cv2.waitKey(1) & 0xFF == ord('q'): Continuously waits for the 'q' key to be pressed to terminate the script.

Important Notes:

    The range for blue detection is defined by the lower_blue and upper_blue arrays. You can adjust these values to detect different shades of blue or even other colors.
    Ensure that you have a camera connected and accessible by the script. If using an external webcam, make sure it's set as the default or adjust the index in cv2.VideoCapture() accordingly.
    The window displaying the results will scale based on the resolution of the captured video. Ensure you have enough screen space for a clear view.

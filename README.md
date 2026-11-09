# Colour Detection with OpenCV

A small computer vision program that uses the webcam to detect a yellow object
and draw a box around it in real time.

This is my first computer vision project, made as practice for the
Data Science block of the Master Next Level Engineering (Hogeschool Utrecht).

## What it does
- Opens the webcam and shows the live video
- Converts each frame from BGR to HSV colour space
- Makes a mask of all yellow pixels
- Finds the biggest yellow area and draws a green box around it
- Shows a second window with the mask (what the computer "sees")

## Requirements
- Python 3
- OpenCV and NumPy

Install with:
    python3 -m pip install opencv-python numpy

## How to run
    python3 webcam.py

Click the video window and press `q` to quit.
On a Mac, `CAMERA_INDEX = 1` uses the built-in camera
(`0` may be an iPhone via Continuity Camera).

## How it works
1. **HSV colour space:** separates the colour (hue) from brightness,
   so a colour is easier to detect than in normal BGR.
2. **Mask:** `cv2.inRange` makes every yellow pixel white and everything else black.
3. **Box:** the biggest white area is found with contours and a rectangle is drawn around it.

## Limitations
- Sensitive to lighting: too much light makes colours look pale and detection fails.
- Detects only one colour, and only the biggest object of that colour.
- Yellow objects in the background can confuse it.

A trained model (for example YOLO) would be more robust, which is the next step.

## Sources
- Colour detection approach based on: <YouTube video title>, <channel name>, <link>
- Code debugged and extended with help from Claude (Anthropic, Opus 5.5), November 2026

## Author
Emmanuel Ukana
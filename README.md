# Ex02 - Image_Acqusition-_using_Web_Camera
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import necessary libraries (cv2).
### Step 2:
Open the camera using cv2.VideoCapture(0).
### Step 3:
Enter a loop to continuously capture frames from the camera.
### Step 4:
Resize each frame, create a blank image, divide it into quadrants, and assign resized frames accordingly. Rotate specific frames if needed.
### Step 5:
Display processed frames on the screen using cv2.imshow(), and continuously check for a termination signal (e.g., pressing 'q' key) to break out of the loop.

## Program:
### Developed By: MAnoj Kumar G
### Register No: 212222230078
## i) Write the frame as JPG file
```python
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("image.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Video Capture',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
<img src="https://github.com/Janarthanan2/Image_Acqusition-_using_Web_Camera/assets/119393515/3800b549-d025-46b3-b391-07e389b900b0" width=50%>

### ii) Display the video'
<img src="https://github.com/Janarthanan2/Image_Acqusition-_using_Web_Camera/assets/119393515/0ee76675-51ab-4ddd-a1ee-2a59c1193571" width=50%>

### iii) Display the video by resizing the window
<img src="https://github.com/Janarthanan2/Image_Acqusition-_using_Web_Camera/assets/119393515/a1cfc4d4-dd44-4691-9992-2035fbb0affd" width=50%>

### iv) Rotate and display the video
<img src="https://github.com/Janarthanan2/Image_Acqusition-_using_Web_Camera/assets/119393515/42ec68d0-8c4a-4f07-8eba-ff63354c7b95" width=50%>

## Result:
Thus the image is accessed from webcamera and displayed using openCV.

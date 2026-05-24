# EXP-2-Record-Image Acquisition using Web Camera

## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations. i) Write the frame as JPG ii) Display the video iii) Display the video by resizing the window iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm:
Step 1:
Use cv2.VideoCapture(0) to access web camera.

Step 2:
Use cv2.imread to read the video or image.

Step 3:
Use cv2.imwrite to save the image.

Step 4:
Use cv2.imshow to show the video.

Step 5:
End the program and close the output video window by pressing 'q'.

## Developed By: Vedhanth H

## Register No: 212224240181
## Program:
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```
```
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
```
```
captured_image = cv2.imread('captured_frame.jpg')
```
```
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## Output:
### i) Write the frame as JPG image
<img width="661" height="509" alt="image" src="https://github.com/user-attachments/assets/9338b13f-33c3-41dc-9e63-011ebc916344" />


### ii) Display the video by resizing the window

<img width="638" height="484" alt="image" src="https://github.com/user-attachments/assets/5911b20d-e5dc-493c-853a-ec93b90cb8b3" />

### iii)
<img width="341" height="499" alt="image" src="https://github.com/user-attachments/assets/f9f221b6-616f-4aab-b0d9-432eaf9b3444" />


#### iv) Rotate and display the video

<img width="381" height="493" alt="image" src="https://github.com/user-attachments/assets/b58ec273-9ca5-4e13-a744-49db887f693d" />


## Result:
Thus the image is accessed from webcamera and displayed using openCV.

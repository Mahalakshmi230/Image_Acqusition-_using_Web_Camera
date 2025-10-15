
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1: 
Initialize the webcam by creating a cv2.VideoCapture object to start video capture.

### Step 2: 
Capture a frame from the webcam using ret, frame = cap.read().

### Step 3: 
Preprocess the captured frame as needed (e.g., resizing, rotating, or converting from BGR to RGB).

### Step 4: 
Display the processed frame using matplotlib.pyplot.imshow(), ensuring the axis is turned off and the previous output is cleared.

### Step 5: 
Release the webcam resource with cap.release() once frame capturing or display is complete.

## Program:

### Developed By: Mahalakshmi R
### Register No: 212223230116

```
i) Write the frame as JPG file

import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

```
ii) Display the video
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
iii) Display the video by resizing the window
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
iv) Rotate and display the video
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

## Output

### i) Write the frame as JPG image
</br>
<img width="536" height="423" alt="Screenshot 2025-10-15 215706" src="https://github.com/user-attachments/assets/29466e44-86ca-4b22-b5c5-d303fbd902af" />


</br>


### ii) Display the video
</br>
<img width="556" height="419" alt="Screenshot 2025-10-15 215713" src="https://github.com/user-attachments/assets/adeb1fcf-1331-49b9-bf9f-2e06b1094964" />

</br>


### iii) Display the video by resizing the window
</br>
<img width="298" height="411" alt="Screenshot 2025-10-15 215720" src="https://github.com/user-attachments/assets/bed9b4d9-c382-40c2-ba09-0291275de89c" />

</br>



### iv) Rotate and display the video
</br>
<img width="375" height="415" alt="Screenshot 2025-10-15 215725" src="https://github.com/user-attachments/assets/20090625-186c-416e-aa26-3bfda8c283c1" />

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.

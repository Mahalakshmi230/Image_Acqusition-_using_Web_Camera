
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
<img width="508" height="404" alt="Screenshot 2025-10-09 155748" src="https://github.com/user-attachments/assets/89516387-a2cb-41c5-ab14-deb52a7702aa" />

</br>


### ii) Display the video
</br>
<img width="505" height="376" alt="Screenshot 2025-10-09 155801" src="https://github.com/user-attachments/assets/99828683-ab92-4faf-bb75-172aeb8378b6" />

</br>


### iii) Display the video by resizing the window
</br>
<img width="254" height="378" alt="Screenshot 2025-10-09 155808" src="https://github.com/user-attachments/assets/a04b62b2-564b-47c3-9ebf-ea26ff1f2b58" />

</br>



### iv) Rotate and display the video
</br>
<img width="280" height="378" alt="Screenshot 2025-10-09 155815" src="https://github.com/user-attachments/assets/799ae6a7-e346-4ee0-a764-5dbd4f104cdf" />

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.

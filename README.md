# Experiment 2: Image Acquisition Using Web Camera
### Aim :
To acquire an image using a web camera, save the captured frame as a JPG file, display the video stream, and display the video by resizing the frames using Python and OpenCV.

### Requirements :
- Computer or laptop
- Web camera (built-in or external)
Software requirements
- Python
- Jupyter Notebook / Anaconda

### Procedure :
1. Import the required libraries: OpenCV, Matplotlib, IPython display, and time.
2. Open the web camera using cv2.VideoCapture(0).
3. Capture and save an image: Read a frame from the camera and save it as ex.jpg using cv2.imwrite().
4. Display the captured image: Read the saved JPG file and display it using Matplotlib.
5. Display the video: Capture and display 50 consecutive frames from the web camera. Convert each frame from BGR to RGB format before displaying it.
6. Resize the video: Resize each captured frame to 100 × 150 pixels using cv2.resize() and display it.
7. Rotate the video: Rotate each captured frame by 90 degrees clockwise using cv2.rotate() and display the rotated frame.
8. Release the web camera after completing the image and video acquisition operations.

### Program :

### Step1 : Write the frame as JPG file

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("ex.jpg", frame)
cap.release()

captured_image = cv2.imread('ex.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('on')
plt.show()
```

### Step2 : Display the video

```python
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

### Step3 : Display the video by resizing the window

```python
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

### Step4 : Rotate and display the video

```python
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

### Output : 

### Step1 : Write the frame as JPG file

<img width="385" height="292" alt="image" src="https://github.com/user-attachments/assets/abfed144-a414-431f-a32b-7be46fa4916c" />

### Step2 : Display the video












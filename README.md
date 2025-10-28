## 🏋️‍♂️ Pose-Based Bicep Curl Counter

A **real-time exercise tracker** built using **OpenCV**, **MediaPipe**, and **NumPy** that detects human body pose through your webcam and counts bicep curls based on elbow angle.

---

### 🚀 Features

* Real-time **pose detection** using MediaPipe.
* **Angle calculation** between shoulder, elbow, and wrist.
* Automatic **rep counting** for left-hand bicep curls.
* On-screen display of:

  * Detected angle
  * Current stage (`up` / `down`)
  * Total repetitions

---

### 🧠 How It Works

1. MediaPipe Pose detects 33 body landmarks.
2. The code tracks **shoulder**, **elbow**, and **wrist** positions.
3. It computes the **elbow angle** using the arctangent formula:
   [
   \text{angle} = |\arctan2(y_3 - y_2, x_3 - x_2) - \arctan2(y_1 - y_2, x_1 - x_2)|
   ]
4. When the arm moves from **straight (angle > 160°)** to **fully bent (angle < 30°)**, one rep is counted.

---

### 🧩 Requirements

Install the required libraries before running:

```bash
pip install opencv-python mediapipe numpy
```

---

### ▶️ Run the Program

1. Save the code as `bicep_curl_counter.py`.
2. Run in terminal:

   ```bash
   python bicep_curl_counter.py
   ```
3. The webcam will open.

   * Press **‘q’** to quit.
   * Watch your **reps** and **angles** display live on screen.

---

### ⚙️ Customization

* You can track the **right arm** by replacing all instances of `LEFT_...` with `RIGHT_...`.
* Adjust angle thresholds (`160` and `30`) to fine-tune sensitivity.
* Change the font and rectangle positions to better fit your screen.

---

### 🧾 Example Output

When you start curling, you’ll see:

```
REPS: 3
STAGE: up
ANGLE: 28.5
```

…and the video feed will show your skeleton landmarks and elbow angle in real-time.

---

### 💡 Future Improvements

* Add both arms and automatic side detection.
* Integrate calorie estimation.
* Export rep counts and session data to a CSV file.



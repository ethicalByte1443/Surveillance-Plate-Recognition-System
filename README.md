

# 🚗 Automatic License Plate Recognition (ALPR / ANPR)

High-accuracy, developer-friendly **license plate recognition software** powered by deep learning. Supports images, video streams, and real-time camera feeds.

---

## 🔥 Key Features

* ✅ Works with **blurry, dark, low-res images** from tough angles and all vehicle types.
* ✅ Supports **vehicle type, make, model, color**, and orientation recognition.
* ✅ Optimized for 90+ countries including:

  * USA (All 50 States)
  * India
  * Brazil
* ✅ Available via REST API or local SDK.
* ✅ Fast response time: **as low as 21 ms**.
* ✅ Supports Linux, Windows, macOS, Jetson, Raspberry Pi, Kubernetes, and more.

---

## 📸 License Plate Recognition from Images (Snapshot)

### 1. **Get Started**

```bash
# 1. Clone the repo
git clone https://github.com/parkpow/deep-license-plate-recognition.git
cd deep-license-plate-recognition

# 2. Install dependencies
pip install requests pillow
```

### 2. **Run Single Image Recognition**

```bash
python plate_recognition.py --api-key MY_API_KEY /path/to/vehicle.jpg
```

**Response Example:**

```json
[
  {
    "processing_time": 30.143,
    "results": [
      {
        "box": {
          "xmin": 56,
          "ymin": 23,
          "xmax": 951,
          "ymax": 518
        },
        "plate": "tn8f4089",
        "region": {
          "code": "in",
          "score": 0.893
        },
        "score": 0.938,
        "candidates": [
          {
            "score": 0.938,
            "plate": "tn8f4089"
          },
          {
            "score": 0.819,
            "plate": "tn8f40b9"
          },
          {
            "score": 0.819,
            "plate": "tn8f4o89"
          },
          {
            "score": 0.819,
            "plate": "tnbf4089"
          },
          {
            "score": 0.7,
            "plate": "tn8f4ob9"
          },
          {
            "score": 0.7,
            "plate": "tnbf40b9"
          },
          {
            "score": 0.7,
            "plate": "tnbf4o89"
          },
          {
            "score": 0.582,
            "plate": "tnbf4ob9"
          }
        ],
        "dscore": 0.918,
        "vehicle": {
          "score": 0.0,
          "type": "Unknown",
          "box": {
            "xmin": 0,
            "ymin": 0,
            "xmax": 0,
            "ymax": 0
          }
        }
      }
    ],
    "filename": "1044_Fb6vS_14inch-3mm-vehicle-number-plate.jpg",
    "version": 1,
    "camera_id": null,
    "timestamp": "2025-07-23T10:44:22.632997Z",
    "image_width": 1000,
    "image_height": 565
  }
]
```

### 3. **Run for Specific Regions**

```bash
python plate_recognition.py --api-key MY_API_KEY --regions fr --regions it /path/to/car.jpg
```

### 4. **Batch Process Multiple Files**

```bash
python plate_recognition.py --api-key MY_API_KEY /path/to/*.jpg
```

### 5. **Use with Local SDK (No Internet Required)**

```bash
python plate_recognition.py --sdk-url http://localhost:8080 /path/to/vehicle.jpg
```

---

## 📹 License Plate Recognition from Video or Live Camera (Stream)

* Handles up to **4 camera feeds** on mid-range PCs.
* Outputs results via **CSV or Webhooks**.
* Compatible with Linux, Windows, macOS, Jetson.

More info: [Stream Setup Guide](https://platerecognizer.com/stream/?utm_source=github&utm_medium=website)

---

## 🛑 Blur or Redact License Plates

Detect and blur license plates using:

```bash
python number_plate_redaction.py --api-key MY_API_KEY vehicles.jpg
```

### Optional Arguments:

* `--split-image`: Improves accuracy on high-res images.
* `--save-blurred`: Save blurred output image.
* `--ignore-regexp ^58c5a57$`: Ignore specific plate formats.
* `--ignore-no-bb`: Skip detections without vehicle bounding boxes.

Run with SDK instead:

```bash
python number_plate_redaction.py --sdk-url http://localhost:8080 --split-image vehicles.jpg
```

---

## 🔄 Automatic Image Transfer & Processing

Continuously monitor a folder and automatically process new images:

```bash
python transfer.py --api-key MY_API_KEY --folder /watch/this/folder
```

* Automatically archives processed images.


---

## 🔗 Useful Links

* **Free API Key & Signup**: [https://platerecognizer.com](https://platerecognizer.com)
* **API Docs**: [docs.platerecognizer.com](http://docs.platerecognizer.com)
* **Vehicle Make/Model Recognition**: [Learn More](https://platerecognizer.com/vehicle-make-model-recognition-with-color/?utm_source=github)
* **Country Support**: [See Full List](https://platerecognizer.com/countries/?utm_source=github)


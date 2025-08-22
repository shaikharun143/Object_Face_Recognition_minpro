**High‑Level Summary of the `mini‑project` Repository**

| Aspect | Description |
|--------|-------------|
| **Purpose** | A Flask‑based web application that provides two core functionalities: <br>1. **Real‑time face detection & recognition** (with registration of new faces). <br>2. **Real‑time object detection** using YOLO models. |
| **Key Technologies** | • **Flask** – web framework and routing<br>• **OpenCV** – video capture and frame handling<br>• **face‑recognition** – encode/compare facial features<br>• **Ultralytics YOLO (v8)** – object detection models (`yolov8n.pt`, `yolov8s.pt`)<br>• **SQLite** – persistent storage of user records and face encodings<br>• **HTML/CSS/JS** – front‑end UI with speech synthesis for alerts |
| **Main Python Modules** | • `app.py` – Flask app, routes, video streaming, admin authentication, API endpoints<br>• `camera.py` – camera wrapper handling face detection, encoding, and YOLO inference<br>• `database.py` – SQLite helper class for CRUD operations, blob handling of face encodings, cleanup utilities |
| **Front‑End** | • Templates (`templates/*.html`) for home, face detection, object detection, admin login/dashboard, face records, and object settings.<br>• Static assets: CSS (`static/css/style.css`), JavaScript (`static/js/face_detection.js`, `object_detection.js`), and saved face images (`static/recognized_faces/`). |
| **Admin Interface** | • Secure login (`admin@example.com` / hashed password).<br>• Dashboard showing total face records and number of YOLO object classes.<br>• Pages to view, search, update, and delete face records; add/remove object categories. |
| **Database** | • `users.db` (SQLite) with a `users` table storing `id`, `name`, `roll_no`, `face_encoding` (pickled BLOB), and optional `image_path`. |
| **Video Streams** | • `/video_feed_face` – MJPEG stream of the camera with face detection overlay.<br>• `/video_feed_object` – MJPEG stream with YOLO object bounding boxes. |
| **APIs** | • `/face_status` – JSON with current face detection/recognition status.<br>• `/object_status` – JSON with current object counts.<br>• `/register_face`, `/delete_face` – REST endpoints for managing face data.<br>• Admin‑only CRUD routes under `/admin/*`. |
| **Deployment** | Run `app.py` (default `debug=True`). The app expects the YOLO `.pt` model files in the repo root and will automatically load `yolov8n.pt` for object detection. |
| **Additional Utilities** | • `view_users.py` – simple script to list registered users from the SQLite DB.<br>• `.gitattributes` marks the `.pt` files as LFS (large‑file storage). |

**Overall**, this repository delivers a complete, browser‑based system for live facial and object recognition, with an admin panel for managing users and detection settings, built on popular Python vision libraries and a lightweight Flask web stack.

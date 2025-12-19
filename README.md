# People Counter 

Project overview: This project is for the detect and count people from a video. Basically it is for counting the number of people in a market by taking the video capture from the gate from a market gate. If a person enter into the market or shop it increase the total count of people and when a person leave the shop or market it decrease the total count of people.

- Purpose: Detect, track, and count people in video/webcam using YOLOv8 + SORT.
- Files: [model_predict.ipynb](model_predict.ipynb), [sort.py](sort.py), weights [yolov8m.pt](yolov8m.pt) / [yolov8x.pt](yolov8x.pt).
- Setup:
  ```bash
  python -m venv .venv && source .venv/bin/activate
  pip install --upgrade pip
  pip install ultralytics opencv-python numpy matplotlib jupyter
  # Optional GPU torch: see https://pytorch.org for CUDA-specific wheels
  ```
- Run: Open [model_predict.ipynb](model_predict.ipynb) in Jupyter (`jupyter lab`), set `MODEL_PATH` to a weight and `SOURCE` to a video path or `0` for webcam, then run all cells.
- Logic: YOLOv8 detects persons, SORT tracks IDs, counts update on line/zone crossing.
- Tips: Use `yolov8m.pt` for speed; adjust confidence/IoU; resize frames; install CUDA torch for GPU.
- Troubleshooting: Check `SOURCE` path/camera index; match torch/CUDA versions; ensure venv active and packages installed.

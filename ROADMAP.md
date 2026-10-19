# Roadmap

Budget: about 2 hours per day. Heavy training happens on Kaggle/Colab GPUs; the laptop is for code, data checks and light inference. Week numbers are estimates and will shift. Learning happens alongside building, and each phase lists what to learn first.

## Phase 0: Setup and first contact (week 1)
- [x] Create the GitHub repo and push this scaffold
- [ ] Set up a Kaggle/Colab notebook that installs dependencies and saves outputs outside the session
- [ ] Run a pretrained YOLO model on a few drone images and a short video
- [ ] Download VisDrone and explore it: class counts, object sizes, images per split
- **Learn:** box formats, IoU, what a detection model outputs
- **Deliverable:** notebook with sample predictions and a dataset summary in `docs/`

## Phase 1: Baseline (weeks 2-3)
- [ ] Convert VisDrone annotations to YOLO format
- [ ] Train a small baseline and evaluate it
- [ ] Read the PR curve, confusion matrix and per-class AP; write down what fails
- **Learn:** precision, recall, AP, mAP@0.5 and mAP@0.5:0.95; NMS; the loss components
- **Deliverable:** baseline row in the README results table, plus a failure-case gallery

## Phase 2: Small-object improvements (weeks 3-5)
- [ ] Higher input resolution
- [ ] Tiled inference (SAHI)
- [ ] Extra small-object detection head
- [ ] Aerial-appropriate augmentation
- [ ] Compare model sizes and at least one non-YOLO detector (e.g. RT-DETR)
- **Learn:** FPN/PAN necks, why small objects vanish through downsampling
- **Deliverable:** ablation table where every row is reproducible from a config
- **Learning track (optional, high value):** write a small YOLOv1-style detector from scratch in PyTorch and compare it with the library baseline

## Phase 3: Tracking (week 6)
- [ ] Run tracking on VisDrone video sequences
- [ ] Count unique objects and inspect ID switches
- **Learn:** Kalman filter, Hungarian assignment, the idea behind ByteTrack
- **Deliverable:** annotated demo video and a short write-up of tracker failures

## Phase 4: Segmentation (weeks 7-8)
- [ ] Prepare a flood segmentation dataset
- [ ] Train and evaluate a segmentation model
- **Learn:** instance vs semantic segmentation, mask metrics
- **Deliverable:** overlay visualizations and metrics in the README

## Phase 5: Geo-localization (week 9)
- [ ] Implement pixel-to-ground projection from altitude, camera angle and field of view
- [ ] Test on synthetic cases with known answers before using real footage
- **Learn:** pinhole camera model, ground sample distance, coordinate frames
- **Deliverable:** `src/geo/` module with unit tests and a map visualization

## Phase 6: Edge deployment (week 10)
- [ ] Export to ONNX (and other formats if hardware allows)
- [ ] Benchmark latency and FPS against accuracy on available hardware
- **Deliverable:** speed/accuracy table and deployment notes

## Phase 7: Simulation stretch and polish (weeks 11-12)
- [ ] Optional: PX4 + Gazebo or AirSim loop where a detection triggers a simulated drone action
- [ ] Demo video, model card, limitations section, clean README
- **Deliverable:** a portfolio-ready repo someone else can reproduce

## Working rules
- Every number in the README links to a config and a run.
- Report failures and limitations, not just best results.
- Commit small and often; each phase ends with a tagged release.

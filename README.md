# aerial-sar-vision

An end-to-end computer vision stack for **aerial search and rescue**: detect and track people, vehicles and hazards in drone footage, segment flooded areas, place detections on a map, and run fast enough for edge hardware.

> **Status: in progress.** Nothing below is claimed as a result until it has a number, a config and a reproducible run behind it. Sections marked `TODO` are planned work.

## Why this project

Floods and disasters make fast situational awareness a life-and-death problem, and drones see what ground teams cannot. Aerial footage is also a hard detection problem: objects are tiny, viewpoints vary and compute on board is limited. This project works through that problem end to end instead of stopping at "fine-tuned a model on a dataset".

## Goals

1. Strong **small-object detection** on aerial imagery, with a clear ablation of what actually helps.
2. **Multi-object tracking** with persistent IDs across video.
3. **Segmentation** of flooded areas, roads or landing zones.
4. **Geo-localization**: convert pixel detections to approximate ground coordinates using altitude, camera angle and field of view.
5. **Edge deployment**: export, quantify the speed/accuracy tradeoff and document it honestly.
6. **Stretch:** closed-loop simulation (PX4 + Gazebo or AirSim) where a detection triggers a simulated drone action.

## Results

| Experiment | Model | Input size | mAP@0.5 | mAP@0.5:0.95 | Notes |
|---|---|---|---|---|---|
| Baseline | TODO | TODO | TODO | TODO | TODO |

Ablations (tiling, higher resolution, extra small-object head, augmentation) will be added here as they are completed.

## Candidate datasets

Verify each license and terms of use before training or redistributing anything.

- **VisDrone**: drone-view detection and tracking benchmark (main detection/tracking dataset).
- **FloodNet**: aerial flood imagery for segmentation.
- **HERIDAL**: aerial images of people for search and rescue.

## Planned repository layout

```
aerial-sar-vision/
  configs/        # training and evaluation configs
  data/           # NOT committed; download scripts and dataset notes only
  notebooks/      # Kaggle/Colab notebooks
  src/            # reusable code (metrics, tiling, geo-localization, tracking helpers)
  scripts/        # train / evaluate / export entry points
  results/        # tables, plots, sample outputs
  docs/           # notes, model card, limitations
  README.md
  ROADMAP.md
  requirements.txt
```

## Setup

```bash
pip install -r requirements.txt
```

Training is intended to run on Kaggle or Colab GPUs. Notebooks will save checkpoints and logs outside the session so runs survive disconnects.

## Limitations (to be filled in honestly)

- TODO: dataset domain gaps (altitude, weather, region).
- TODO: known failure cases with example images.

## License and acknowledgements

- Code license: TODO (choose before publishing).
- Uses the Ultralytics YOLO library, which is offered under AGPL-3.0 and Enterprise licenses; this repository is public and complies with the AGPL-3.0 terms.
- Dataset credits: TODO.

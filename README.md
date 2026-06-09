# Exercise_Form_Detection

A biomechanics-inspired machine learning pipeline for squat form assessment using pose landmarks and engineered features.

## Overview

This project
1. Downloads squat video clips from a registry of URLs and timestamps
2. Extracts frames from each clip
3. Uses MediaPipe Pose to generate 2D body landmarks
4. Computes engineered biomechanical features
5. Trains baseline machine learning classifiers
6. Evaluates performance using repeated train/test splits
7. Saves trained models and feature schemas

The project emphasizes interpretable engineered features rather than deep learning


## Installation

Clone the repository and install dependencies:

```bash
pip install -r requirements.txt
```

For Google Colab users, an optional install cell is provided in the notebook.



## MediaPipe Model Setup

This repository does not redistribute MediaPipe model files

Download the official MediaPipe pose landmark model:

`pose_landmarker_lite.task`

Create the following directory structure:

```text
physio_project/
├── models/
│   └── pose_landmarker_lite.task
```

The notebook expects:

```python
PROJECT_ROOT / "models" / "pose_landmarker_lite.task"
```

If the model file is missing, pose extraction cells will raise an error


## Dataset Setup

Video clips are not included in this repository.

Users must provide:

* clip registry
* source URLs
* timestamps
* labels

The expected registry format is documented in the notebook.


## Repository Structure

```text
dataset/
├── metadata/
├── clips/
├── exports/
│   ├── features/
│   ├── trained_models/
│   └── vectors_zip/
```

Generated outputs are excluded from version control.



## Notes/limitations

* Rule-based measurements are heuristic indicators only
* Rule-based outputs are not used as model inputs
* This project is intended for educational and research purposes
* Outputs should not be interpreted as medical, clinical, or coaching diagnoses
* Future work includes more rigorous citations/justifications of engineered features
* 


# Detection and Classification of Chromosomes with Sister Chromatid Cohesion Defects Using Object Detection Models

This repository will be the sample code for the title paper.


---

## Overview
Unlike standard classification models that require pre-cropped images, this pipeline utilizes **Object Detection** (e.g., YOLOv8, Faster R-CNN) to automatically locate individual chromosomes within a full **metaphase spread** and classify them into three categories based on their cohesion status.

## Repository Structure

### 1. Data: Metaphase Images
* **Description**: Microscopic images of metaphase spreads from **DDX11 -/-** cells.
* **Format**: Full-frame images.
* **Annotations**: Bounding box coordinates and class labels (typeA, typeB, typeC) provided in YOLO/COCO format.

### 2. Models: Trained Object Detection Models
This folder contains trained weights optimized for the morphological features of DDX11-deficient chromosomes.
* **Architectures**: Includes checkpoints for **YOLOv8/v10** and **Faster R-CNN** (ResNet50-FPN).
* **Classes**:
    * **typeA**: Normal cohesion (sister chromatids tightly aligned).
    * **typeB**: Partial cohesion defect (dissociation of chromosome arms).
    * **typeC**: Complete cohesion defect (total separation of sister chromatids).

### 3. Results
* **DDX11_Detection_Results.csv**: Output files containing `image_id`, `box_coordinates`, `class_prediction`, and `confidence_score`.
* **Visualizations**: Metaphase images with detected chromosomes highlighted by bounding boxes and labels.

### 4. Code: DDX11_Detection_Demo.ipynb
A Google Colaboratory notebook designed for automated detection and quantitative analysis.

---

## Usage

1.  **Open the Notebook**: Locate `DDX11_Detection_Demo.ipynb` in the `Code` folder.
2.  **Launch in Colab**: Click the **"Open in Colab"** badge.
3.  **Hardware Acceleration**: 
    * Go to `Runtime` → `Change runtime type`.
    * Select **GPU** as the Hardware accelerator.
4.  **Run Pipeline**: Execute the cells in order from top to bottom.
5.  **Adjust Parameters**: 
    * Lines starting with `###` allow you to modify the `confidence_threshold` or `input_path` for your own datasets.

---

## Key Features of this Pipeline
* **No Manual Cropping**: Directly processes raw metaphase spread images.
* **High Efficiency**: Automatically counts the frequency of each SCC defect type (typeA/B/C) per cell.
* **Overlapping Handling**: Uses **Non-Maximum Suppression (NMS)** to accurately detect chromosomes in crowded metaphase spreads.

---

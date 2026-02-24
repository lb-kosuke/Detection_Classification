# Detection and Classification of Chromosomes with Sister Chromatid Cohesion Defects Using Object Detection Models

This repository will be the sample code for the title paper.


## Repository Structure

### 1. Data: Metaphase Images
* **images**: Microscopic images of metaphase spreads from **DDX11 -/-** cells.
* **labels**: Bounding box coordinates and class labels (typeA:0, typeB:1, typeC:2) provided in YOLO format.

### 2. Models: Trained Object Detection Models

This folder contains trained weight files (`.pt`) for **YOLOv8n**, used to detect and classify chromosomes based on their morphological cohesion patterns.

- **Architecture**: YOLOv8n (Nano) — a lightweight, high-speed object detection model suitable for rapid analysis.
- **Classes**:
    - **typeA**: Normal cohesion
    - **typeB**: Partial cohesion defect (arm dissociation)
    - **typeC**: Complete cohesion defect (total separation)

### 3. Results
* **DDX11_Detection_Results.csv**: Output files containing `image_id`, `box_coordinates`, `class_prediction`, and `confidence_score`.
* **Visualizations**: Metaphase images with detected chromosomes highlighted by bounding boxes and labels.

### 4. Code: DDX11_Detection_Demo.ipynb
A Google Colaboratory notebook designed for automated detection and quantitative analysis.


## Usage

1.  **Open the Notebook**: Locate `DDX11_Detection_Demo.ipynb` in the `Code` folder.
2.  **Launch in Colab**: Click the **"Open in Colab"** badge.
3.  **Hardware Acceleration**: 
    * Go to `Runtime` → `Change runtime type`.
    * Select **GPU** as the Hardware accelerator.
4.  **Run Pipeline**: Execute the cells in order from top to bottom.
5.  **Adjust Parameters**: 
    * Lines starting with `###` allow you to modify the `confidence_threshold` or `input_path` for your own datasets.


## Key Features of this Pipeline
* **No Manual Cropping**: Directly processes raw metaphase spread images.
* **High Efficiency**: Automatically counts the frequency of each SCC defect type (typeA/B/C) per cell.
* **Overlapping Handling**: Uses **Non-Maximum Suppression (NMS)** to accurately detect chromosomes in crowded metaphase spreads.


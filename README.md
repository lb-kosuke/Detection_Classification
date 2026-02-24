[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lb-kosuke/Detection_Classification/blob/main/code/Detection_Classfication.ipynb)
# Detection and Classification of Chromosomes with Sister Chromatid Cohesion Defects Using Object Detection Models

This repository will be the sample code for the title paper.


## Repository Structure

### 1. Data: Metaphase Images
* **images**: Microscopic images of metaphase spreads from **DDX11 -/-** cells.
* **labels**: Bounding box coordinates and class labels (typeA : 0, typeB : 1, typeC : 2) provided in YOLO format.

### 2. Models: Trained Object Detection Models

This folder contains trained weight files (`.pt`) for **YOLOv8n**, used to detect and classify chromosomes based on their morphological cohesion patterns.

- **Architecture**: YOLOv8n
- **Classes**:
    - **typeA**: Normal cohesion
    - **typeB**: Partial cohesion defect (arm dissociation)
    - **typeC**: Complete cohesion defect (total separation)


### 3. Code: Detection_Classification.ipynb
A Google Colaboratory notebook designed for automated detection and classification.


## Usage

1.  **Open the Notebook**: Locate `Detection_Classification.ipynb` in the `Code` folder.
2.  **Launch in Colab**: open in colab
3.  **Run Pipeline**: Execute the cells in order from top to bottom.



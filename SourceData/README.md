# Source Data ReadMe

This folder contains the source data for the study described in “Kinematic Hand Synergies Differ Between Reach-and-Grasp and Functional Object Manipulation” by A. Michael West Jr. and Neville Hogan. The dataset supports all analyses and figures in the manuscript. For details on the experimental setup, data collection, and processing, please refer to the [manuscript](INSERT LINK).

The dataset is designed to facilitate further exploration of kinematic hand synergies and functional manipulation. Below, you will find an explanation of the dataset structure, abbreviations, and details on the individual files.

---

## Abbreviations

The following abbreviations are used throughout the dataset:

1. **R2G** – Reach-and-Grasp Experiment.
2. **Manipulation** – Manipulation Experiment.
3. **X** – Data prior to Singular Value Decomposition (SVD).
4. **V** – Synergy matrix obtained from SVD on X.
5. **VAF** – Variance-Accounted-For by a given synergy after SVD on X.
6. **t** – Time associated with the data in X.

These terms correspond to specific steps in the experimental pipeline described in the manuscript.

---

## Data Organization

### Subjects:
- The dataset includes data from 7 subjects, each with no known neurological or musculoskeletal impairments.

### Experimental Context:
1. **R2G Data**:
   - Data for 5 objects are presented in the order described in the manuscript:
     - Scissors, Zip tie, Screwdriver, Branched Wire Harness (Tied), Branched Wire Harness (Untied).
2. **Manipulation Data**:
   - Data for 5 steps correspond to the wire harnessing procedure:
     - Step 1, Step 2, Step 3, Step 4, Step 5, as detailed in the manuscript.

### Joint Degrees of Freedom:
The data include measurements of 23 joint degrees of freedom, recorded in the following order:
- **Thumb**: T Rot, T MCP, T IP, T ABD
- **Index Finger**: I MCP, I PIP, I DIP, I ABD
- **Middle Finger**: M MCP, M PIP, M DIP, M ABD
- **Ring Finger**: R MCP, R PIP, R DIP, R ABD
- **Little Finger**: L MCP, L PIP, L DIP, L ABD
- **Palm and Wrist**: PA, W Pitch, W Yaw

For details on these abbreviations, refer to the manuscript.

---

## File Descriptions

### 1. `X_R2G_SUBJECTbyOBJECT_raw.mat`
- **Description**: Raw joint angle data collected from the CyberGlove during the Reach-and-Grasp experiment.
- **Structure**: 7 x 5 cell array:
  - **Rows**: Subject.
  - **Columns**: Object.
  - **Each cell contains**: An n x 23 array where:
    - **Rows (n)**: Time-stamped observations.
    - **Columns (23)**: Joint degrees of freedom.

### 2. `X_R2G_bySubject.mat`
- **Description**: Preprocessed “All Tools” Reach-and-Grasp joint angle data.
- **Structure**: 4000 x 23 x 7 array:
  - **Dimension 1 (4000)**: Time-stamped observations.
  - **Dimension 2 (23)**: Joint degrees of freedom.
  - **Dimension 3 (7)**: Subject.

### 3. `X_R2G_SUBJECTbyOBJECT.mat`
- **Description**: Preprocessed Reach-and-Grasp joint angle data for individual objects.
- **Structure**: 7 x 5 cell array:
  - **Rows**: Subject.
  - **Columns**: Object.
  - **Each cell contains**: An 800 x 23 array where:
    - **Rows (800)**: Time-stamped observations after preprocessing.
    - **Columns (23)**: Joint degrees of freedom.

### 4. `X_Manipulation_SUBJECTbyOBJECT_raw.mat`
- **Description**: Raw joint angle data collected from the CyberGlove during the Manipulation experiment.
- **Structure**: 7 x 5 cell array:
  - **Rows**: Subject.
  - **Columns**: Step.
  - **Each cell contains**: An n x 23 array where:
    - **Rows (n)**: Time-stamped observations.
    - **Columns (23)**: Joint degrees of freedom.

### 5. `X_Manipulation_bySubject.mat`
- **Description**: Preprocessed “All Tools” Manipulation joint angle data.
- **Structure**: 5000 x 23 x 7 array:
  - **Dimension 1 (5000)**: Time-stamped observations.
  - **Dimension 2 (23)**: Joint degrees of freedom.
  - **Dimension 3 (7)**: Subject.

### 6. `X_Manipulation_SUBJECTbyOBJECT.mat`
- **Description**: Preprocessed Manipulation joint angle data for individual objects.
- **Structure**: 7 x 5 cell array:
  - **Rows**: Subject.
  - **Columns**: Step.
  - **Each cell contains**: An n x 23 array where:
    - **Rows (n)**: Time-stamped observations after preprocessing.
    - **Columns (23)**: Joint degrees of freedom.

### 7. `t_R2G_SUBJECTbyOBJECT_raw.mat`
- **Description**: Time stamps collected from the CyberGlove during the Reach-and-Grasp experiment.
- **Structure**: 7 x 5 cell array:
  - **Rows**: Subject.
  - **Columns**: Object.
  - **Each cell contains**: An n x 1 array where:
    - **Rows (n)**: Time-stamped observations.

### 8. `t_Manipulation_SUBJECTbyOBJECT_raw.mat`
- **Description**: Time stamps collected from the CyberGlove during the Manipulation experiment.
- **Structure**: 7 x 5 cell array:
  - **Rows**: Subject.
  - **Columns**: Step.
  - **Each cell contains**: An n x 1 array where:
    - **Rows (n)**: Time-stamped observations.

### 9. `V_R2G_bySubject.mat`
- **Description**: The Synergy Matrix obtained from SVD on the Preprocessed “All Tools” Reach-and-Grasp joint angle data in `X_R2G_bySubject.mat`.  
- **Structure**: 23 x 23 x 7 array:
  - **Dimension 1 (23)**: Joint degree-of-freedom.
  - **Dimension 2 (23)**: Synergy number.
  - **Dimension 3 (7)**: Subject.

### 10. `V_R2G_SUBJECTbyOBJECT.mat`
- **Description**: The Synergy Matrix obtained from SVD on the Preprocessed Reach-and-Grasp joint angle data for individual objects in `X_R2G_SUBJECTbyOBJECT.mat`.  
- **Structure**: 23 x 23 x 7 x 5 array:
  - **Dimension 1 (23)**: Joint degree-of-freedom.
  - **Dimension 2 (23)**: Synergy number.
  - **Dimension 3 (7)**: Subject.
  - **Dimension 4 (5)**: Object.

### 11. `V_Manipulation_bySubject.mat`
- **Description**: The Synergy Matrix obtained from SVD on the Preprocessed “All Tools” Manipulation joint angle data in `X_Manipulation_bySubject.mat`.  
- **Structure**: 23 x 23 x 7 array:
  - **Dimension 1 (23)**: Joint degree-of-freedom.
  - **Dimension 2 (23)**: Synergy number.
  - **Dimension 3 (7)**: Subject.

### 12. `V_Manipulation_SUBJECTbyOBJECT.mat`
- **Description**: The Synergy Matrix obtained from SVD on the Preprocessed Manipulation joint angle data for individual objects in `X_Manipulation_SUBJECTbyOBJECT.mat`.  
- **Structure**: 23 x 23 x 7 x 5 array:
  - **Dimension 1 (23)**: Joint degree-of-freedom.
  - **Dimension 2 (23)**: Synergy number.
  - **Dimension 3 (7)**: Subject.
  - **Dimension 4 (5)**: Step.

### 13. `VAF_R2G_bySubject.mat`
- **Description**: The variance-accounted-for obtained from SVD on the Preprocessed “All Tools” Reach-and-Grasp joint angle data in `X_R2G_bySubject.mat`.  
- **Structure**: 23 x 7 array:
  - **Row (23)**: Synergy number.
  - **Column (7)**: Subject.

### 14. `VAF_R2G_SUBJECTbyOBJECT.mat`
- **Description**: The variance-accounted-for obtained from SVD on the Preprocessed Reach-and-Grasp joint angle data for individual objects in `X_R2G_SUBJECTbyOBJECT.mat`.  
- **Structure**: 23 x 7 x 5 array:
  - **Dimension 1 (23)**: Synergy number.
  - **Dimension 2 (7)**: Subject.
  - **Dimension 3 (5)**: Object.

### 15. `VAF_Manipulation_bySubject.mat`
- **Description**: The variance-accounted-for obtained from SVD on the Preprocessed “All Tools” Manipulation joint angle data in `X_Manipulation_bySubject.mat`.  
- **Structure**: 23 x 7 array:
  - **Row (23)**: Synergy number.
  - **Column (7)**: Subject.

### 16. `VAF_Manipulation_SUBJECTbyOBJECT.mat`
- **Description**: The variance-accounted-for obtained from SVD on the Preprocessed Manipulation joint angle data for individual objects in `X_Manipulation_SUBJECTbyOBJECT.mat`.  
- **Structure**: 23 x 7 x 5 array:
  - **Dimension 1 (23)**: Synergy number.
  - **Dimension 2 (7)**: Subject.
  - **Dimension 3 (5)**: Step.

---

## Additional Notes

1. **Software Requirements**:
   - Files are provided in `.mat` format, compatible with MATLAB.

2. **Reproducibility**:
   - For exact replication of the analyses described in the manuscript, refer to the Methods sections.

3. **Contact Information**:
   - If you have questions about the dataset, please contact Michael West via email ([awest36@jh.edu](mailto:awest36@jh.edu)).

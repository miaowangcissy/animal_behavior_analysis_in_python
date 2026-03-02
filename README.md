# Python for Animal Behavioral Analysis (5-Day Workshop)

**Duration:** 5 Days  
**Prerequisites:** Entry-level knowledge of Python syntax is desirable, but not mandatory.

## 📖 Course Overview
This practical course provides an introduction to modern approaches in computational ethology. We will cover the main methodological approaches to the quantitative analysis of animal behavior (flies, fish, rodents, and humans) through the discussion of key publications. Students will gain practical skills in using Python to perform basic analyses of diverse behavioral data, including methods from computer vision, kinematic feature extraction, behavioral segmentation, and unsupervised classification.

---

## ⚙️ Quick Start for Students: Setting up the Environment

To avoid local installation issues and GPU bottlenecks, all coding sessions will be run using **Google Colab**. We will use **Google Drive** to store and access large datasets (like tracking output and videos).

**Before starting the coding sessions:**
1. Log into your Google account.
2. Click the shared Google Drive link provided by the instructor.
3. Right-click the shared `Behavioral_Course_Data` folder and select **"Add shortcut to Drive"**.
4. In the first cell of every Colab notebook, run the following code to connect your Drive:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

---

## 🗓️ Course Schedule

### Day 1: Foundations of Computational Ethology & Python Basics
*Focus: Transitioning from manual observation to automated machine vision, and setting up our computational environment.*

*   **Morning: Theory & Concepts**
    *   **Introduction to Computational Ethology:** From stopwatches to machine vision. The "observability problem" (behavior is latent, we only observe kinematics).
    *   **Hierarchical Organization:** Defining behavior across scales (movemes → actions → activities).
    *   **Space:** Understanding Egocentric vs. Allocentric reference frames.
    *   📝 *Slides:* [Day 1 Theory Slides](path/to/slides.pdf)
*   **Afternoon: Python Warm-Up (Hands-on)**
    *   **Environment Setup:** Setting up Google Colab and mounting Google Drive.
    *   **Basic Data Handling:** Loading a sample rigid-body tracking dataset using `pandas`.
    *   **Basic Kinematics:** Writing functions to calculate velocity and distance traveled from (X, Y) coordinates, and applying a simple speed-threshold for state detection.
    *   💻 *Code:* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO_NAME/blob/main/Day1_Foundations/1_python_warmup.ipynb)

### Day 2: Pose Estimation (From Pixels to Posture)
*Focus: Extracting pose data from raw video using modern deep learning tools.*

*   **Morning: DeepLabCut (DLC) Theory & Demo**
    *   **Markerless Tracking:** Introduction to DeepLabCut, transfer learning, and ResNet backbones.
    *   **Workflow:** Creating a project, extracting frames, and labeling strategies.
    *   **Live Demo:** Instructor walk-through of evaluating a pre-trained model.
    *   📝 *Slides:* [Day 2 Theory Slides](path/to/slides.pdf)
*   **Afternoon: Working with Tracking Data (Mini-Project)**
    *   **Data Import:** Loading pre-analyzed DLC output data (CSV/HDF5).
    *   **Quality Control:** Handling low-confidence points (likelihood scores), interpolating missing data, and applying smoothing (e.g., rolling averages).
    *   **Feature Extraction:** Calculating distances between body parts (e.g., nose-to-tail base) and angular velocity.
    *   💻 *Code:* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO_NAME/blob/main/Day2_Pose_Estimation/2_dlc_postprocessing_skeleton.ipynb)

### Day 3: Movement Ecology & Trajectory Segmentation
*Focus: Analyzing spatial trajectories and finding change-points in continuous movement.*

*   **Morning: Spatial Trajectories & Autocorrelation**
    *   **Path Characteristics:** Measuring path tortuosity (straightness index, sinuosity).
    *   **The Autocorrelation Problem:** Dealing with high-frequency tracking data and continuous-time movement modeling.
    *   **Path Segmentation:** Methods for detecting behavioral changes in movement patterns.
    *   📝 *Slides:* [Day 3 Theory Slides](path/to/slides.pdf)
*   **Afternoon: Change-Point Detection (Hands-on)**
    *   **Library Setup:** Introduction to the `ruptures` Python library.
    *   **Coding Task:** Feeding the cleaned speed and turning-angle data from Day 2 into the PELT algorithm to segment the trajectory into distinct movement bouts.
    *   💻 *Code:* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO_NAME/blob/main/Day3_Movement_Ecology/2_pelt_segmentation_skeleton.ipynb)

### Day 4: Unsupervised Behavioral State Discovery
*Focus: Finding hidden behavioral states without human-labeled bias using sub-second postural data.*

*   **Morning: Statistical Clustering of Posture**
    *   **The Problem:** Why supervised classification introduces human bias.
    *   **Key Literature across Species:** *Drosophila* (MotionMapper), Mice (MoSeq), and *C. elegans* (Markovian dynamics on body curvature).
    *   📝 *Slides:* [Day 4 Theory Slides](path/to/slides.pdf)
*   **Afternoon: Postural Embedding (Mini-Project)**
    *   **Dimensionality Reduction & Clustering:** Taking kinematic features (speed, body elongation, head angle) and applying **PCA**.
    *   **State Discovery:** Applying **K-Means Clustering** to find discrete behavioral states and visualizing the results.
    *   💻 *Code:* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO_NAME/blob/main/Day4_State_Discovery/project3_pca_kmeans_clustering.ipynb)

### Day 5: Cognitive Strategies & Neural Connections
*Focus: Connecting lower-level behavioral motifs to high-level cognitive goals and neural activity.*

*   **Morning: High-Level Strategies & Grammar**
    *   **Navigation Strategies:** The Morris Water Maze as a case study for spatial cognitive strategies (thigmotaxis, scanning, directed search).
    *   **Behavioral Grammar:** How sub-second "syllables" transition into complex sequences using Hidden Markov Models (HMMs).
    *   📝 *Slides:* [Day 5 Theory Slides](path/to/slides.pdf)
*   **Afternoon: Capstone Integration**
    *   Choose an integration project based on your comfort level:
        1.  **Transition Matrices:** Use the `hmmlearn` library to build a transition matrix of the clusters found on Day 4.
        2.  **Strategy Classification:** Write a rule-based algorithm to classify a trajectory into Morris Water Maze strategies.
        3.  **Own Data:** Apply the basic kinematics and segmentation pipeline to your own lab's data.
    *   💻 *Code:* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO_NAME/blob/main/Day5_Cognitive_Strategies/option_A_HMM_transitions.ipynb)

---

## 📚 Reading List
Papers are categorized by how we will use them in the workshop:
*   🔴 **Red (Hands-on / Applied):** Essential methodology applied directly in our coding tutorials.
*   🟠 **Orange (Core Discussion):** Theoretical foundations for our morning lectures.
*   🟢 **Green (Optional):** Supplemental material for further reading.

**Day 1**
*   🟠 [Dawkins 1976 - Hierarchical organisation](path_to_pdf)
*   🟠 [Berman 2018 - Measuring behavior across scales](path_to_pdf)

**Day 2**
*   🔴 [Mathis 2018 - DeepLabCut: markerless pose estimation](path_to_pdf)
*   🟠 [Mathis 2020 - Deep learning tools for measurement of behavior](path_to_pdf)

**Day 3**
*   🔴 [Edelhoff 2016 - Path segmentation for beginners](path_to_pdf)
*   🟠 [Benhamou 2004 - How to reliably estimate the tortuosity](path_to_pdf)

**Day 4**
*   🔴 [Costa 2024 - A Markovian dynamics for C. elegans](path_to_pdf)
*   🔴 [Weinreb 2024 - Keypoint-MoSeq](path_to_pdf)
*   🟠 [Berman 2016 - Predictability and hierarchy in Drosophila](path_to_pdf)
*   🟠 [Findley 2021 - Sniff-synchronized, gradient-guided olfactory search](path_to_pdf)
*   🟢 [Wiltschko 2015 - Mapping Sub-Second Structure in Mouse Behavior](path_to_pdf)

**Day 5**
*   🟠 [Garthe 2009 - Adult-Generated Hippocampal Neurons & Spatial Strategies](path_to_pdf)

---
*Created for the Python for Animal Behavioral Analysis Workshop.*

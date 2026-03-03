# Animal Behavior Analysis in Python (5-Day Practical course)

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
    *   📝 *Slides:* TBA
*   **Afternoon: Python Warm-Up (Hands-on)**
    *   **Environment Setup:** Setting up Google Colab and mounting Google Drive.
    *   💻 *Code:* linear algebra foundations: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/miaowangcissy/animal_behavior_analysis_in_python/blob/main/day1_foundations/Day1_1_LinearAlgebra_Foundations.ipynb)
    *   💻 *Code:*  basic Kinematics/features: TBA


### Day 2: Pose Estimation (From Pixels to Posture)
*Focus: Extracting pose data from raw video using modern deep learning tools.*

*   **Morning: DeepLabCut (DLC) Theory & Demo**
    *   **Markerless Tracking:** Introduction to DeepLabCut, transfer learning, and ResNet backbones.
    *   **Workflow:** Creating a project, extracting frames, and labeling strategies.
    *   **Live Demo:** Instructor walk-through of evaluating a pre-trained model.
    *   📝 *Slides:* TBA
*   **Afternoon: Working with Tracking Data (Mini-Project)**
    *   **Data Import:** Loading pre-analyzed DLC output data (CSV/HDF5).
    *   **Quality Control:** Handling low-confidence points (likelihood scores), interpolating missing data, and applying smoothing (e.g., rolling averages).
    *   **Feature Extraction:** Calculating distances between body parts (e.g., nose-to-tail base) and angular velocity.
    *   💻 *Code:* TBA
### Day 3: Movement Ecology & Trajectory Segmentation
*Focus: Analyzing spatial trajectories and finding change-points in continuous movement.*

*   **Morning: Spatial Trajectories & Autocorrelation**
    *   **Path Characteristics:** Measuring path tortuosity (straightness index, sinuosity).
    *   **The Autocorrelation Problem:** Dealing with high-frequency tracking data and continuous-time movement modeling.
    *   **Path Segmentation:** Methods for detecting behavioral changes in movement patterns.
    *   📝 *Slides:* TBA
*   **Afternoon: Change-Point Detection (Hands-on)**
    *   **Library Setup:** Introduction to the `ruptures` Python library.
    *   **Coding Task:** Feeding the cleaned speed and turning-angle data from Day 2 into the PELT algorithm to segment the trajectory into distinct movement bouts.
    *   💻 *Code:* TBA
    * 
### Day 4: Unsupervised Behavioral State Discovery
*Focus: Finding hidden behavioral states. The whole day will cover two-three mini project covering differnet methods and species.*
*   Project 1:  Mice behavior interpretation based on the body markers.
*   Project 2:  *C. elegans* (Markovian dynamics on body curvature)
*   Project 3: Moseq application (TBD)
    *   📝 *Slides:* TBD
    *   💻 *Code:* TBD
    
### Day 5: Cognitive Strategies (TBD)
*Focus: Connecting lower-level behavioral motifs to high-level cognitive goals.*

*   **Morning: High-Level Strategies & Grammar**
    *   **Navigation Strategies:** The Morris Water Maze as a case study for spatial cognitive strategies (thigmotaxis, scanning, directed search).
    *   **Behavioral Grammar:** How sub-second "syllables" transition into complex sequences using Hidden Markov Models (HMMs).
    *   📝 *Slides:* TBA
*   **Afternoon: Capstone Integration**
    *   Choose an integration project based on your comfort level:
        1.  **Transition Matrices:** Use the `hmmlearn` library to build a transition matrix of the clusters found on Day 4.
        2.  **Strategy Classification:** Write a rule-based algorithm to classify a trajectory into Morris Water Maze strategies.
        3.  **Own Data:** Apply the basic kinematics and segmentation pipeline to your own lab's data.
    *   💻 *Code:* TBD
---
## 📚 Reading List
Papers are categorized by how we will use them in the workshop:
*   🔴 **Red (Hands-on / Applied):** Essential methodology applied directly in our coding tutorials.
*   🟠 **Orange (Core Discussion):** Theoretical foundations for our morning lectures.
*   🟢 **Green (Optional):** Supplemental material for further reading.

**Day 1**
*   🟠 [Dawkins 1976 - Hierarchical organisation](https://psycnet.apa.org/record/1976-19904-012)
*   🟠 [Berman 2018 - Measuring behavior across scales](https://doi.org/10.1186/s12915-018-0494-7)

**Day 2**
*   🔴 [Mathis 2018 - DeepLabCut: markerless pose estimation](https://doi.org/10.1038/s41593-018-0209-y)
*   🟠 [Mathis 2020 - Deep learning tools for measurement of behavior](https://www.sciencedirect.com/science/article/pii/S0959438819301151)

**Day 3**
*   🔴 [Edelhoff 2016 - Path segmentation for beginners](https://link.springer.com/article/10.1186/s40462-016-0086-5)
*   🟠 [Benhamou 2004 - How to reliably estimate the tortuosity](https://www.sciencedirect.com/science/article/pii/S0022519304001353)

**Day 4**
*   🔴 [Costa 2024 - A Markovian dynamics for C. elegans](https://pubmed.ncbi.nlm.nih.gov/39083417/)
*   🔴 [Weinreb 2024 - Keypoint-MoSeq](https://www.nature.com/articles/s41592-024-02318-2)
*   🟠 [Berman 2016 - Predictability and hierarchy in Drosophila](https://www.pnas.org/doi/10.1073/pnas.1607601113)
*   🟠 [Findley 2021 - Sniff-synchronized, gradient-guided olfactory search](https://elifesciences.org/articles/58523)
*   🟢 [Wiltschko 2015 - Mapping Sub-Second Structure in Mouse Behavior](https://www.sciencedirect.com/science/article/pii/S0896627315010375)

**Day 5**
*   🟠 [Garthe 2009 - Adult-Generated Hippocampal Neurons & Spatial Strategies](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0005464)

---
*Created for the Python for Animal Behavioral Analysis Workshop.*

# Python for Animal Behavioral Analysis (5-Day Workshop)

**Duration:** 5 Days  
**Audience:** PhD students in Neuroscience  
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

--------------------------------------------------------------------------------
🗓️ Course Schedule
Day 1: Foundations of Computational Ethology & Python Basics
Focus: Transitioning from manual observation to automated machine vision, and setting up our computational environment.
Morning: Theory & Concepts
Introduction to Computational Ethology: From stopwatches to machine vision. The "observability problem" (behavior is latent, we only observe kinematics).
Hierarchical Organization: Defining behavior across scales (movemes → actions → activities).
Space: Understanding Egocentric vs. Allocentric reference frames.
📝 Slides: Day 1 Theory Slides
Afternoon: Python Warm-Up (Hands-on)
Environment Setup: Setting up Google Colab and mounting Google Drive.
Basic Data Handling: Loading a sample rigid-body tracking dataset using pandas.
Basic Kinematics: Writing functions to calculate velocity and distance traveled from (X, Y) coordinates, and applying a simple speed-threshold for state detection.
💻 Code: 
Day 2: Pose Estimation (From Pixels to Posture)
Focus: Extracting pose data from raw video using modern deep learning tools.
Morning: DeepLabCut (DLC) Theory & Demo
Markerless Tracking: Introduction to DeepLabCut, transfer learning, and ResNet backbones.
Workflow: Creating a project, extracting frames, and labeling strategies.
Live Demo: Instructor walk-through of evaluating a pre-trained model.
📝 Slides: Day 2 Theory Slides
Afternoon: Working with Tracking Data (Mini-Project)
Data Import: Loading pre-analyzed DLC output data (CSV/HDF5).
Quality Control: Handling low-confidence points (likelihood scores), interpolating missing data, and applying smoothing (e.g., rolling averages).
Feature Extraction: Calculating distances between body parts (e.g., nose-to-tail base) and angular velocity.
💻 Code: 
Day 3: Movement Ecology & Trajectory Segmentation
Focus: Analyzing spatial trajectories and finding change-points in continuous movement.
Morning: Spatial Trajectories & Autocorrelation
Path Characteristics: Measuring path tortuosity (straightness index, sinuosity).
The Autocorrelation Problem: Dealing with high-frequency tracking data and continuous-time movement modeling.
Path Segmentation: Methods for detecting behavioral changes in movement patterns.
📝 Slides: Day 3 Theory Slides
Afternoon: Change-Point Detection (Hands-on)
Library Setup: Introduction to the ruptures Python library.
Coding Task: Feeding the cleaned speed and turning-angle data from Day 2 into the PELT algorithm to segment the trajectory into distinct movement bouts.
💻 Code: 
Day 4: Unsupervised Behavioral State Discovery
Focus: Finding hidden behavioral states without human-labeled bias using sub-second postural data.
Morning: Statistical Clustering of Posture
The Problem: Why supervised classification introduces human bias.
Key Literature across Species: Drosophila (MotionMapper), Mice (MoSeq), and C. elegans (Markovian dynamics on body curvature).
📝 Slides: Day 4 Theory Slides
Afternoon: Postural Embedding (Mini-Project)
Dimensionality Reduction & Clustering: Taking kinematic features (speed, body elongation, head angle) and applying PCA.
State Discovery: Applying K-Means Clustering to find discrete behavioral states and visualizing the results.
💻 Code: 
Day 5: Cognitive Strategies & Neural Connections
Focus: Connecting lower-level behavioral motifs to high-level cognitive goals and neural activity.
Morning: High-Level Strategies & Grammar
Navigation Strategies: The Morris Water Maze as a case study for spatial cognitive strategies (thigmotaxis, scanning, directed search).
Behavioral Grammar: How sub-second "syllables" transition into complex sequences using Hidden Markov Models (HMMs).
📝 Slides: Day 5 Theory Slides
Afternoon: Capstone Integration
Choose an integration project based on your comfort level:
Transition Matrices: Use the hmmlearn library to build a transition matrix of the clusters found on Day 4.
Strategy Classification: Write a rule-based algorithm to classify a trajectory into Morris Water Maze strategies.
Own Data: Apply the basic kinematics and segmentation pipeline to your own lab's data.
💻 Code:

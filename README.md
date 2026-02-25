# Robust Mouse Behavior Recognition (MABe 2025 Challenge)

[![Kaggle](https://img.shields.io/badge/Kaggle-Competition-blue)](https://www.kaggle.com/competitions/MABe-mouse-behavior-detection)
[![Status](https://img.shields.io/badge/Rank-Top%20370%20/%201413-green)](#)

This repository contains the source code for our team's solution in the **MABe 2025: MABe Challenge - Social Action Recognition in Mice**. Our system achieved a **Private Leaderboard score of 0.42033**, ranking **370/1413** participants.

## Project Overview
The goal of this project is to automate the detection of mouse social behaviors from pose-tracking data. Our approach focuses on handling heterogeneous data from multiple labs with varying frame rates (FPS) and recording setups.

## Key Technical Contributions
* **FPS-Aware Feature Engineering:** * Automatically scales all time-related parameters (rolling windows, lags, EWM spans) based on the actual FPS of each video.
    * Ensures physical consistency where a 1-second window always represents 1 second, regardless of whether the video is 30 or 60 FPS.
* **Multi-Scale Spatial-Temporal Features:** * **Geometric:** Euclidean distances between body parts, body elongation, and relative orientations.
    * **Kinematic:** Velocity, acceleration, and curvature calculated with FPS-scaled lags.
    * **Social/Interaction:** Approach speed, nose-to-nose distance, and leading/chasing indices.
* **Ensemble Gradient Boosting:** * A robust ensemble of **LightGBM**, **XGBoost**, and **CatBoost**.
    * **Stratified Subset Sampling:** Trained on 1.5M representative frames to balance efficiency and accuracy.
* **Post-Processing:** Automated thresholding and temporal smoothing to convert frame-level predictions into continuous behavioral events (start/stop frames).

## Tech Stack
- **Languages:** Python 3.11.13
- **ML Frameworks:** LightGBM, XGBoost, CatBoost, Scikit-learn
- **Data Processing:** Pandas, NumPy, Polars
- **Hardware used:** NVIDIA P100 GPU (Kaggle Environment)

## Results
* **Public Leaderboard Score:** 0.449
* **Private Leaderboard Score:** 0.42003
* **Ranking:** Top 30% (370th out of 1413 teams)
* **Training Time:** ~6 hours 21 minutes for the full ensemble pipeline.

## Contributors
* **Nguyễn Đỗ Trọng Nghĩa** (Student ID: 23020125)
* **Nguyễn Thành Long** (Student ID: 23020104)
* **Nguyễn Quốc Minh** (Student ID: 23020116)

---
*Developed as part of the INT34055 course at University of Engineering and Technology (VNU-UET).*

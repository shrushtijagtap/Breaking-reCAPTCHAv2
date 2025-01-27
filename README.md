# No CAP(TCHA) - Enhancing CAPTCHA Solvers and Using Adversarial Examples to Make CAPTCHA More Robust
Mitali Mukherjee, Shrushti Jagtap, Saumitra Chaskar, Arunesh Kumar

## Overview
In our study, we build on [previous work](https://github.com/aplesner/Breaking-reCAPTCHAv2/tree/main) that focuses on breaking Google’s reCAPTCHA v2 using advanced machine learning-based approaches, specifically object detection. The prior research demonstrates a method that can solve 100% of presented CAPTCHA challenges. However, we have identified several directions for extending this work, which we define as the primary focus of our project.

## Goals

1. **Improving Prediction Confidence and Enhancing the Overall Solver**
   - We introduce a more recent model - YOLOv11 to replace YOLOv8, which is expected to enhance the predictive power of the solver. This upgrade aims to make the solver more robust and effective at breaking existing CAPTCHA challenges.

2. **Enhancing Performance on Type 2 Challenges through Dataset Augmentation and Model Fine-Tuning**
   - To improve the solver's performance on Type 2 challenges, we incorporate a new dataset into the fine-tuning pipeline of the solver. This enhancement is essential for improving its image segmentation performance in solving these challenges.

3. **Assessing the Impact of Adversarial Examples on Both the Original and Enhanced Solvers**
   - We conduct a comparative analysis between the baseline and enhanced solvers, evaluating their robustness against a variety of adversarial examples generated using established methods from the literature.

## Usage
- Run `solve_recaptcha.py` to solve a single reCAPTCHA challenge:
  ```
  python solve_recaptcha.py
  ```

- Run `test_environment.py` to solve multiple reCAPTCHA challenges and create a log file:
  ```
  python test_environment.py
  ```

## Project Structure
This project has the following directory structure:

- `assets/`: Contains the images used in the README.
- `IP/`: Contains the script for changing IP address.
  - `vpn.py`: Script for changing IP address (only works on macOS).
- `models/`: Contains all the models used in the original project.
  - `YOLO_Classification/`: Contains the YOLO model for classification.
  - `YOLO_Segment/`: Contains the YOLO model for segmentation.
- `utils/`: Contains utility scripts.
  - `collect_data.py`: Script for collecting data for the classification model.
  - `label_tool.py`: A UI tool for labeling CAPTCHA images.
  - `visualize_log_files.py`: Analyzes log files, providing insights into task attempts, their distribution, and key statistical measures.
- `README.md`: This file, providing an overview of the project.
- `solve_recaptcha.py`: Demo script for solving a single reCAPTCHA challenge using Selenium.
- `test_environment.py`: Demo script for solving multiple reCAPTCHA challenges using Selenium and creating a log file.
- `requirements.txt`: Contains the required libraries for the project.
- `YOLOv11/`: contains our fine-tuned models
   - `runs/classify/`: contains the `best.pt` file which is the best performing image classification model
   - `validationScripts`: contains some basic evaluation on the validation dataset
   - `inference.py`: this file has the detailed inference including the calculation of metrics such as precision and recall which we have used to report our results
   - `finetune_yolov11.py`: this file is used to train the YOLOv11 model on CAPTCHA images. It is inspired by the original training code from Plesner et al.

## Report
https://drive.google.com/file/d/1AGsh4l8Q2dqwQLwdEXlvrMVnkNtpMMAS/view?usp=sharing

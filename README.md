# Autonomous-Medical-Assistant

## Overview
This repository presents a prototype framework for an **autonomous robotic platform** integrating environmental sterilisation with physiological monitoring.  
The system demonstrates how **AI-based sensing and decision algorithms** can support infection control and safety assurance in healthcare environments.

Although the physical robot and embedded control code are not included here, this repository contains the **core dataset and trained AI model** used for oxygen saturation (SpO₂) monitoring — a key component of the robot’s physiological safety system.  
*Hardware integration code will be added once the embedded system is accessible.*

---

## Project Summary
- **Autonomous Navigation and Control:** Designed a robot prototype capable of mapping and navigating healthcare spaces using sensor fusion and control loops.  
- **UVC Sterilisation Simulation:** Developed simulated UVC coverage algorithms to model surface disinfection and optimise exposure patterns.  
- **AI-Based SpO₂ Monitoring:** Trained a machine learning model on oxygen saturation data to classify or predict patient safety states in real time.  
- **System Integration:** Coupled environmental control with physiological monitoring to enable context-aware disinfection routines.  
- **Impact:** Demonstrated the feasibility of autonomous disinfection robots to reduce reliance on manual sterilisation procedures in hospitals.

## Dataset
**File:** `Oxygen Dataset Final.csv`  
- ~200,000 samples  
- **Example columns:** `age`, `gender`, `spo2`, `pr`, `c/nc`, `oxy_flow`  
- Represents anonymised physiological readings used to train and test the SpO₂ monitoring model.

---

## Model
**File:** `model.pkl`  
- Type: `DecisionTreeClassifier` (scikit-learn)  
- Input: Processed physiological parameters  
- Output: Predicted classification of oxygen saturation state  
- Achieved approximately **70% accuracy** on validation data.  

> To load and inspect the model:
```python
import pickle
with open("models/model.pkl", "rb") as f:
    model = pickle.load(f)
print(model)

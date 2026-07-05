# ⚡ AI-Based Fault Detection and Fault Location in Renewable Integrated IEEE 14-Bus Power System

An intelligent power system protection framework that integrates **Solar PV**, **Wind Energy**, **STATCOM**, and **Machine Learning** to accurately detect and locate faults in an IEEE 14-bus power system.

---

## 📖 Project Overview

The increasing penetration of renewable energy sources introduces significant challenges in maintaining power system stability and reliability. This project presents an AI-assisted fault diagnosis framework capable of identifying fault types and locating faulted buses in a renewable-integrated IEEE 14-bus network.

The system combines MATLAB/Simulink-based power system simulation with machine learning techniques to improve fault diagnosis while enhancing voltage stability using a STATCOM.

---

## 🎯 Objectives

- Integrate Solar PV and Wind Energy into the IEEE 14-Bus System
- Improve voltage stability using STATCOM
- Detect different fault types using Machine Learning
- Locate the faulted bus accurately
- Analyze voltage sag, swell, and various fault conditions
- Enhance overall power system reliability

---

# 🏗️ System Architecture

```
Solar PV          Wind Energy
     │                  │
     └──────┬───────────┘
            │
     Power Electronic Converters
            │
         DC Link
            │
      Voltage Source Inverter
            │
         LCL Filter
            │
      Step-up Transformer
            │
        STATCOM Controller
            │
      IEEE 14-Bus Network
            │
      Fault Generation
            │
Signal Measurement & Feature Extraction
            │
   Random Forest Classifier
     (Fault Identification)
            │
 Extra Trees Classifier
   (Fault Bus Location)
            │
 Protection Decision
```

---

# 🧠 ANN-Based STATCOM Controller

To enhance the dynamic performance of the STATCOM, the conventional **PI controllers** used in the control loop were replaced with an **Artificial Neural Network (ANN)** controller.

### Conventional Control

In a traditional STATCOM, PI controllers regulate:
- DC-link Voltage (Vdc)
- Reactive Current (Iq)
- Active Current (Id)

Although PI controllers perform well under steady-state conditions, their performance deteriorates during nonlinear disturbances, renewable intermittency, and severe grid faults because they require manual gain tuning and have limited adaptability.

### Proposed ANN Controller

The proposed ANN controller learns the nonlinear relationship between the system operating conditions and the required control action.

The ANN receives real-time electrical measurements such as:

- DC-link Voltage (Vdc)
- PCC Voltage
- Voltage Error
- Current Error
- Reference Signals

Based on these inputs, the ANN directly predicts the appropriate control signal required for the Voltage Source Inverter (VSI), effectively replacing the conventional PI controllers.

### ANN Control Workflow

```
Measured Voltage & Current
            │
            ▼
      Error Calculation
            │
            ▼
      ANN Controller
            │
            ▼
 PWM Pulse Generation
            │
            ▼
 Voltage Source Inverter
            │
            ▼
       STATCOM Output
            │
            ▼
 Dynamic Reactive Power Compensation
```

### Advantages of ANN over PI

- Eliminates manual PI gain tuning
- Learns nonlinear system dynamics
- Faster transient response
- Better voltage regulation
- Reduced oscillations
- Improved fault ride-through capability
- Enhanced reactive power compensation during faults

The ANN-based STATCOM significantly improves voltage stability by generating adaptive switching signals for the inverter, enabling rapid reactive power injection during LG, LL, LLG, LLL faults, voltage sag, and voltage swell conditions.

# ⚙️ Technologies Used

- MATLAB R2024a
- Simulink
- Python
- Scikit-learn
- NumPy
- Pandas
- Matplotlib

---

# ⚡ Faults Considered

- Line-to-Ground (LG)
- Line-to-Line (LL)
- Double Line-to-Ground (LLG)
- Three-Phase Fault (LLL)
- Voltage Sag
- Voltage Swell

---

# 🤖 Machine Learning Models

## Random Forest
**Purpose:** Fault Identification

- Ensemble learning algorithm
- Uses multiple decision trees
- Majority voting for final prediction
- High robustness against overfitting

### Performance

| Metric | Value |
|--------|------:|
| Accuracy | **97.50%** |
| Precision | **97.92%** |
| Recall | **97.50%** |
| F1-Score | **97.50%** |

---

## Extra Trees Classifier

**Purpose:** Fault Bus Location

- Extremely Randomized Trees
- Fast training
- High generalization capability
- Efficient multiclass classification

### Performance

| Metric | Value |
|--------|------:|
| Accuracy | **96.36%** |
| Precision | **0.97** |
| Recall | **0.96** |
| F1-Score | **0.96** |

---

# 📊 Results

The proposed framework demonstrates significant improvement in system performance under various fault conditions.

### Key Highlights

- ✅ 97.50% Fault Identification Accuracy
- ✅ 96.36% Fault Location Accuracy
- ✅ Improved Voltage Stability
- ✅ Fast Fault Recovery
- ✅ Reduced Power Oscillations
- ✅ Effective Reactive Power Compensation
- ✅ Enhanced Renewable Grid Stability

---

# 📂 Repository Structure

```
AI-Based-Fault-Diagnosis-IEEE14Bus/

├── Simulation/
├── Dataset/
├── ML/
│   ├── RandomForest.ipynb
│   └── ExtraTrees.ipynb
├── Results/
├── Report/
└── README.md
```

---

# 📈 Workflow

```
Renewable Sources
        │
        ▼
 IEEE 14-Bus System
        │
        ▼
 Fault Generation
        │
        ▼
 Signal Acquisition
        │
        ▼
 Feature Extraction
        │
        ▼
 Random Forest
(Fault Identification)
        │
        ▼
 Extra Trees
(Fault Location)
        │
        ▼
 Protection Decision
```

---

# 🚀 Future Scope

- Real-time PMU integration
- Deep Learning-based fault diagnosis
- Hardware implementation using FPGA/DSP
- IoT-enabled remote monitoring
- Adaptive protection schemes
- Digital Twin for smart grids

---

# 👨‍💻 Author

**Uday Vardhan Singh Rathore**

B.Tech – Electrical and Computer Science Engineering (ECSE)

VIT Chennai

---

## ⭐ If you found this project useful, consider giving it a star!

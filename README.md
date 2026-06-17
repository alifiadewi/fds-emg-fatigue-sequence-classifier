A deep learning pipeline for binary classification of muscle fatigue (Fatigue vs. Non-Fatigue) using Electromyography (EMG) time-series data collected from the Flexor Digitorum Superficialis (FDS) muscle.
This project utilizes a Long Short-Term Memory (LSTM) neural network architecture to process sequential biosignals, capturing the temporal dynamics of muscle exertion over time.

### Data Processing Highlights
**Patient Split (Subject-Independent):** To prevent data leakage and ensure real-world generalization, the dataset is strictly split by patient: **36 patients for training** and **16 patients for testing**.
**Windowing Strategy:** The continuous EMG signal is segmented into sliding windows of **100 time-steps** to capture localized temporal dynamics.
**Feature Extraction:** For each window, we extract 3 distinct time-domain features, resulting in our final input matrices:
 * **RMS (Root Mean Square):** Captures the sustained power of the muscle signal.
 * **MAV (Mean Absolute Value):** Measures the average amplitude of muscle contraction.
 * **VAR (Variance):** Tracks the fluctuation and spread of the signal, which often changes during muscle fatigue.
**Input Shape Strategy:** The optimal performing model utilizes a `(Samples, Features, Time-steps)` matrix structure. 
**Target:** Binary classification (`0` = Non-Fatigue, `1` = Fatigue).

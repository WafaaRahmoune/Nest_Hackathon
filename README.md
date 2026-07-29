# Nest Hackathon: AI + IoT for Energy Efficiency, Monitoring & Security

![Python](https://img.shields.io/badge/Python-Jupyter-3776AB?style=flat-square&logo=jupyter&logoColor=white)
![ML](https://img.shields.io/badge/ML%2FDL-XGBoost%20%7C%20LSTM%20%7C%20DNN-F7931E?style=flat-square)
![IoT](https://img.shields.io/badge/IoT-ESP32%20%7C%20Firebase-E7352C?style=flat-square&logo=espressif&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

An **AI + IoT** project built for the **Nest Robotics hackathon** (for Mobilis / ATM), tackling **energy efficiency, monitoring and security**. It combines machine-learning models with a connected cooling system driven in real time through Firebase.

## Concept

The submission is organized around two ideas (see `Conception_Side/`):

- **Intelligent cooling:** predict temperature and drive fans/AC automatically to save energy.
- **Intelligent OFDM:** optimize OFDM based on real network-traffic data.

## Repository structure

```
Nest_Hackathon/
├── Conception_Side/          # idea documents and hackathon theme (PDF)
├── Presentation/             # hackathon presentation (PDF)
└── Technical_Work/
    ├── 20Attack_Detection_with_ML_DL/   # network intrusion detection (20 attack types)
    ├── Ai_Side/
    │   ├── OFDM_Optimisation_Based_on_Network_Traffic/   # OFDM optimization from traffic data
    │   └── Temperature_Prevention/                       # temperature prediction (XGBoost)
    └── IOT_Side/
        └── Systeme_de_refroidissement_IA_NatureExploitation/   # ESP32 smart cooling sketch
```

## Technical components

### AI side
- **Attack detection (ML/DL):** classifies 20 attack types using several models (XGBoost, AdaBoost, LSTM, DNN, MLP, Logistic Regression) with PCA feature reduction, and compares performance before and after optimization.
- **OFDM optimization:** learns from real network-traffic datasets to optimize OFDM allocation.
- **Temperature prevention:** predicts minimum and maximum temperatures (XGBoost) to anticipate cooling needs.

### IoT side
- **Smart cooling system:** an **ESP32** with two **DHT22** temperature sensors, fans and LEDs. Readings are pushed to a **Firebase Realtime Database** and fans can be controlled remotely, enabling real-time monitoring and AI-driven cooling.

## Tech stack

- **AI / ML:** Python, Jupyter, scikit-learn, XGBoost, TensorFlow / Keras, pandas, NumPy
- **IoT:** ESP32 (Arduino), DHT22 sensors, Firebase Realtime Database
- **Docs:** idea and presentation PDFs

## IoT configuration (secrets)

The Arduino sketch reads WiFi and Firebase credentials from `arduino_secrets.h`, which is **git-ignored**. Copy the template and fill in your own values:

```bash
cp arduino_secrets.h.example arduino_secrets.h
```

Then open the sketch in the Arduino IDE (with the `WiFi`, `Firebase ESP Client` and `DHT` libraries installed) and flash it to your ESP32.

## Note on data

The repository keeps the datasets and trained models (`.pkl`) used during the hackathon so the notebooks are reproducible, which makes the repo relatively large.

## License

Released under the MIT License. See [LICENSE](LICENSE).

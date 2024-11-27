# RS-FEDRAD: Robust and Scalable Federated Ransomware Detection Using TTP-Enhanced Dataset 

![Python](https://img.shields.io/badge/python-3.9-blue) ![License](https://img.shields.io/badge/license-MIT-green)
## Abstract
Ransomware continues to evolve as a significant cybersecurity threat, employing advanced evasion techniques such as polymorphism and obfuscation to bypass detection mechanisms. Conventional detection approaches fail to detect this modern Ransomware because they usually implore either single or limited feature sets. Additionally, they heavily rely on centralized architecture, thereby causing privacy and scalability issues. To address these limitations, we present RS-FEDRAD, a robust and scalable Federated Learning (FL)-based ransomware detection system. RS-FEDRAD integrates FL with deep dynamic analysis, using novel Tactics, Techniques, and Procedures (TTP)-enhanced dataset to create a decentralized, privacy-preserving solution. 

This comprehensive feature set provides crucial behavioral insights into Ransomware, encompassing API call sequences, dynamic link library (DLL) interactions, and Mutex operations specific to ransomware TTPs. Experimental evaluations demonstrate that RS-FEDRAD achieves state-of-the-art results across key metrics, including an accuracy of 99.90\% and an average federated accuracy of 99.50\% while maintaining impressive F1-scores, recall, and precision. RS-FEDAD also achieved remarkable resilience against unknown-type black-box attacks as well as known-type white-box attacks. This outcome demonstrates the robustness and scalability of RS-FEDRAD, offering a comprehensive and privacy-conscious, decentralized solution to modern ransomware detection.
<p align="center">
  <img src="https://github.com/EmpireNetwork123/RS-FEDRAD/blob/master/RS-FEDRAD.jpg" alt="Architecture Diagram" width="800" height="300">
</p>


---

## Table of Contents
- [Abstract](#abstract)
- [Key Contributions](#key-contributions)
- [Setup Instructions](#setup-instructions)
- [Experimental Results](#experimental-results)
- [System Requirements](#system-requirements)
---
## Key Contributions
1. **TTP-Enhanced Dataset**: Maps ransomware features (API calls, DLL interactions) to TTPs for enriched detection capabilities.
2. **Hybrid CNN-LSTM Model**: Combines spatial and temporal pattern analysis for superior results.
3. **Scalable Federated Learning**: Dynamic client participation supports privacy-preserving decentrlaized training.
4. **Adversarial Resilience**: Robust under FGSM and BIM attacks with minimal accuracy drop (~0.20%).

---

## Setup Instructions

1. **Data Preprocessing**  
   Navigate to the `src` folder and run: `python src/data_preprocessing.py`  
   This will:
   - Standardize, shuffle, and split the dataset.
   - Divide the data into 10 client-specific datasets for federated training.
   - RS-FEDRAD is scalable; therefore, the number of clients can be adjusted according to your needs.
  
##  Federated Training  
Follow the steps below:

1. **Initialize the Flower Server**:  
   Run the server script: `python src/start_server.py`  
   - The server is configured for 10 clients by default. You can modify the `start_server.py` file to the desired number of clients or training rounds.

2. **Start Clients**:  
   In parallel, execute the following command for each client: `python scripts/run_federated-client.py`  
   - The server will begin training once at least 2 clients have connected. Training continues simultaneously as more clients join.

3. **Results**:  
   - Training metrics (e.g., accuracy, precision, recall, F1-score) and history for each client are saved in `results/experiment_results`.

---

### Adversarial Training  
- Follow the federated training setup, but use the adversarial client scripts:
   1. **For BIM attacks**:  
      Navigate to the `scripts` folder and run: `python scripts/adversarial-bim_run_client.py`
   2. **For FGSM attacks**:  
      Navigate to the `scripts` folder and run: `python scripts/adversarial-fgsm_run_client.py`

---

### Centralized Training  
- Run the `Centralized-run.py` script from the `scripts` folder. This script combines all client datasets into a single repository and trains the model centrally:
   ```bash
   python scripts/centralized-run.py


## Experimental Results:
RS-FEDRAD achieves state-of-the-art performance with:
Accuracy of 99.90% and Average Federated Accuracy of 99.5% while maintining
Resilience to Adversarial Attacks with minimal/negligible accuracy degradation (~0.20%).
Visualizations in `results/experiment_plots`, Metrics and history in `results/experiment_results`

## System Requirements
- **Python**: 3.9+
- **Dependencies**:
  - `flwr==1.2.0`
  - `tensorflow==2.10.0`
  - `numpy==1.23.5`
  - `pandas==1.5.3`
  - `scikit-learn==1.2.2`

Install dependencies using:
```bash
pip install -r requirements.txt






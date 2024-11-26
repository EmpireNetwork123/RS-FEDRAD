# RS-FEDRAD: Robust and Scalable Federated Ransomware Detection Using TTP-Enhanced Dataset 

![Python](https://img.shields.io/badge/python-3.9-blue) ![License](https://img.shields.io/badge/license-MIT-green)

## Abstract
Ransomware continues to evolve as a significant cybersecurity threat, employing advanced evasion techniques such as polymorphism and obfuscation to bypass detection mechanisms. Conventional detection approaches fail to detect this modern Ransomware because they usually implore either single or limited feature sets. Additionally, they heavily rely on centralized architecture, thereby causing privacy and scalability issues. To address these limitations, we present RS-FEDRAD, a robust and scalable Federated Learning (FL)-based ransomware detection system. RS-FEDRAD integrates FL with deep dynamic analysis, using novel Tactics, Techniques, and Procedures (TTP)-enhanced dataset to create a decentralized, privacy-preserving solution. 

This comprehensive feature set provides crucial behavioral insights into Ransomware, encompassing API call sequences, dynamic link library (DLL) interactions, and Mutex operations specific to ransomware TTPs. Experimental evaluations demonstrate that RS-FEDRAD achieves state-of-the-art results across key metrics, including an accuracy of 99.90\% and an average federated accuracy of 99.50\% while maintaining impressive F1-scores, recall, and precision. RS-FEDAD also achieved remarkable resilience against unknown-type black-box attacks as well as known-type white-box attacks. This outcome demonstrates the robustness and scalability of RS-FEDRAD, offering a comprehensive and privacy-conscious, decentralized solution to modern ransomware detection.

---

## Table of Contents
- [Abstract](#abstract)
- [Key Contributions](#key-contributions)
- [System Requirements](#system-requirements)
- [Folder Structure](#folder-structure)
- [Setup Instructions](#setup-instructions)
- [Experimental Results](#experimental-results)
- [Citation](#citation)
- [Contact](#contact)

---

## Key Contributions
1. **TTP-Enhanced Dataset**: Maps ransomware features (API calls, DLL interactions) to TTPs for enriched detection capabilities.
2. **Hybrid CNN-LSTM Model**: Combines spatial and temporal pattern analysis for superior results.
3. **Scalable Federated Learning**: Dynamic client participation supports privacy-preserving decentrlaized training.
4. **Adversarial Resilience**: Robust under FGSM and BIM attacks with minimal accuracy drop (~0.20%).

---

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

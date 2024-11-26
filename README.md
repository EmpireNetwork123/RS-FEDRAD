RS-FEDRAD: Robust and Scalable Federated Ransomware Detection Using TTP-Enhanced Dataset 
Ransomware continues to evolve as a significant cybersecurity threat, employing advanced evasion techniques such as polymorphism and obfuscation to bypass detection mechanisms. Conventional detection approaches fail to detect this modern Ransomware because they usually implore either single or limited feature sets. Additionally, they heavily rely on centralized architecture, thereby causing privacy and scalability issues. To address these limitations, we present RS-FEDRAD, a robust and scalable Federated Learning (FL)-based ransomware detection system. RS-FEDRAD integrates FL with deep dynamic analysis, using novel Tactics, Techniques, and Procedures (TTP)-enhanced dataset to create a decentralized, privacy-preserving solution. 

This comprehensive feature set provides crucial behavioral insights into Ransomware, encompassing API call sequences, dynamic link library (DLL) interactions, and Mutex operations specific to ransomware TTPs. Experimental evaluations demonstrate that RS-FEDRAD achieves state-of-the-art results across key metrics, including an accuracy of 99.90\% and an average federated accuracy of 99.50\% while maintaining impressive F1-scores, recall, and precision. RS-FEDAD also achieved remarkable resilience against unknown-type black-box attacks as well as known-type white-box attacks. This outcome demonstrates the robustness and scalability of RS-FEDRAD, offering a comprehensive and privacy-conscious, decentralized solution to modern ransomware detection.

Key Contributions
Novel TTP-Enhanced Dataset: Incorporates critical ransomware features (API calls, DLL interactions, mutex operations) mapped to TTPs using the MITRE ATT&CK framework, offering a richer and more insightful feature space.
Hybrid CNN-LSTM Model: Combines convolutional and recurrent architectures to capture both spatial and temporal patterns for accurate ransomware detection.
Scalable Federated Learning: Implements training process using the Flower framework and TensorFlow, supporting multiple clients and robust aggregation mechanisms to achieve a scalable, privacy preserved and decentralized detection system
Robustness Against Adversarial Threats: Validated under FGSM and BIM attacks (both black-box and white-box), demonstrating minimal accuracy degradation (~0.20%).

System Requirements
The following dependencies are required to execute RS-FEDRAD:
Python: 3.9+
Libraries:
flwr==1.2.0
tensorflow==2.10.0
numpy==1.23.5
pandas==1.5.3
scikit-learn==1.2.2
Additional requirements can be found in requirements.txt.
Install dependencies using:pip install -r requirements.txt

Setup Instructions
1. Data Preprocessing
Navigate to the src folder and run:python src/data_preprocessing.py
This will:
Standardize, shuffle, and split the dataset.
Divide the data into 10 client-specific datasets for federated training.

2. Federated Training
A.Initialize the Flower Server: Run the server script:python src/start_server.py
The server is configured for 10 clients by default. Modify the start_server.py file to adjust the number of clients or training rounds
B.Start Clients: In parallel, execute the following command for each client:python scripts/run_federated-client.py
The server will begin training once at least 2 clients have connected. Additional clients can join during training.
C.Results:Training metrics (e.g., accuracy, precision, recall, F1-score) and history for each client are saved in results/experiment_results.

3. Adversarial Training
Follow the federated training setup, but use the adversarial client scripts:
For BIM attacks:python scripts/adversarial-bim_run_client.py
For FGSM attacks:python scripts/adversarial-fgsm_run_client.py

5. Centralized Training
Run the centralized training script:python scripts/Centralized-run.py
This script combines all client datasets into a single repository and trains the model centrally

6.Experimental Results
RS-FEDRAD achieves state-of-the-art performance with:

Accuracy: 99.90%
Average Federated Accuracy: 99.5%
Resilience to Adversarial Attacks:
Minimal accuracy degradation (~0.20%)
Visualizations in results/experiment_plots
Metrics and history in results/experiment_results












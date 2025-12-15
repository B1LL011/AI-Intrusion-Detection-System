<p align="center">
  <img src="title_icon.png" width="700">
</p>

# AI-Intrusion-Detection-System
**Group 3**

## 🧾Prerequisite

The environment needed to set up based on conda

```bash
conda create -n IDS_env python=3.10
conda activate IDS_env
pip install flask scikit-learn pandas scapy numpy joblib requests locust
```

Download (click icon) Npcap to adapt *scapy* on windows (no need for linux)

[![Multi-Modality](https://npcap.com/images/sitelogo-2x.png)]((https://npcap.com/dist/npcap-1.85.exe))

---
## 🌐Program Structure

![strktr](structure_dia.png)

---

## 🚀Quick Run 
Initially run the starter (web server) file

```conda
python app.py
```
You'll get something like this:

```output
[Collector] Sniffer started
 * Serving Flask app 'app'
 * Debug mode: on
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5000
 * Running on http://26.26.26.1:5000
Press CTRL+C to quit
 * Restarting with stat
[Collector] Sniffer started
 * Debugger is active!
 * Debugger PIN: 274-065-662
```

Then randomly choose one of the two websites to enter.

---

## 🤖Train / Retrain

*When training or retraining, suspend the real-time monitoring by clicking pause button, or there would be a concurrency problem.*
It will take a dozen seconds to train. After completing successfully, performance matrics will display below like this:

```output
{
  "AUC": 0.9991242715005394,
  "Accuracy": 0.9993853140683531,
  "Avg PFR": 0.00018087369043881765,
  "Recall": 0.996118258307724
}
```

## 📈Manual Inference (prediction)

Upload .csv file on website, and make sure whether the data is raw (aligned) or not.

## 🧪Tests 

Execute simulated attacks (DoS) by yourself using *Locust*. *Note: Turn on windows Firewall*

![locust](Locust_icon.png)

```conda
locust -f attack.py --host=http://26.26.26.1:5000
```
## 🧹Monitor in real-time 

It continues monitoring automatically, and you could decide to pause or resume.

## 🧑‍🤝‍🧑Contribution

| Name | Achievement |
|---------|------|
| Jin Wenzhuo (team leader) | Contributed to data preprocessing by designing feature selection and implementing the train/test split. Led core model evaluation by computing accuracy and recall, implemented key Flask routes, defined alert thresholds, and designed retraining trigger logic. Also supported unit testing of the preprocessing and model pipeline. |
| Li Yuanzhe  | Handled data cleaning and feature scaling during preprocessing. Contributed to model evaluation through false positive rate (FPR) analysis, implemented request validation in the Flask application, supported medium-level alert logic, compared metrics before and after retraining, and assisted with evaluation-related documentation.  |
| Li Junjie | Implemented categorical feature encoding and contributed to model evaluation by computing AUC/ROC metrics. Developed prediction display and response formatting in the Flask application, implemented high-level alert escalation, managed saving and updating retrained models, and conducted API and route testing. |
| Liu Dianyu  | Ensured feature consistency across datasets during preprocessing and contributed to metric interpretation and justification. Implemented alert logging in the Flask application, handled low-level alert logic, analyzed model adaptivity after retraining, and led the writing and organization of the final README documentation. |





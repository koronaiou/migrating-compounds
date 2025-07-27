# migrating-compounds
Welcome to the repository for "Beyond the Known: Integrated Non-Target Screening and In-Silico Toxicity Prediction of Substances Migrating from Plastic and Paper-Based Food Contact Materials"
<img width="1328" height="531" alt="graphical abstract" src="https://github.com/user-attachments/assets/355f097e-963c-4290-86da-77e57a558e7b" />

🧪 Analytical platform: UHPLC-Orbitrap Q Exactive Focus
📄 Databases: 9 FCM-related suspect lists
📊 Analysis: Cosine-based spectral matching, multivariate statistics, and toxicological relevance assessment

Workflow Guide
Follow this step-by-step process to reproduce the suspect screening and MS/MS matching workflow:

✅Step 1 – Build In-Silico Spectral Databases
-Positive Ionization Mode
Run suspect lists.ipynb to:
Load FCM-relevant suspect lists
Predict in-silico MS/MS spectra
Export a .msp-formatted library
-Negative Ionization Mode
Run suspect lists_NI.ipynb to:
Process NIAS-specific suspect lists
Generate negative-mode in-silico MS/MS spectra
Export another .msp file for use in matching

✅Step 2 – Prepare Experimental Spectra
Run extract_msms_from_experimental_spectra.ipynb to:
Extract MS/MS spectra from raw data (e.g. .mzML)
Save as a formatted .msp experimental spectral library

✅Step 3 – Match and Score Spectra
Run matching.ipynb to:
Score similarities between the in-silico and experimental spectra
Generate a ranked list of candidate matches based on cosine similarity
Run 2b_2a_matches.ipynb to:
Compare MS2 spectra from FCM extracts against MoNA database entries
Confirm or extend annotations with an external public library

| Notebook Name                                  | Description                                                                                                                               |
| ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `suspect lists.ipynb`                          | Loads suspect lists and generates an in-silico MS/MS spectral library for **positive ionization** mode.                                   |
| `suspect lists_NI.ipynb`                       | Loads NIAS-related suspect lists and generates an in-silico MS/MS spectral library for **negative ionization** mode.                      |
| `extract_msms_from_experimental_spectra.ipynb` | Extracts experimental MS/MS spectra from FCM samples and builds the experimental MSP database.                                            |
| `matching.ipynb`                               | Implements the scoring algorithm for cosine similarity and generates ranked candidate matches between in-silico and experimental spectra. |
| `2b_2a_matches.ipynb`                          | Performs final MS2 spectral comparison between FCM sample spectra and external MoNA database using cosine-based scoring.                  |


Getting Started
Requirements
Python ≥ 3.8
Jupyter Notebook
Packages:
pandas
numpy
scikit-learn
matplotlib
rdkit (optional but recommended)
tqdm
scipy

Citation
If you use this code or data in your research, please cite our corresponding publication:

Beyond the Known: Integrated Non-Target Screening and In-Silico Toxicity Prediction of Substances Migrating from Plastic and Paper-Based Food Contact Materials
Author names
Lelouda-Athanasia Koronaiou, Dimitri Abrahamsson, Junjie Yang, Loukia Daktylidi, Dimitra A. Lambropoulou


Corresponding author: Tel: +30 2310 997687, Fax: +30 2310 997799 
E-mail: dlambro@chem.auth.gr (Dr. D. Lambropoulou) 

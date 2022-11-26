---
title: Dataset
permalink: /dataset/
---

### **<span style="color:#2B547E">Seize It1 Dataset – Training set</span>**
\
This dataset is obtained during an ICON project (2017-2018) in collaboration with KU Leuven (ESAT-STADIUS), UZ Leuven, UCB, Byteflies and Pilipili. The goal of this project was to design a system using bhe EEG electrodes for monitoring the patient in a home environment. This way, a nice balance can be found between sufficient accuracy of seizure detection algorithms and wearability. The dataset was acquired in the hospital during presurgical evaluation. During such presurgical evaluation, neurologists try to see if a specific part of the brain is causing the seizures and, if so, if that part of the brain can be removed during surgery. During the presurgical evaluation, patients are monitored using vEEG for multiple days (typically a week). Patients are however restricted to move within their room because of the wiring and video analysis.

In this dataset, following data is available per patient:
- Full 10-20 scalp EEG data of the patient during the presurgical evaluation.
- Behind-the-ear data (2 electrodes positioned behind each ear)
- Single-lead ECG data (typically lead II)

Seizures are annotated by the clinicians based on the gold standard vEEG system. These seizure annotations are also available in the dataset (see below for details).

In total 82 patients were recorded between 23/01/2017 and 26/10/2018. From those patients, 54 were recorded with the behind-the-ear channels. Forty-two of those patients had seizures during their presurgical evaluation, while for twelve patients no seizure has been recorded. The number of seizures per patient ranged from 1 to 22, with a median of 3 seizures per patient. The duration of the seizures, the time difference of seizure EEG onset and end, varied between 11 and 695 seconds with a median of 50 seconds. 89% of the seizures were Focal Impaired Awareness seizures. 91% of the seizures originated from the (fronto-) temporal lobe. For more information concerning the dataset see [2]. The dataset available for participants will contain the data of the 42 patients who had epileptic events during the recording period.


#### Data format:

The raw data is in the form of **.edf** (European Data Format). The annotations are provided in **.tsv** (tab separated values) files. For every seizure, the first column represents the starting point (in seconds) of the seizure, the second one the end point of the seizure, the third one the type of the seizure, while in the last column extra information are provided. The extra information includes the origin of the seizure, the hemisphere and if the seizure can be noted from the behind the ear channels (bhe:1 in that case).  In the header section of every file information concerning the dataset and the annotations used are included.

For every subject and for every session (even if no seizure is present) two different sets of annotations are provided. The _"a1"_ set of annotations is the annotations as provided by the doctors. The _"a2"_ set of annotations are the annotations used in [2] for training of the algorithm. The annotations provided from the doctors were not always perfectly aligned with the typical rhythmic ictal pattern, hence in _"a2"_ a refinement of the start of each annotation was performed visually by an engineer. Furthermore, in the annotations of the doctor, the end point of some seizures was missing ("none") in the _"a2"_ subset of annotations each seizure was considered with a stable length of 10 seconds. The participants can use any of the two sets of annotations or a combination of both. 

&nbsp;  

### **<span style="color:#2B547E">SeizeIT2 Dataset – Validation and test set</span>**
\
The SeizeIT2 dataset is an international multicenter dataset (containing EEG and ECG) with more than 350 patients suffering from epilepsy and recorded both in home and hospital environments (the first ever phase-4 clinical trial for a wearable for in home monitoring for seizure detection). The data are acquired with the SD device and the current study is an extension of SeizeIT1 and part of a larger multicenter trial with focus on clinical validation of the SD in people with typical absence, focal impaired awareness, and generalized tonic–clonic seizures. SeizeIT2 unites public and private stakeholders to address an unmet patient need. This is a continuation of SeizeIT1 ICON project, led by UCB, with partners from Un. de Navarra, Karolinska Institutet, KU Leuven, RWTH Aachen, Universitäts klinikum Aachen, Centro Hospitalar e Universitário de Coimbra, Oxford University Hospitals NHS Foundation Trust and Stockholms Läns Landsting. 
Patients underwent video-EEG monitoring using the standardized 25-electrode array of the International Federation of Clinical Neurophysiology. Behind each ear, two additional Ag/AgCl cup electrodes were attached on the mastoid bone for concomitant recording with the SD. The closest corresponding electrodes on 25-channel EEG were T7 and T8 for the top electrode and P9 and P10 for the lower electrode. The SD was attached on the upper back using a patch, and two bipolar channels were created by connecting the ipsilateral top and lower electrode. Impedance was ≤5 kΩ at the beginning and checked throughout. The sampling rate of the SD and video-EEG was 250 Hz.

In the context of this challenge the data for the in-hospital recordings of the patients in UZ Leuven will be used for the test set, but also for validation set. The SD recordings from 2 patients  will be provided to the participants in order to validate the performance of their models. All the models will be tested in the remaining 31 adult patients from UZ Leuven with focal seizures, by the organizers. 

#### Data format:

Similar to the SeizeIT1 dataset, the raw EEG and ECG data is in the form of **.edf**. The annotations for the validation set are also provided in **.tsv** files, where the first column represents the start of the seizure and the second the end (in seconds). For this dataset, only the annotations provided by the neurologist are present (_a1_).

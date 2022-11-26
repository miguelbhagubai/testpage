---
title: Regulations
permalink: /regulations/
---


### **<span style="color:#2B547E">Rules</span>**
\
Participants are subject to the following rules:

- Participants must register via the [registration form]({{ '/register/' | relative_url }}). After the registration, the participants will receive instructions and will be granted access to the dataset and code when released and instructions on how to upload their submissions.

- The participation of groups is encouraged. Each group/participant can submit only once, either as an individual or as a team. It is not possible to submit both individually and as a team.

- The data can only be used in the context of the ICASP 2023 Grand Challenge. For any other use of the data the participants must contact Prof. Wim Van Paesschen (wim.vanpaesschen@uzleuven.be).

- The participants ranking in the top 5 upon centralising results for all submissions will be invited to to submit a 2-page paper and present it at ICASSP 2023 (more information [here](https://2023.ieeeicassp.org/call-for-sp-grand-challenges/)).

- The organizers, based on the amount and quality of submissions, will explore the possibility of hosting an article collection (Research Topic) on a related journal.

&nbsp;  

### **<span style="color:#2B547E">Evaluation Criteria</span>**
\
Researchers in ML typically report performance in terms of sensitivity and specificity. Seizure detection is usually a problem with a high imbalance between classes, since seizure events are rare within the datasets. In these cases, False Alarm (FA) rate is commonly used instead of specificity. FA rate is simply the number of false positives divided by the total duration of the recordings and normalized to one hour (FA/h).

In the current use case scenario, in which we use the automatic seizure detection for automated seizure diaries, sensitivity is important, and none of the seizure events should be missed. Hence, the sensitivity will be measured on an event basis which does not consider individual windows. To compute sensitivity, the any-overlap method (OVLP) [6] will be employed. True Positives (TPs) are counted when the hypothesis has any overlap with the corresponding event in the ground truth annotation. False Positives (FPs) or FAs correspond to situations in which a hypothesis does not overlap with the corresponding event in the reference. OVLP is a more permissive metric and tends to produce higher sensitivities and lower FAs rates. The metric ignores the duration of the term in the provided annotation; hence, longer events will provide better scores. Accounting for the under-reporting of FAs by the OVLP method, we will combine two methods in our scoring formula. Sensitivity will be computed based on OVLP, as mentioned, and FAs rate will be based on epoch-based scoring. EPOCH [7] treats the reference and hypothesis as time series. These signals are sampled at a fixed window length (epoch duration). The corresponding label in the reference is compared to the hypothesis for each epoch. Any possible substitutions, deletions, or insertion errors are tabulated with an equal weight of 1.0 for each type of error.

A weighting factor of 0.01 will be used in order to balance sensitivity and FA rate and provide the scoring points. The same formula will be used for both tasks and the scores will be averaged with weight 0.6 for task 1 and 0.4 for task 2. In case that a participant submits a model only for one of the tasks, the other task will be graded with the minimum grade obtained of all the other submissions.

\
![Scoring]({{ '/assets/theme/images/score.png' | relative_url }})
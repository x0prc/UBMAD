# UBMAD
## 🕷️ User Behavior Modeling and Anomaly Detection

This repository is based on my understanding and implementation of the algorithms published in Paper : 

`Kim, Junhong, Minsik Park, Haedong Kim, Suhyoun Cho, and Pilsung Kang. 2019. "Insider Threat Detection Based on User Behavior Modeling and Anomaly Detection Algorithms" Applied Sciences 9, no. 19: 4018. https://doi.org/10.3390/app9194018`

## 🔨 Background
<details>
<summary>Abstract from the Paper</summary>
Insider threats are malicious activities by authorized users, such as theft of intellectual property or security information, fraud, and sabotage. Although the number of insider threats is much
lower than external network attacks, insider threats can cause extensive damage. As insiders are very
familiar with an organization’s system, it is very difficult to detect their malicious behavior. Traditional
insider-threat detection methods focus on rule-based approaches built by domain experts, but they
are neither flexible nor robust. In this paper, we propose insider-threat detection methods based on
user behavior modeling and anomaly detection algorithms. Based on user log data, we constructed
three types of datasets: user’s daily activity summary, e-mail contents topic distribution, and user’s
weekly e-mail communication history. Then, we applied four anomaly detection algorithms and
their combinations to detect malicious activities. Experimental results indicate that the proposed
framework can work well for imbalanced datasets in which there are only a few insider threats and
where no domain experts’ knowledge is provided.
</details>


## ❓ Problem Statement
<details>
<summary>Section 1 : Introduction</summary>
From a modeling perspective, it is virtually impossible to train a binary classification algorithm when only a few abnormal examples
exist [19]. Under this class imbalance circumstance, most statistical/machine learning algorithms tend
to classify all activities as normal, which results in a useless insider-threat detection model. To resolve
these shortcomings, the paper has proposed an insider-threat detection framework based on user activity modeling
and one-class classification.
</details>

## 💽 Dataset
<details>
<summary>CERT Dataset</summary>
Because it is very difficult to obtain actual corporate system logs, authors used the “CERT Insider
Threat Tools” dataset (Carnegie Mellon’s Software Engineering Institute, Pittsburgh, PA, USA) [20].
The CERT dataset is not real-world enterprise data, but it is an artificially generated dataset created for
the purpose of validating insider-threat detection frameworks [1].
The CERT dataset includes employee computer usage logs (logon, device, http, file, and email)
with some organizational information such as employee departments and roles. Each table consists of
columns related to a user’s ID, timestamps, and activities. The CERT dataset has six major versions
(R1 to R6) and the latest version has two variations: R6.1 and R6.2. The types of usage information,
number of variables, number of employees, and number of malicious insider activities are different
depending on the dataset version. Authors conducted this study using R6.2, which is the latest and
largest dataset. In this version, the dataset includes 4000 users, among whom only five users behaved
maliciously.

  `Lindauer, Brian (2020). Insider Threat Test Dataset. Carnegie Mellon University. Dataset. https://doi.org/10.1184/R1/12841247.v1`
</details>

## 💡 Solution Statement
<details>
<summary>Three Mainstream Strategies</summary>
<p>The first strategy is to develop a rule-based detection system. A pool of experts generates a set of rules to identify insiders’ malicious activities. Then, each user’s behavior is recorded as a log and is tested to determine whether it meets any of the pre-designed rules.</p>

<p>The second strategy is to build a network graph to identify suspicious users or malicious behaviors by monitoring the changes of the graph structure. Graph-based insider threat identification
does not only analyze the value of the data itself but also analyzes the relationships among the data.</p>

<p>The third strategy is to build a statistical or machine learning model based on previous data to predict potential malicious behavior. Insider threat detection using machine learning aims at developing a method to automatically identify users who perform unusual activities among all users without prior knowledge or rules.</p>
</details>


## 🎨 Project Design
![FLOWCHART drawio](https://github.com/x0prc/UBMAD/assets/105520102/64aeb788-9f2a-461a-8499-a6fdcf1e90bc)

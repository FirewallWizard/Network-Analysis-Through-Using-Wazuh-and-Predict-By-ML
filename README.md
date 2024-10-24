# Network-Analysis-Through-Using-Wazuh-and-Predict-By-ML
Introduction
In the ever-evolving landscape of cybersecurity, the need for robust and intelligent threat detection mechanisms has become increasingly crucial. Traditional security approaches often struggle to keep pace with the growing complexity and sophistication of cyber threats. This project explores the integration of Machine Learning into the threat detection process, leveraging the Wazuh open-source security platform to enhance the efficiency and effectiveness of cybersecurity operations.
Objective
The primary objective of this capstone project is to develop and implement a machine learning threat detection system for network analyses, utilizing the Wazuh security platform. The goal is to improve the organization’s ability to identify, analyze, and respond to potential security threats in a timely and effective manner.
Project Scope
The scope of this project encompasses the following key elements:
• Integrating ML-based threat detection capabilities into the Wazuh security platform
• Developing and training machine learning models to analyze network traffic and identify
anomalies or suspicious activities
• Implementing a comprehensive threat detection and response workflow within the Wazuh
ecosystem
• Evaluating the performance and effectiveness of the AI-powered threat detection system
• Providing recommendations for future enhancements and scalability

Detailed Analysis of How the Technology Works

The AI-powered threat detection system implemented in this capstone project leverages machine learning algorithms and deep learning techniques to analyze network traffic and identify potential security threats. The key components of the system are as follows:

1. Data Collection and Preprocessing: The Wazuh security platform collects and aggregates various security-related data, including network traffic logs, user activity logs, and threat intelligence feeds. This data is then preprocessed and transformed into a format suitable for machine learning models.

2. Feature Engineering: The preprocessed data is used to engineer relevant features that can be used by machine learning models to detect patterns and anomalies. This may include features such as network flow characteristics, user behavior metrics, and indicators of compromise.

3. Model Training and Deployment: The engineered features train supervised and unsupervised machine learning models, such as random forests, support vector machines, and deep neural networks. These models are then deployed within the Wazuh platform for real-time threat detection and analysis.

4. Threat Detection and Response: The AI-powered threat detection system continuously monitors network traffic and other security-related data, using trained machine learning models to identify potential threats. When a threat is detected, the system triggers automated incident response workflows within the Wazuh platform, such as generating alerts, blocking malicious traffic, and initiating remediation actions.

5. Continuous Learning and Optimization: The AI-powered threat detection system is designed to learn and adapt over time, incorporating new threat intelligence and security data to improve its detection accuracy and reduce false positive rates.

SOC Analyst Role
To gain live data, we performed an SIEM Lab where Wazuh was our primary tool for data collection. Using Wazuh we collected threatful and benign data in the network. An attacker tried to compromise one of the systems using a DDoS attack. In which he sent a heavy payload of ICMP traffic. Below is the network diagram for the created topology of the attacking environment:

![image](https://github.com/user-attachments/assets/5432d9b8-6291-4159-90f2-14a05ea8c7ee)


Figure 1: SIEM Network Diagram
The above image is the network topology of the SIEM Lab over which data collection is performed

![image](https://github.com/user-attachments/assets/173629e5-7c08-4516-95eb-5c65d34bd5f4)

Figure 2: Wazuh Dashboard
Added Windows agent on wash and deployed related services.

![image](https://github.com/user-attachments/assets/dea8fa77-16f3-4253-84e7-6ad6f983f014)

Figure 3: Adding Wazuh Agent
The above screenshot is the dashboard showing detailed information about the agent.

![image](https://github.com/user-attachments/assets/5e3eacf2-f665-4346-b865-2d6bc42df217)

Figure 4: Creating a custom dashboard
Here we have designed our custom dashboard for our use.

![image](https://github.com/user-attachments/assets/a73bd64f-7bc4-43f6-80cf-924d9922f236)

Figure 5: Getting event logs
Triggering events from Sysmon

![image](https://github.com/user-attachments/assets/af408f0e-16b3-4408-acf1-56d269e265e3)

Figure 6: Event files
Getting logs from Sysmon in the Event viewer
![image](https://github.com/user-attachments/assets/bb3d7186-9906-4d38-a142-d17c119d1f56)


Figure 7: Wireshark

![image](https://github.com/user-attachments/assets/90d90f1e-0db3-444b-b4c4-6682116c337c)

Figure 8: .PCAP to. CSV


I am converting the captured data of Wireshark into CSV for ML procedures.

Data Analyst Role
For the Machine learning part of the project, we will refer to the following diagram:

![image](https://github.com/user-attachments/assets/c4cfcc85-6382-480d-b85c-26cdb716c460)

Figure 9: Data processing in Machine Learning

Working on the data processing:

1. Wire shark provides the feed to the Wazuh user and then a SOC analyst converts the.PCAP file to a . CSV file

2. This CSV file having all the packet data information is classified as “Threat” and “Benign” traffic

3. After getting the Classified CSV file, the data analyst performs feature extraction, count vectorizer, and data cleaning

4. The main CSV file is then split into a training dataset and a testing dataset in the ratio of 80- 20%

5. Then data variables are created which exclude nonnumerical columns and Classification columns

6. A Machine Learning model is trained, in our case we used a Random Forrest Classifier

7. After we get our trained model we then predict Classification for our testing dataset

8. And based on the output we get a higher understanding of the malicious and benign data traffic Below are practical screenshots taken when performing this technology:

![image](https://github.com/user-attachments/assets/38f1f6d1-089c-4bb5-b83e-3959980f0f76)

Figure 10: Running Python code

The above Python includes several technologies such as Machine learning modules and libraries, FLASK, HTML, and many more which collectively work together to provide desired output. This code trains the model, creates job libraries, and runs the FLASK application.

![image](https://github.com/user-attachments/assets/93cae1e9-ad9e-4c8c-8b2d-4baf8da18890)

Figure 11: Upload portal

The above portal is accessed on a web browser using FLASK and HTML. A user can upload their testing data set to test with the already trained model.

![image](https://github.com/user-attachments/assets/dabbbc8e-dadc-4d05-8ee7-d2a1e5ea20bd)

Figure 12: Analysis Dashboard

The above image is the next page you get after you upload the testing dataset. Here the analysis of the testing dataset concerning our trained model is performed. Here we can see that there is a ton of information for a security analyst. Here we got accuracy scores, classification reports, and feature-based histograms.

Project Code Snippets: Vectorize_&_split.py
![image](https://github.com/user-attachments/assets/4dc54131-c2a5-49d3-9d4f-525210394b65)
![image](https://github.com/user-attachments/assets/3285616f-d242-4756-9b0f-92bc282d6f85)


Main.py

![image](https://github.com/user-attachments/assets/c3bac699-5f7d-4016-9e69-e1ca3b313e22)
![image](https://github.com/user-attachments/assets/9c20a462-1803-4613-bf2f-f022328f5f5e)




Summary and Learning

This capstone project has demonstrated the significant potential of integrating Artificial Intelligence into the threat detection process, leveraging the Wazuh open-source security platform. Implementing the AI-powered threat detection system has resulted in improved threat detection accuracy, faster incident response, and increased operational efficiency for the organization. The key learnings from this project include:

· The importance of aligning the AI-powered threat detection system with the organization’s specific security requirements and threat landscape.

· The value of a comprehensive data collection and preprocessing strategy to ensure the accuracy and effectiveness of the machine learning models.

· The need for continuous monitoring, optimization, and adaptation of the AI-powered threat detection system to keep pace with the evolving threat landscape.

· The significance of integrating the AI-powered threat detection system with the organization’s existing security tools and processes to ensure seamless and effective security operations.

Future Scope

The following are the future scope for this particular project:

· Model improvements: The feature extraction and classification of the data needs more work to incorporate this solution into real-world scenarios

· Different training models should be tested against different training data to grow the overall threat detection horizon

· Data collection and processing needs more work such that incorporation of data augmentation is required to expand training data sets

· Scalability to the cloud. Cloud integration can be a good choice of implementation to gain exposure to powerful computing

· User interface can be enhanced by implementing many modern technologies such as CSS

· APIs (Application Programming Interface) can be built over this concept such that the benefits of such great applications can be used in various points of workings

Conclusion

The Capstone Project, “Threat Detection Using Machine Learning,” effectively showed the integration of AI with the Wazuh platform to improve cybersecurity. By utilizing machine learning models, the study greatly enhanced network threat detection, demonstrating AI’s promise in cybersecurity. The installation of automated response procedures inside Wazuh demonstrated a proactive approach to threat mitigation. This attempt not only achieved its goals but also provided the groundwork for future advances in the discipline. The initiative emphasized the significance of continual learning and adaptability in AI models to stay up with new cyber threats. It demonstrated the power of AI in automating and enhancing threat detection and response operations. The proof-of-concept proved the AI system’s practical feasibility and operational advantages.

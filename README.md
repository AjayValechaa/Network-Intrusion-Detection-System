# Network-Intrusion-Detection-System

Background
In this project, we developed a Network Intrusion Detection System using supervised and unsupervised data mining models for classification. The dataset used for network_traffic.csv. We performed exploratory data analysis and multiple factor analysis to understand the nature and patterns in intrusions. After exploration, we decided to use 4 models that work well for binary classification. We used Logistic Regression, KNN,Decision Trees and Random Forest and Gradient Boosting Machine. After building our models we evaluated the models using confusion matrix and ROC/AUC plots. In the end we present out findings and the model bank should choose for intrusion detection.

Motivation
After discovering unusual activity on the Bank’s networking system, many other such instances of anomalous network activity were found which have resulted in significant sums of money being siphoned from bank accounts of the customers. Using a synopsis of logged network activities (containing benign network sessions as well as intrusions), we are trying to build and train a model with high accuracy intrusion detection.

Data
Our dependent variable is is_intrusion which contains 1 if the session resulted in an intrusion; 0 otherwise (data type: discrete)

network_traffic.csv has the following predictor variables :

duration: contains the length of the connection in seconds (data type: continuous)

protocol_type: contains details on the type of the protocol, e.g. tcp, udp, etc.(data type: discrete)

service : contains details on the network service on the destination, e.g., http, telnet, etc.(data type: discrete)

src_bytes : contains the number of data bytes from source to destination (data type: continuous)

5.dst_bytes : contains the number of data bytes from destination to source (data type: continuous)

flag : contains details on the normal or error status of the connection (data type: discrete)

land : contains 1 if connection is from/to the same host/port; 0 otherwise (data type: discrete)

wrong_fragment : contains number of ``wrong’’ fragments (data type: continuous)

urgent: contains number of urgent packets(data type: continuous)

hot : contains number of ‘’hot’’ indicators (data type: continuous)

num_failed_logins : contains number of failed login attempts (data type: continuous)

logged_in : contains 1 if successfully logged in; 0 otherwise (data type: discrete)

num_compromised: contains the number of ‘’compromised’’ conditions (data type: continuous)

root_shell : contains 1 if root shell is obtained; 0 otherwise (data type: discrete)

15.su_attempted : contains 1 if ‘’su root’’ command attempted; 0 otherwise (data type: discrete)

num_root : contains the number of ‘’root’’ accesses (data type: continuous)

num_file_creations : contains the number of file creation operations (data type: continuous)

num_shells: contains the number of shell prompts (data type: continuous)

num_access_files: contains the number of operations on access control files (data type: continuous)

num_outbound_cmds: contains the number of outbound commands in an ftp session (data type: continuous)

is_hot_login: contains 1 if the login belongs to the ``hot’’ list; 0 otherwise (data type: discrete)

is_guest_login : contains 1 if the login is a ``guest’’login; 0 otherwise (data type: discrete)

Findings and Conclusion
We find that several models perform well. The KNN, Logistic and GBM models each have similar performance on the validation set. Further, the AUC measures are all only marginally different

We find that several models perform well. The KNN, Logistic and GBM models each have similar performance on the test set. Further, the AUC measures are all only marginally different.

We believe the logistic model and GBM have the most promise. RF performed worse on Sensitivity. Such false negatives can be especially costly in this setting, and so this model should not be used. KNN, meanwhile, is computationally expensive. Since it is not a parametric model, it must search through the dataset each time it classifies a point. This can take a long time with a large dataset, which is detrimental for the purposes of real-time execution.

The logistic model’s strength is in its simplicity and interpretability. If the bank is concerned with identifying KNOWN attack vectors, the logistic model can provide a straightforward way to update and maintain a model that readily identifies known attacks.

Note: The files in this repository are uploaded in retrospection.

Date: Spring 2020 | Collaborators: Daniel Schnelbach, Chetna Bakhshi, Akshay Oza, Ajay Valecha

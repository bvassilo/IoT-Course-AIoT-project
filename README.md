# AIoT Project - Human Gesture Recognition

### An End-to-end Artificial Intelligence of Things Project

## Project Description

In this project, you are prompted to create an end-to-end Artificial Intelligence of Things (AIoT) procedure in order 
to recognize a set of gestures automatically. This problem is identified as Human Gesture Recognition (HGR), which is 
actually the technology that uses sensors to read and interpret hand movements as commands. Nowadays, HGR has multiple 
uses in various domains, such as healthcare, industry, gaming, etc. In the automotive industry, for instance, this 
capability allows drivers and passengers to interact with the vehicle — usually to control the infotainment system 
without touching any buttons or screens

In particular, you will take advantage of the Mbientlab’s sensorial device, MetaMotionR research sensor kit [1], and 
its wristband [2], which is a wrist-worn device that provides recorded (logging) or real-time (streaming) sensor data. 
The sensor kit embeds the Bosch BMI160 Inertial Measurement Unit (IMU), which is a small, low power, low noise 16-bit 
inertial measurement unit designed for use in mobile applications like augmented reality or indoor navigation which 
require highly accurate, real-time sensor kinesiological data. In full operation mode, the user can enable both the 
accelerometer and gyroscope sensors to collect the movement data. The device, the wristband, and the embedded IMU are 
presented in Figure 1. 

For the data collection procedure, you can utilize the mobile and desktop open-source applications (MetaWear, 
MetaBase) that Mbientlab provides in the Apple Store (Mac, iPhone), the Play Store, and the Windows Store:

* [Mbientlab MetaWear and MetaBase Apps for iOS and macOS on App Store](https://apps.apple.com/us/developer/mbientlab-inc/id920878580)
* [Mbientlab MetaWear App on Play Store](https://play.google.com/store/apps/details?id=com.mbientlab.metawear.app)
* [Mbientlab MetaBase App on Play Store](https://play.google.com/store/apps/details?id=com.mbientlab.metawear.metabase)
* [Mbientlab MetaBase on Microsoft Store](https://apps.microsoft.com/store/detail/metabase/9NBLGGH4TXJ3)


As an alternative option, you can use the MetaWear APIs the company provides in Java, Swift, Javascript, Python, and 
C++ programming languages:

* [MetaWear APIs](https://mbientlab.com/tutorials/MetaWearAPI.html)

![](img/AIoT_course_MMR.png)
*Figure 1. From left to the right. a) the MetaMotionR research sensor kit, b) its wristband, and, c) the embedded 
Bosch BMI160 Inertial Measurement Unit (IMU).*

For the learning scenario, you can select one of the activities’ classes to monitor as they are presented in the 
publications: a) Figure 8 in publication [3], b) Select a set of classes in Table 1 of publication [4], or in Figure 2 
of publication [5]. For the data engineering and preparation, it is suggested to follow some of the methodologies that 
are presented in a) [6], in sections II, III, and IV, b) [3], in section 2, c) [5], in sections B, C, D, E, and 
finally, d) [7], in sections III, IV, V. However, it is suggested to read the whole papers in order to better 
understand the identification scenario. Finally, you will train the models either with time-series series data 
(after the data engineering and preparation), defining a 1D problem solution, or in the form of spectrograms, i.e. 
a 2D solution.

**Note**: A Jupyter Notebook with coding hints will be provided with the project’s official announcement.

## Data Collection

1.	You familiarize with the wearable and select one or more of its sensors that indicate movement, i.e. accelerometer 
and/or gyroscope
2.	You use the wearable for X days and collect sensor data regarding the gesture scenario you want to monitor.
3.	You collect and annotate the data based on the gesture classes you want to train the AI model.
4.	Visualize the sensor data in the following ways: a) Accelerometer data (3-axis), b) Gyroscope data (3-axis), 
c) Accelerometer and Gyroscope data (6-axis).

## Data Engineering

1.	Split the data into fixed windows of X seconds with X% overlap.
2.	Filter the data with a low-pass filter at a frequency of X Hz.
3.	Transform the data into the frequency domain (in the case only of addressing the problem as 2D)
4.	Visualize a time-series (or spectrogram) instance of the transformed dataset to see the effect of the filter 
to the signal.

## Data Preparation

1.	Split the data into train and test sets (in the case of Neural Networks usage, split the data into 
train/validation/test sets).
2.	Use a scaling algorithm to normalize the data into a standard value range (Standardization, 
Min Max Normalization)
3.	Perform dimensionality reduction (if needed) by using Principal Component Analysis (PCA) or Linear Discriminant 
Analysis (LDA)
4.	The data is in proper format to feed the AI model.

## 

1.	Select a supervised Machine Learning approach to perform the gesture recognition scenario. For instance, you can 
use Support Vector Machines (SVM) or a Neural Network architecture (Convolutional Neural Networks are suggested).
2.	Fit the data into the model
3.	Evaluate the AI model performance in the form of: a) Learning curves during the training procedure: Accuracy, Loss.
b) Confusion Matrix and Classification Report by using the evaluation metrics that arise from the True Positives, 
False Positives, True Negatives, False Negatives classification results.

**Note**: You can select and deploy any of the AI models that are presented in the bibliography section.

## Report

Provide us with:
* A link in Google Drive or One Drive that contains the collected dataset with its annotated metadata, as well as a 
max 1 page report related to the data collection procedure, the classes, how the data was annotated, the controlled 
environment, etc. 
* The code used to convert the CSV data into a format (data engineering, data preparation), capable of training the 
models.
* The code used to train and evaluate the models. 
* The code could be in a notebook or in scripting format, however, a README of how to automatically run the data 
loading, data processing, model training, and model evaluation process as one should be delivered. 
* A short report (~1 page) describing the process that you took to convert the data and generate the model. Include 
your observations on the accuracy of the model regarding the classes’ identification.

## Bonus

* Fine-tune the end-to-end pipeline. 
* Use more than one AI models (e.g., CNNs, RNNs, statistical models) to compare their performance.

## Technologies

* AI modeling: scikit-learn, TensorFlow 
* Data Engineering: NumPy, SciPy, pandas 
* Data preparation: scikit-learn 
* Visualization: Matplotlib, seaborn

## References

[1] "MMR – MetaMotionR," Mbientlab, [Online]. Available: https://mbientlab.com/store/metamotionr/.

[2] Mbientlab, "Wrist Band Kit for MMC and MMR," Mbientlab, [Online]. Available: https://mbientlab.com/store/wristband-sensor-research-kit/.

[3] Iyer, Darshan, Fahim Mohammad, Yuan Guo, Ebrahim Al Safadi, Benjamin J. Smiley, Zhiqiang Liang, and Nilesh K. 
Jain., "Generalized hand gesture recognition for wearable devices in IoT: Application and implementation challenges.," 
in Machine Learning and Data Mining in Pattern Recognition: 12th International Conference, MLDM 2016, New York, NY, 
USA, 2016. 

[4] Xu, Chao, Parth H. Pathak, and Prasant Mohapatra., "Finger-writing with smartwatch: A case for finger and hand 
gesture recognition using smartwatch," in 16th International Workshop on Mobile Computing Systems and Applications, 2015. 

[5] Liu, Fang-Ting, Yong-Ting Wang, and Hsi-Pin Ma., "Gesture recognition with wearable 9-axis sensors.," in 
International Conference on Communications (ICC),, 2017. 

[6] Tzamalis, Pantelis, Andreas Bardoutsos, Dimitris Markantonatos, Christoforos Raptopoulos, Sotiris Nikoletseas, 
Xenophon Aggelides, and Nikos Papadopoulos., "End-to-end Gesture Recognition Framework for the Identification of 
Allergic Rhinitis Symptoms.," in 2022 18th International Conference on Distributed Computing in Sensor Systems (DCOSS), 
Marina del Rey, Los Angeles, CA, USA, 2022. 

[7] Zhu, Peide, Hao Zhou, Shumin Cao, Panlong Yang, and Shuangshuang Xue., "Control with gestures: A hand gesture 
recognition system using off-the-shelf smartwatch.," in IEEE, 4th International Conference on Big Data Computing and 
Communications (BIGCOM), 2018. 

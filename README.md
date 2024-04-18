# AIoT Course - Human Gesture Recognition Project

**An End-to-end Artificial Intelligence of Things Project**

This is a repository that contains the demonstration of the Human Gesture Recognition of AIoT lectures which are
part of the course "Algorithmic Foundations of Sensor Networks" in the Computer Engineering and Informatics Department, 
University of Patras.

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
publications: 
1. Figure 8 in publication [3]
2. Select a set of classes in Table 1 of publication [4]
3. Figure 2 of publication [5] 

For the data engineering and preparation, it is suggested to follow some of the methodologies that 
are presented in:
1. [6], in sections II, III, and IV.
2. [3], in section 2.
3. [5], in sections B, C, D, E.
4. [7], in sections III, IV, and V.

However, it is suggested to read the whole papers in order to better 
understand the identification scenario. Finally, you will train the models with time-series series data 
(after the data engineering and preparation), defining a 1D problem solution.

**Note**: Jupyter Notebooks with coding hints will be provided with the project’s official announcement.

## Instructions for data collection

Based on your movements collection definition, please, use accelerometer and/or gyroscope.

1. You familiarize with the wearable and select one or more of its sensors that indicate movement, i.e. accelerometer 
and/or gyroscope
2. To properly collect the instances, you must be careful the data to contains exactly the instances of interest. This 
means that the recording of the data collection must start while you perform the gesture repetitively, and terminate the
recording before you stop performing the gesture.
3. You use the wearable for X days and collect sensor data regarding the gesture scenario you want to monitor. 
4. You collect and annotate the data based on the gesture classes you want to train the AI model. 
5. Visualize the sensor data in the following ways: 
   1. Accelerometer data (3-axis)
   2. Gyroscope data (3-axis)
   3. Accelerometer and Gyroscope data (6-axis).

**Note: Collect a representative dataset, meaning each class should have almost the same time-length of instances in 
total.**

## Configuration

As the majority of software projects work with configuration files to set up the instantiation of their
components or experiments, we follow the same principle in this project too.

Thus, a configuration file should contain all the parameters set up that are utilized for the project. To use this file, 
please, copy and rename the `config.yml.template` which is located in the root directory to `config.yml`.

The file should contain all parameters regarding the MongoDB host, the database name, the collection name, as well as
parameters about the data engineering and the learning processes.


## Dataset creation

1. Follow the folder and files structure guideline which can be found in `data/README.md`.
2. Instantiate a `mongod` primary daemon process for the MongoDB system.
3. Based on the instructions in `aiot_dataset_creation.ipynb`:
   1. Create the database and the collection you will save your data.
   2. Transform the data in the proper MongoDB's document format.
   3. Upload the data to your collection.


**Note**: Use the MongoDB Compass GUI to check your databases and collections:

* https://www.mongodb.com/products/compass

    
## Exploratory Data Analysis and Data Engineering

For the Exploratory Data Analysis (EDA) and the Data Engineering process for both a single instance, and
the whole dataset, you are prompted to implement and run the following steps:
1. Provide a barplot that contains the time-length of the collected instances for each class.
2. Split the data into fixed windows of X seconds with X% overlap (in samples). 
3. Provide a barplot with the count of instances that occurred after this process, for each class.
4. Filter the data with a low-pass filter at a frequency of X Hz. 
5. Transform the data into the frequency domain (in the case only of addressing the problem as 2D)
6. Visualize a time-series instance of the transformed dataset to see the effect of the filter 
to the signal.

**Note**: Depending on the sensors you will exploit for your project, there is a chance you have to modify either 
the configuration or some of the functions.


## Data Preparation

1. Split the data into train and test sets (in the case of Neural Networks usage, split the data into 
train/validation/test sets). 
2. Use a scaling algorithm to scale the data into a standard value range (Standardization, 
Min Max Normalization)
3. Perform dimensionality reduction (if needed) by using Principal Component Analysis (PCA)
4. The data is in proper format to feed the AI model.

**Note**: You can use any of the steps of data engineering or preparation as many times as you wish
until you achieve the desired results.

## Learning Process (AI Modeling)

1. Select a supervised Machine Learning approach to perform the gesture recognition scenario. For instance, you can 
use Support Vector Machines (SVM) or a Neural Network architecture (Convolutional Neural Networks are suggested). 
2. Fit the data into the model. 
3. Evaluate the AI model performance in the form of Confusion Matrix and Classification Report by using the evaluation 
metrics that arise from the True Positives, False Positives, True Negatives, False Negatives classification results.

**Note**: You can select and deploy any of the AI models that are presented in the bibliography section.


## Report

Provide us with:
* A link in Google Drive or One Drive that contains the collected dataset with its annotated metadata, as well as a 
max 1 page report related to the data collection procedure, the classes, how the data was annotated, the controlled 
environment, etc. 
* The code used to convert the CSV data into a format (data engineering, data preparation), capable of training the 
models.
* The configuration file in order for us to run your code based on your settings you chose or created to converge to 
your optimal solution.
* The code used to train and evaluate the models. 
* The code could be in a notebook or in scripting format, however, a `README.md` of how to automatically run the data 
loading, data processing, model training, and model evaluation process as one should be delivered. 
* A short report (~1 page) describing the process that you took to convert the data and generate the model. Include 
your observations on the accuracy of the model regarding the classes’ identification.

**Important Note:** *Feel free to change any part of code in utilities functions or even create your own. However, you have to 
describe and explain how you decided to proceed with any changes.*


## Bonus

* Fine-tune the end-to-end AI pipeline (e.g., use Exhaustive Grid Search algorithm). 
* Use more than one AI model (e.g., CNNs, RNNs, statistical models) to compare their performance.
* Plot the `architecture` of ot the TensorFlow model
* Print the `summary` of the TensorFlow model
* Evaluate the Neural Network training procedure and its performance on the test set by plotting the 
Learning curves during the training procedure: Accuracy, Loss.
* Interpret the results


## Technologies

The following list provides all the necessary Python packages that can be exploited for the project needs:

* Data Engineering: NumPy, SciPy, pandas 
* Data preparation: scikit-learn
* Visualization: Matplotlib, seaborn, pandas
* AI modeling: scikit-learn, TensorFlow 

However, the whole Python environment setup can be found in the `requirements.txt` file in the root directory.

If you need some extra knowledge of how to utilize Pandas, NumPy, MatplotLib, seaborn, scikit-learn, and other 
Data Science stuff, you can read and experiment with the tutorials that can be found here:

* [Python Data Science and Machine Learning Tutorials](https://github.com/tzamalisp/data-science-and-machine-learning-tutorials)


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

[8] Tzamalis, Pantelis., "Python Data Science and Machine Learning Tutorials", [Online]. Available: https://github.com/tzamalisp/data-science-and-machine-learning-tutorials

## Important Notes

* Anouncement date: 02 May, 2023 
* Delivery Date: 02 June, 2023

## Contact

Dr. Pantelis Tzamalis
* email: [tzamalis@ceid.upatras.gr](mailto:tzamalis@ceid.upatras.gr)
* GitHub: [https://github.com/tzamalisp](https://github.com/tzamalisp)
* Website: [https://tzamalisp.github.io)](https://tzamalisp.github.io)
* Social: [https://www.linkedin.com/in/pantelis-tzamalis/](https://www.linkedin.com/in/pantelis-tzamalis/)

Ph.D. George Kontogiannis
* email: [george.k.kontogiannis@gmail.com](mailto:george.k.kontogiannis@gmail.com)
* GitHub: [https://github.com/gkontogiannhs](https://github.com/gkontogiannhs)
* Social: [https://www.linkedin.com/in/george-kontogiannis/](https://www.linkedin.com/in/george-kontogiannis/)

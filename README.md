# Comparing performances of QSVM for different feature maps using the Iris Dataset


In this project I have used different feature maps (ZFeatureMap, ZZFeatureMap, Angle Encoding, Amplitude Encoding)  for generating a Quantum-enhanced Support Vector Machine (QSVM) algorithoms to classify the three classes(setosa, versicolor, virginica) of the IRIS Dataset using the one-vs-all format and compared their performance to find the best performing feature map with parameters. 


#### **Results**
I have used k-fold cross validation (without it, it's possible to get 100% accuracy using certain seeds in train_test_split) to analyze the performance of different quantum kernels. The mean accuracy and std are given in the following table-

| Features | Feature Map | Library/SDK | Number of Qubits | Depth | Mean Accuracy | STD |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | 
| All | ZFeatureMap | Qiskit | 4 | 2 | 0.967 | 0.021|
| All | ZZFeatureMap | Qiskit | 4 | 11 | 0.967 | 0.021|
| Petal Length & Width | Angle Encoding | Pennylane | 2 | 2 | 0.96 | 0.025|
| Petal Length & Width | ZZFeatureMap | Qiskit | 2 | 5 | 0.96 | 0.025|
| All | Angle Encoding | Pennylane | 4 | 2 | 0.96 | 0.025|
| Petal Length & Width | Classic | scikit-learn | NA | NA | 0.96 | 0.044|
| All | Classic | scikit-learn | NA | NA | 0.96 | 0.061|
| Reduced by PCA(2) | Classic | scikit-learn | NA | NA | 0.953 | 0.043|
| Reduced by PCA(2) | Angle Encoding | Pennylane | 2 | 2 | 0.927 | 0.033|
| Reduced by PCA(2) | ZZFeatureMap | Qiskit | 2 | 5 | 0.92 | 0.034|
| Sepal Length & Width | Angle Encoding | Pennylane | 2 | 2 | 0.807 | 0.074|
| Sepal Length & Width | ZZFeatureMap | Qiskit | 2 | 5 | 0.8 | 0.047|
| Sepal Length & Width | Classic | scikit-learn | NA | NA | 0.78 | 0.085|
| All | Amplitude Encoding | Pennylane | 4 | 5 | 0.773 | 0.102|
| Sepal Length & Width | Amplitude Encoding | Pennylane | 2 | 2 | 0.7 | 0.047|
| Petal Length & Width | Amplitude Encoding | Pennylane | 2 | 2 | 0.64 | 0.053|
| Reduced by PCA(2) | Amplitude Encoding | Pennylane | 2 | 3 | 0.58 | 0.098|


#### **Highest performance**

The QSMV model which uses all 4 features with ZFeatureMap encoding yeiled the highest accuracy of 0.967 with std of 0.021. This kernel has 4 qubits and a depth of 2. The kernel is shown below- 
<img width="626" alt="image" src="https://user-images.githubusercontent.com/40586752/221820893-033cd664-2be5-4061-a939-4beb9d3de834.png">

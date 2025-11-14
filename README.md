This project aims to classify electrical grid stability using machine learning techniques applied to the Electrical Grid Stability Simulated Data (10,000 samples, 14 attributes (https://archive.ics.uci.edu/dataset/471/electrical+grid+stability+simulated+data). The goal is to compare model performances, tune key hyperparameters, and understand their impact on predictive accuracy. The analysis focuses on Support Vector Machines (SVM) with multiple kernels and a Decision Tree classifier.
Steps & Process Overview
1.	Data Loading & Inspection
   
    o	Loaded the dataset and checked dimensions, data types, and missing values.
    o	Confirmed a clean dataset with no null entries.
3.	Preprocessing
   
    o	Encoded the target variable stabf (stable/unstable).
    o	Standardized all numerical features using StandardScaler.
    o	Split the dataset into 80% training and 20% testing with stratification.
5.	Model Development (SVM)
   
    o	Trained SVM models using linear, polynomial (degree=3), and RBF kernels.
    o	Evaluated performance using accuracy, precision, recall, F1-score, and ROC–AUC.
7.	Hyperparameter Tuning (SVM - C Value)
   
    o	Tested C = [0.1, 1, 10, 100] on all kernels.
    o	Identified optimal C for each kernel based on F1-score.
9.	Decision Tree Tuning
    
    o	Trained Decision Trees with max_depth from 1 to 20.
    o	Selected the best depth based on training F1-score.
    o	Evaluated final model on the test set.

Methodology-	
    • Supervised Learning Framework: Classification problem using SVM and Decision Tree algorithms.
    • Evaluation Metrics:
            Accuracy, precision, recall, F1-score, and ROC–AUC were chosen to assess both balance and discriminative ability between stable vs. unstable states.
    • Hyperparameter Tuning Strategy:
    
          o	For SVM: varied C values to control regularization strength and used fixed gamma (‘scale’).
          o	For Decision Trees: tuned tree depth to find the optimal balance between underfitting and overfitting.
          o	All experiments used the same train–test split for fairness and comparability.

Conclusion

The RBF SVM delivered the highest overall performance, achieving strong accuracy and excellent ROC–AUC, indicating clear separability between classes. Tuning the C parameter significantly improved results for polynomial and RBF kernels, showing that model performance is highly sensitive to regularization. The Decision Tree achieved good results at max_depth=15 but was outperformed by the tuned SVM models. 


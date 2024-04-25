# Parameter_Optimization_using_SVM

Dataset link: https://archive.ics.uci.edu/dataset/891/cdc+diabetes+health+indicators

## Methodology

### 1. Data Preprocessing: 
The dataset is loaded from a CSV file. 
Missing values are handled. 
Graph is made for analysis.

### 2. Feature Scaling: 
Standardization is applied to the feature variables using StandardScaler to bring them onto the same scale.

### 3. Model Training and Evaluation: 
The dataset is split into training and testing sets using a 70-30 split and this process is repeated 10 times with different random states to generate multiple samples for cross-validation.For each sample, SVM models with different kernels ( 'sigmoid', 'poly', 'rbf', 'linear') are trained with randomly chosen hyperparameters (kernel, epsilon and nu) using a custom fitness function based on accuracy score.The best performing model (with the highest accuracy) for each sample is recorded along with its hyperparameters. 
A DataFrame (result_df) is created to store the results (sample number, best accuracy, best kernel, best epsi value, best nu value).
Finally, the model with the best accuracy across all samples is selected and its learning curve is plotted to visualize the convergence of accuracy with respect to the number of training iterations.

### 4. Observation:

|index|Sample|Best Accuracy|Best nu|Best Epsilon|Best Kernel|
|---|---|---|---|---|---|
|0|S1|0\.9489304964984431|0\.18124449789678865|0\.38259483316308407|sigmoid|
|1|S2|0\.9481718098884354|0\.10275632148812777|0\.3665828139522429|poly|
|2|S3|0\.9474996932198871|0\.16964886027189247|0\.45872799672228903|rbf|
|3|S4|0\.9450761929277612|0\.22902760605090672|0\.6924822358355808|linear|
|4|S5|0\.949692495846034|0\.06454064424732683|0\.16220477220123086|linear|
|5|S6|0\.949447971274733|0\.0923339898329325|0\.6798478889931833|rbf|
|6|S7|0\.9407219372966757|0\.07466022355623061|0\.633138223544199|poly|
|7|S8|0\.9498034034804179|0\.18308465840332988|0\.22013299521662488|linear|
|8|S9|0\.9499999874880998|0\.09193697736259261|0\.198043929151955|linear|
|9|S10|0\.9492446978359635|0\.1324327539307883|0\.6082372206790093|linear|

### Convergence of Best SVM Model:

![image](https://github.com/jaisika22/Parameter_Optimization_using_SVM/assets/107528387/8347f500-3f10-4434-8649-38700cc4a827)

### Iteration vs Accuracy:

![image](https://github.com/jaisika22/Parameter_Optimization_using_SVM/assets/107528387/3f1831b6-778b-4ad0-ac57-5e603c49c418)


Note: The results may vary as the code works on random choices

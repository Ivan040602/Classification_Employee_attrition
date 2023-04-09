# Classification  «HR employee attrition» 

### Explanatory data analysis: <br />

The following dataset contains information about the company's employees:  
-	<b>Age</b> 
-	<b>Frequency of business trips</b>
-	<b>Employee rating </b>
-	<b>Education level </b>
-	<b>Position </b>
-	<b>Working hours</b> 
-	<b>Work / life balance rate </b>
-	<b>Salary </b>
-	<b>Distance from home from work </b>
- <b>etc. </b>

Based on these data, we need to build a model to determine the presence of <b>"Exhaustion"</b> in an employee. 
First you need to conduct an explanatory data analysis to review what is contained in the following data. 
We see that the selected dataset consists of 35 columns with various characteristics and 1470 rows with various employees of the company. 

First of all, we separate categorical variables from quantitative ones in order to apply Label encoding to categorical variables later on at the preprocessing stage. 
This method will allow us to convert text variables into numbers in order to further apply various methods of model training to our data. 

<br/>
<img src="https://imgur.com/O7avRz9.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />

In order to determine the level of correlation between variables, we need to build an appropriate correlation matrix of parameters. 
This correlation matrix shows that the most dependent variables are <b>JobLevel</b> and <b>TotalWorkingYears</b>, as well as the variables <b>TotalWorkingYears</b> and <b>MonthlyIncome</b>. 
It is clear that the graph also reflects absolutely logical parameter dependencies, for example, the dependence of the <b>Age</b> parameter and <b>TotalWorkingYears</b>. 

### Preprocessing: 

At the preprocessing stage, we use the above-mentioned LabelEncoding, which allows us to take into account categorical variables when further applying learning models. 
We also delete the Standard Hours and EmployeeCount columns, which showed themselves to be insignificant on the correlation matrix. 
The last preparatory action before applying the training models, we divide the sample into test and training, having previously applied <b>SMOTE()</b> <b>(Synthetic Minority Over-sampling)</b>. 
This method is intended for use in the Balanced classification. 
This is exactly our case, because we see that the number of people who do not have Attrition is much greater than the number of people who have Attrition. <br />

### Implementation of the models: 

After conducting Explanatory data analysis and Preprocessing, we apply the Logistic Regression, Random Forest Classifier and XGB Classifier models to our data in order to determine the best indicator of the applied models. 
It will be most convenient to display the results of using models in the form of Confusion matrices, with the help of which the hit of the model on the test sample is clearly visible compared to the training sample. 

<br/>
<img src="https://imgur.com/rrwd2H5.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
### Result: 

Based on the results of using models, we see that the <b>XGB Classifier model</b> with the accuracy of 0.93 on the test sample has the highest accuracy. 
In this case, <b>Accuracy_score</b> means the built-in sklearn function for determining accuracy when applying the model for classification.

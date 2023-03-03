# Contingency Tables, Chi-Squared Test and Hypothesis-Testing



# The concept of contingency tables:
In statistics, a contingency table (also known as a cross tabulation or crosstab) is a type of table in a matrix format that displays the (multivariate) frequency distribution of the variables. They are heavily used in survey research, business intelligence, engineering, and scientific research.

## We have a dataset surveys carried out by an University which distributes a survey of 14 questions and receives responses from 62 undergraduates.
The data looks as below:

![image](https://user-images.githubusercontent.com/33120664/222844198-61cd4be8-f697-421e-93c6-882d92990ca7.png)

### The contingency table for gender and Major looks as below:

![image](https://user-images.githubusercontent.com/33120664/222844489-937e01e3-9681-41c2-97db-03792d0364d3.png)

This can be generated using crosstab from pandas library.

Different sets of probabilities can be found using the contingency tables. It is just to visualize the numbers in a tabular format giving us easier ways to calculate probabilities.

The contingency tables can be formed using different variables. For example:
Gender and Grad Intention:
![image](https://user-images.githubusercontent.com/33120664/222844947-af5e2f80-7e34-4a34-afac-4519926a008a.png)
Gender and Employment:
![image](https://user-images.githubusercontent.com/33120664/222845028-5bbe2a7c-b952-47d9-92aa-7e11a570a069.png)
and so on.

Few of the probabilities we see from the data we are using are:
The probability of a randomly selceted student being Male is 46.77%
The probability of a randomly selceted student being Female is 53.22%

The below table gives the conditional probability(%) of different majors among the male students in CMSU:
![image](https://user-images.githubusercontent.com/33120664/222845347-9ff7ea27-afd0-4d93-a24d-7d17fe15b897.png)

The below table gives the conditional probability(%) of intent to graduate, given that the student is a female:
![image](https://user-images.githubusercontent.com/33120664/222845477-eb08cc2b-83ab-4d14-834a-bc9465d24868.png)

Based on the different probabilities we calculated, we can check if the column variable in each case is independent of Gender for example.
We can apply the chi squared test of independance on the contingency tables we have.

For our data, below is an example of Hypothesis tests we can perform. Check the jupyter notebook from the files of this repository for p value calculations and coding specifics in python. However, an output from the excercise is as follows:
### Hypothesis:
#### Null: Column variable is independent of Gender
#### Alternate: Column variable is dependent on Gender
From the chi-squared tests, we have the following P values:
For,
Gender and Major : P value = 42%
Gender and Grad Intention : P value = 9.18%
Gender and Employement : P value = 23.04%
Gender and Computer pref : P value = 34.74%
#### 1. At Alpha = 5%
All the P values are higher than alpha.
Hence,The column variables have no dependancy on the gender. That is, the variables are independent of the Gender.
#### 2. At Alpha = 1%
All the P values are higher than alpha.
Hence,The column variables have no dependancy on the gender. That is, the variables are independent of the Gender.
#### 3. At Alpha = 10%
From the P values, we can say the variable Grad Intention is dependant on the Gender
The rest of the column variables have no dependancy on the gender.

There are three numerical (continuous) variables in the data set, Salary, Spending and Text Messages. For each of them we can check whether they follow a normal distribution using normality tests. Please check the jupyter notebook for detailed steps. The results are as below:

[symmetric histogram does not necessarily mean that the underlying distribution is symmetric]

#### Assuming Alpha = 5%
#### Null hypothesis : Variables follow normal distribution
#### Alternate hypothesis : Variable do not follow normal distribution
Using the normaltest function from scipy.stats, we can get the P value
From the P values, we can say that:
A.For the variable Salary, we fail to reject the null hypothesis as the P value (14.6%) is greater than alpha(5%). Hence, the variable Salary follows a normal distribution.

B.For the variable Spending, we reject the null hypothesis as there is enough evidence to say that the variable Spending doesn't follow normal distribution. The P value (0.0000238%) is less than alpha(5%). Hence, the variable Spending doesn not follow a normal distribution.

C.For the variable Text Messages, we reject the null hypothesis as there is enough evidence to say that the variable Spending doesn't follow normal distribution. The P value (0.028%) is less than alpha(5%). Hence, the variable Spending doesn not follow a normal distribution.



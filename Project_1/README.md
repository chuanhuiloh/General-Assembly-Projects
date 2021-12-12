# Project 1: What Factors Influence SAT And ACT Participation Rate?

In this project, I analyzed the SAT and ACT performance and participation rate in 2017 and 2018 of all states in the United States. Due to the federal system of the United States, each state is free to make its own requirement with regards to the college admission tests. This creates a myriad of factors which may influence the participation rate of SAT and ACT in each state. For example, certain state governments in the United States administer either the SAT or the ACT exclusively and also cover the fees for taking the test. These programs increase access to low-income students and consequently the participation rate of both standardized tests. However, there remains pocket of demands in these states to take the non-mandatory tests to expand the student's options for colleges.

For this analysis, I attempted to answer the following questions:

1. Establish if there is any relationship between the test performance and test participation rate for both SAT and ACT.

2. Identify the SAT-mandatory states that has high demand for the ACT test

3. Identify states with low ACT participation rate from states without test requirement

These information would be useful for ACT to draw useful lessons from states with the high participation and to apply them and devote more resources in states with low participation rate.

---

## Executive Summary
For this project, I used the data from the following sources: SAT 2017, SAT 2018, ACT 2017 and ACT 2018. The source file can be found in the /data folder. I have also included information on the test requirement of each state in the United States as of May 2017 ([*source*](https://magoosh.com/hs/sat/states-that-require-the-act-or-sat/)). All the afore-mentioned datasets were combined as a single dataset as /data/act_sat_1718.csv. Various data visualization techniques were then used to identify trends and correlations between features to help to surface insights which help to answer the questions.

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|ACT and SAT, 2017 and 2018|The name of the State in the United States| 
|act_18_participation|float|ACT 2018|The participation rate of ACT in the state in 2018 (units in floats to two decimal places 0.33 means 33%)| 
|act_18_composite|float|ACT 2018|The average ACT Composite score of the state in 2018. The composite score is derived from the average of the scores for English, Math, Reading and Science. The score ranges from 1 to 36 | 
|act_17_participation|float|ACT 2017|The participation rate of ACT in the state in 2017 (units in floats to two decimal places 0.33 means 33%)|
|act_17_composite|float|ACT 2017|The average ACT Composite score of the state in 2017. The composite score is derived from the average of the scores for English, Math, Reading and Science. The score ranges from 1 to 36 |
|sat_18_participation|float|SAT 2018|The participation rate of SAT in the state in 2018 (units in floats to two decimal places 0.33 means 33%)| 
|sat_18_erw|int|SAT 2018|The average SAT Evidence-Based Reading and Writing score of the state in 2018. The score ranges from 200 to 800 | 
|sat_18_math|int|SAT 2018|The average SAT Math score of the state in 2018. The score ranges from 200 to 800 |  
|sat_18_total|int|SAT 2018|The average SAT Total score of the state in 2018. The total score is the sum of the scores for Evidence-Based Reading and Writing and Math. The score ranges from 400 to 1600 | 
|sat_17_participation|float|SAT 2017|The participation rate of SAT in the state in 2017 (units in floats to two decimal places 0.33 means 33%)| 
|sat_17_erw|int|SAT 2017|The average SAT Evidence-Based Reading and Writing score of the state in 2017. The score ranges from 200 to 800 | 
|sat_17_math|int|SAT 2017|The average SAT Math score of the state in 2017. The score ranges from 200 to 800 |  
|sat_17_total|int|SAT 2017|The average SAT Total score of the state in 2017. The total score is the sum of the scores for Evidence-Based Reading and Writing and Math. The score ranges from 400 to 1600 |
|state_choice|object|External Source|The test chosen by the state as mandatory. 'ACT' means the state has chosen ACT as madatory. 'SAT' means the state has chosen SAT as mandatory. 'Both' means both ACT and SAT are mandatory in the state. 'None' means neither ACT nor SAT are compulsory in the state |


### Key Conclusions and Recommendations

#### Conclusion

The following were the key observations made from the given data:

1. The choice of mandatory test in the state leads to high participation rate of the test. This is not surprising given that the cost of a test that is made mandatory is also most likely to be covered by the state government, which therefore access to low-income students.

2. The states that has the least participation rate in ACT tends to be from the Northeast Region of the United States, whereas states from the Midwest and the South tend to have the least participation rate in SAT. Again, this may be related to the state's choice of mandatory test.

3. New Jersey, DC, Connecticut and New York performed best for ACT. Tennessee, Kansas and Kentucky leads in performance for SAT.

4. Colorado and Illinois SAT participation rate experienced a sharp increase from about 10% in 2017 to almost 100% in 2018. Given that Colorado and Illinois only switched to mandatory SAT in the 2016-2017 school year, this sudden increase in participation reflects the year of transition.

5. Performance is negatively correlated with Participation in general for both ACT and SAT in both 2017 and 2018. Some plausible reasons are as follows:

- States with high participation rate would include students of a range of ability, thereby lowering the average performance.

- Only a small number of more academically students are taking the non-compulsory test in their state. This has the possible effect of having states with low participation having higher performance.
   
6. Distribution of both SAT and ACT participation rates are consistent between 2017 and 2018.

### Recommendations

The following are suggested follow-up actions for ACT:

1. Despite some states making certain SAT mandatory, it is obvious that there is strong demand for the ACT in certain states. This may stem from the fact that some students, especially the ones who are more academically inclined wishes to enroll in both tests to expand their range of college options.   The ACT should analyse further the reasons for such high participation rate for their test and seek to duplicate the conditions in states where the participation rate is lower.


2. The ACT should devote more resources to increase the current ACT participation rate (< 20%) of the following states where neither tests are required:
- Pennsylvania
- Rhode Island

3. The ACT should also assign resources to states to increase ACT participation where academically inclined students are more likely to take more than one tests such as Illinois, DC and New Jersey.

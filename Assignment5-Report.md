**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#:      | 04          |
| -------------- | ----------- |
| Student Names: | Azlan Amjad |
|                | Saud Agha   |
|                | Rohan Amjad |
|                | Sajid Hafiz |

# Introduction
This lab introduces tools such as C-SFRAT and SRTAT to assess the reliability of the given system. The two ways
used to assess the failure data in this lab were
1. Reliability growth testing 
2. Reliability Demonstration Chart
#

# Assessment Using Reliability Growth Testing

## Result of Model Comparison
![Ranking of various models](https://github.com/seng438-winter-2022/seng438-a5-AzlanAmjad/blob/main/Ranking.PNG?raw=true)

Fig. 1. Ranking of top two models

Sorting by the greatest Log-Likelihood reveals that the two best models are DW3(F) and IFRGSB(E,F). This can be seen in Fig. 1. The failure intensity graph is given in Fig.2 for each model and the MVF graph for each model is given in Fig. 3.

![Failure intensity of DW3 and IFRGSB(E,F)](https://github.com/seng438-winter-2022/seng438-a5-AzlanAmjad/blob/main/top2graphintensity.PNG?raw=true)

Fig. 2. Failure intensity graph of the top two best models

![MVF of DW3 and IFRGSB(E,F)](https://github.com/seng438-winter-2022/seng438-a5-AzlanAmjad/blob/main/top2graphmvf.PNG?raw=true)

Fig. 3. MVF graph of the top two best models

## Result of Range Analysis

Using the laplace trend test for model DW3(F) it was found u(31) = -0.8 which is between 2 and -2 which means the range
of acceptable data is from intervals [0,31]. Fig. 4. shows the laplace trend test applied to the DW3(F) model

![Laplace Test of Model DW3(F)](https://github.com/seng438-winter-2022/seng438-a5-AzlanAmjad/blob/main/laplace.PNG?raw=true)

Fig. 4. Laplace Trend Test Applied to Model DW3(F)

Additionally, Fig. 4 reveals that there is reliability growth as the u(k) values are below zero on the interval [3,31].

Using the laplace trend test for model IFRGSB(E,F) it was found u(31) = -0.54 which is between 2 and -2 which means the range
of acceptable data is from intervals [0,31]. Fig. 5. shows the laplace trend test applied to the IFRGSB(E,F) model

![Laplace Test of Model IFRGSB(E,F)](https://github.com/seng438-winter-2022/seng438-a5-AzlanAmjad/blob/main/laplace2.PNG?raw=true)

Fig. 5. Laplace Trend Test Applied to Model IFRGSB(E,F)

Additionally, Fig. 5 reveals that there is reliability growth as the u(k) values are below zero on the interval [27,31].

## Plots For Failure Rate and Reliability
The plot for the failure intensity rate for Model DW3(F) can be seen in Fig. 2. and the reliability graph for the  Model DW3(F) can be seen in Fig. 6. 

![Reliability of model DW3(F)](https://github.com/seng438-winter-2022/seng438-a5-AzlanAmjad/blob/main/rel1.PNG?raw=true)

Fig. 6. Reliability Graph for Model DW3(F)

The plot for the failure intensity rate for model IFRGSB(E,F) can be seen in Fig. 2. and the reliability graph for the Model IFRGSB(E,F) can be seen in Fig. 7. 

![Reliability of model DW3(F)](https://github.com/seng438-winter-2022/seng438-a5-AzlanAmjad/blob/main/rel2.PNG?raw=true)

Fig. 7. Reliability Graph for Model IFRGSB(E,F)



## Discussion on Decision Making Given a Target Failure Rate

The implications of setting a target failure rate are that you may need to test more if the failure rate is low which would increase costs and delay the time it would take to launch the product; however, if it's higher then there is a larger threshhold in either testing the product more to determine if it's of acceptable quality or outright accepting the product. Given this information, we believe that the ideal target failure rate for this system is 0.6. For the model IFRGSB(E,F) it reaches this target on the 32nd interval and for the model DW3(F) it reaches this target on the 37th interval. This can be seen in Fig. 8. below. This would make it so not much more additional testing is necessary and it would also ensure a level of reliability of the system. 

![Reliability of model DW3(F)](https://github.com/seng438-winter-2022/seng438-a5-AzlanAmjad/blob/main/fit.PNG?raw=true)

Fig. 8. Failure Intensity Graph of the two models 

## Advantage and Disadvantages
Advantages:
1. It gives confidence regarding the reliability of the system.
2. The tool can predict how many more intervals it may take to reach a failure intensity target, thereby having a more accurate idea of the costs to undertake the testing of the system
3. Predict the reliability of the system by increasing the number of intervals to predict


Disadvantages:
1. Difficult and time consuming
2. Requires a large amount of past failure data to make better predictions
3. Requires specialized tools which have an extra cost in form of a licensing fee


# Assessment Using Reliability Demonstration Chart

## 3 Plots For MTTFmin

Minumum MTTF:

![minMTTF](media/minMTTF.png)

Twice MTTFmin: 

![twiceMTTF](media/twiceMTTF.png)

Half MTTFmin: 

![halfMTTF](media/halfMTTF.png)



## Evaluation and Justification of MTTFmin

To calculate minimum Mean Time Between Failures (MTTF), we used a "brute-force" approach, by playing around with the Failure Intensity Objective (FIO) inputs
on the SRTAT Reliability Demo Chart tool. This method might not have been the best, but due to the vagueness of data provided, and to avoid mis-identifying the data set, we decided to use observations as the guiding force. We evaluted that due to simplistic nature of Reliability Demo Chart, it is easy to get a "glance" of the reliabilty surrounding a system, but it lacks a more quantitative aspect which might help determine exact cause-effects around reliability. 

## Advantages and Disadvantages

An advantage we found when using the SRTAT Reliability Demo Chart Tool was the ease of setting everything up and modelling the data. However, a disadvantage was finding "exact values" or any information which might help us quanitfy the model in real-world terms. 

#

# Comparison of Results

The calculated target failure rate from Part One (0.60) would not fit in the "accept" range on the Reliability Demonstartion Chart from Part Two. One way to allow the calculations from Part One to "fit" in our RDC, we can increase the customer risk. However, we are increasing the risk of assessing entities which are wrong to be right, and in the real world this can have dire consequences. Another method is to increase the discrimination ratio, this is the risk related to measured entity itself.

# Discussion on Similarity and Differences of the Two Techniques

Both tools allow to see software quality in a more qualitiative light. However, one major difference is that one tool (C-SFRAT) is focused heavily on reliability growth assessment, while SRTAT has potential to do both reliability growth assessment and Reliability Demonstration Chart; however, RDC can't calculate the reliability of the system. One thing to note, is while SRTAT can do both of the parts in the lab, we decided to use a mixture of C-SFRAT and SRTAT to gain wider understanding of the different toolsets.


# How the team work/effort was divided and managed
Part 1 was split to two group members and part 2 was split to the remaining two group members. Each pair worked on their separate part and once completed, each pair would explain how they came to their conclusion and explain their results. If we found the explanation sufficient we accepted the results and if we found it insufficient, we together as a group would go through the pair's methodology again and derive new results. 

#

# Difficulties encountered, challenges overcome, and lessons learned
The difficulties that we encountered include running the SRTAT tool as it was not working very well. The challenges that we overcame were trying to calculate the laplace trend test for the models in the C-SFRAT tool since that tool did not provide trend tests. The lessons that we learned were how reliability growth assessments tool can be used to determine the reliability growth of a system and also assume a target failure rate. We also learned how to determine if the MTTF is met and whether to reject, accept, or continue the testing/product using the RDC. Another lesson we learned from modelling the Reliability Demonstration Chart was on how to manipulate given data-sets to make them work with a tool. The initial data-set provided was a in .CSV file format. To use this data with the provided SRTAT tool, we had to change the file format and data format to be usable. All in all, we feel we are better equipped for the future if we face a file format that does not work the a modelling tool provided
# Comments/feedback on the lab itself

SRTAT is outdated. In the future, I would like to see tools that aren't outdated or more precise instructions to run this tool. 



STOR 665 Project
================

Authors
-------

Andrew Ackerman <br/>

USAGE
-----
#### R.Studio, Latex

Rmd output should be reproducible from the raw code and accompanying data.  Note, the .tex files include various images not included in this github page.  In order to run the .tex file independently, it is necessary to first reproduce these illustrations via the Rmd and ammend the latex files accordingly.  Outside of this small inconvenience, the methods and procedures (including random processes) should be entirely reproducible (with seeds clearly defined within the code).  


    
     

Introduction
------------
The turn of the decade has been distinguished by the single most infectious and insidious global pandemic in over a century.  Not since the 1918 “Bird-Flu” has a virus so completely decimated populations and with it, morale.  Yet, for all of its well-warranted notoriety, Corona-19 was only the third leading cause of death in the United States in 2020.  Responsible for over 598,000 deaths last year alone, cancer nearly doubled the already staggering death toll of Corona-Virus.  Among this cacophony of grief, breast cancer affects the lives of more women than any other form of cancer, save for melanoma.  It is estimated that over 330,000 women will be diagnosed with breast cancer this year alone.  Roughly 43,600 of these women will tragically succumb to the insidious disease. Of these 43,600 deaths, a staggering majority will be women in late stage progression.  By this I mean the tumor has metastasized and now exists beyond just breast tissue.  To put this intuition into perspective the five-year survival rate of a stage 0-1 breast cancer patient is 99 percent.  This stands in stark contrast to the 28 percent survival rate of a patient in stage 4.  Thus, it should be apparent that detecting cancerous cells early is tantamount to numerous years of added life expectancy.  Such is my ambition with this project.  


Data
----
As it pertains to the data itself, I will be using a set garnered from the machine-learning repository.  Originally developed at the University of Wisconsin, it has 569 observations and 32 unique features.  Said features include the patient ID, Diagnosis category (malignant or benign), and ten real-valued cell-nucleus descriptors.  These are as follows: radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, symmetry, and fractal dimension.  Subsequently, each of these ten covariates has three corresponding metrics associates with it — mean, standard error, and largest mean — to produce a total of 32 features.  A subset of the data is provided below.  


Methodology
-----------

Breast cancer has historically been detected in one of three ways — mammography, fine needle aspirate (FNA), and surgical biopsy.  While biopsy boasts a nearly perfect sensitivity, it is an invasive and resource intensive.  Therefore, the incentive to improve the accuracy of more innocuous procedures like FNA is profound.  The medical and machine learning literature is dense with citations of a linear-programming approach to classification.  While such algorithms have been touted to perform with marked accuracy (upwards of 97.5 percent predictive accuracy on 10-fold cross validation), I believe the efficiency could be improved upon.  More pointedly, the data-set used to train such algorithms contains 32 real-valued features.  The established approach for such high dimensional data classification is to build classifiers using all subsets of 1-4 features and 1-2 separating planes.  However, considering each of these subsets is computationally expensive (as it requires parsing through over 41,000 combinations) and limited in complexity (while we do want a lower dimensional model, restricting attention to 4 features may in fact be too restrictive).  To rectify such efficiency concerns, the novelty of my approach will be to enact a penalization approach to a logistic regression form of classifier.  More specifically by examining Ridge, Lasso, and Elastic Net procedures, I intend to heighten efficiency while retaining sensitivity by placing more accurate emphasis on covariates of truly significant influence.  

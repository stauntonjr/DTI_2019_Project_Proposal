# The Data Incubator 2019 Fellowship Application: Project Proposal
This repository contains my project proposal for Section 3 of The Data Incubator 2019 Fellowship Application Challenge. The proposed project seeks (i) to characterize the statistical relationships between race, health care coverage, and cancer diagnosis in American individuals; and (ii) to identify personal factors that are predictive of health insurance coverage status and type.

A cursory exploration of data[1] on cancer incidence and county population statistics  takes the form of a Jupyter notebook written with Python 3 using numpy, pandas, scipy, matplotlib and seaborn. The notebook reveals some interesting trends. Firstly, Figure 1 shows that among U.S counties, the relative size of the black population is positively correlated to public healthcare coverage and negatively correlated to private healthcare coverage. Secondly, Figure 2 shows that there is a distinct subset of counties with a higher percentage of cancer diagnoses, which have a considerably lower fraction of citizens that are insured only by public healthcare and a slightly higher than average fraction of citizens that are insured only by private healthcare. This suggests that among the counties in which better preventative care is giving rise to a higher number of (hopefully early and thus manageable) diagnoses of cancer, more people are insured with private than public health insurance. 

I next investigated how public and private health insurance coverage rates of Black vs. Non-Black Americans have changed over the past several years in response to the implementation of the Affordable Care Act. Using DataFerrett (a Java-based tool developed by the U.S. Census Bureau) I accessed a 13.9 GB dataset from the U.S. Census Bureau's American Community Survey (ACS), namely the ACS Public Use Microdata Sample (PUMS) in the range of years 2013-2017. I successfully deployed a Dash app to Heroku using Git, gunicorn plot.ly, and numpy which plots the ACS PUMS data. The app is hosted at https://census-dashboard.herokuapp.com/. Consistent with the first dataset, the census data revealed in the app shows that, compared to (self-identified) Non-Black populations, Black populations have a greater percentage of public coverage, a lesser percentage of private coverage, and a lesser percentage of total coverage throughout the timespan. However, (and encouragingly), this disparity is seen to decrease slightly over the time span investigated. In addition, the ACS PUMS data show that public, private and total coverage slightly increased form 2013 through 2016, but then slightly decreased in 2017. Because health care coverage is (according to the data in the Jupyter notebook) associated with more proactive diagnosis of cancer, this reversal of the trend of increasing health care coverage is concerning, and justifies further investigation into the factors predictive of health insurance coverage. 

The code for my web app is in the app.py file. I am currently working on connecting the app directly to the census data via their API with the 'requests' library to get queries with my API key. The next step is to produce a user-facing interface to build custom queries from the variables of interest, and to choose how they should be plotted together. My intermediate goal is to transform my Dash web app into an improved replacement for the DataFerrett tool (which I found to be slow and unintuitive). Thereafter, I will use the app to further explore the data and identify trends of interest. This will enable me to identify real factors that are predictive of health insurance coverage. Depending on my findings, I will consider engineering features and building a machine learning model to predict health insurance status from the other columns in the census data. Such a model would be of utility in hazard identification and risk assessment.   

[1] This dataset was aggregated and kindly provided by data.world user nrippner from census.gov, clinicaltrials.gov, and cancer.gov were as described at https://data.world/nrippner/cancer-trials and was accessed from https://query.data.world/s/3b96GyLkqZ1IgCONmj193k1yF59fNz.

# StuberUdacityProject1 &#128049;

### <b>Project Note:</b>
 - I operated my Jupyter Notebook editing in a potentially unusual way
 - So please keep in mind that I will save them into Github, but that is not where I stored them under daily coursework/operation
 - My steps for reference:
     - Prompt Interface > Jupyter Notebook > Navigated to my desktop folder within > Opened my ipynb file

### <b>Libraries Used:</b>
 - import pandas as pd
 - import numpy as np
 - import matplotlib.pyplot as plt
 - from decimal import Decimal
 - from sklearn.linear_model import LinearRegression
 - from sklearn.model_selection import train_test_split
 - from sklearn.metrics import r2_score, mean_squared_error, root_mean_squared_error, accuracy_score, precision_score, recall_score

### <b>Project Motivation:</b>
 - I searched all the datasets, some were blocked
 - My intent was to find any analysis on cats, as I thought that would be funny, and I like and have 2 cats
 - Alas, no cats were found, so I searched the World Bank Dataset for environmental datasets, as those are interesting to me as well
 - The landmine dataset immediately stood out as very different and interesting, as it is not a concept one thinks of every day
 - Looking at the series, I picked ones that would be easy for me to conceptually think on and hypothesize

### <b>Files within this public repository:</b>
 - <b>Jupyter Notebook File:</b> StuberUdacityProject1.ipynb
     - This file has many of my notes in Markdown, Comment Blocks which are visually more appealing to me ''' ''', and regular inline comments via #
     - I dicuss CRISP DM, the data, and all my cleaning, analysis, and thoughts throughout this project
 - <b>Project Data:</b> Project1Data.csv
     - This contains the raw export after I applied all filters and selections within the WorldBank database
     - These explicit filters and selections are at the top of my Jupyter Notebook file for reference
 - <b>Project Data Metadata:</b> MetaData.csv
     - This is a very similar dataset as Project1Data, however its footer cells have definitions to the series Chosen for reference as well

### <b>Summary/Results:</b>
 - <b>Cleaning:</b>
     - I had to use many pandas functions I had not used before for work, such as melt to unpivot columns back into their vertical datasets
     - Footer rows were generated with the export, so removed those
     - I removed NaN rows, and I also siwtched dtypes to Integer and Float so I could perform analyses
 - <b>Model Choices:</b>
     - Many of the series/Features within WorldBank database I could have chosen were more broken down forms of the aggregated ones I chose
     - Scanning through them all it was not ideal to me to bring in the split out versions of Casulaties for example
     - Which had Male, Female, Boy Child, Girl Child, and so on
     - So with that decided, I brought in 3 distinct measures that I could have used, in which I used 2 individually to compare to Casualties
     - Anti-Vehicle and Non-Anti Vehicle Mines Destroyed
     - I wanted to assess each of these individully against my target variable, in Single Linear Regression
     - My hypothesis was in Countries and Years with more destruction of these mines, that Casulaties could be predicted to follow
 - <b>Model Results:</b>
    - #1: All r^2 produced were negative, even when removing what I tried considering as outliers, so all models produced no better than general guesses
    - #2: R^2 got closer to the range of 0-1 when I removed outliers, but then RMSE as a 2nd metric skyrocketed to unsafe mine variances
    - <b>Question #1:</b>
      - Could a Country's representatives consider civilian/government casualties to increase the more Anti-Vehicle mines are cleared/destroyed?
    - <b>Answer #1:</b>
      - It is inconclusive that "Anti-Vehicle Mines Destroyed" is impactful/predictive of Total Casualties
    - <b>Question #2:</b>
      - Could a Country's representatives consider civilian/government casualties to increase the more Non-Anti Vehicle mines are cleared/destroyed?
    - <b>Answer #2:</b>
      - It is inconclusive that "Non-Anti Vehicle Mines Destroyed" is impactful/predictive of Total Casualties
    - <b>Question #3:</b>
      - This data halted capture in 2012, could a Country's representatives consider large/stockpile of either mine type destroyed to be abnormal scenarios, if they are considering to bring back this program, they could filter out these occurrences to better predict and decrease Total Casualties?
    - <b>Answer #3:</b>
      - Assuming due to the lack of Annual Data (ended in 2012), that the program could have captured misstated or inflated values/outliers, did not help produce better predictions for this dataset
 - <b>Conisderations:</b>
     - Assumption: If a mine is Destroyed, my assumption going in is accidental and intended destruction are included, clearly accidental destructions would cause more harm/casualties
     - Assumption: The destroyed mine dataset was not purely mines that were safely removed from their sqft area, and transported to a safe location to then destroy
     - Hindsight: Some of the distributions looked more logarithmic, so potentially a logarithmic regression would have been more appropriate

### <b>Acknowledgments:</b>
 - Google, as always was helpful with python/pandas documentation for code reminders and new bits I had not used prior for data cleaning.
 - Udacity Data Science course videos, demos, and solutions were very helpful as well!


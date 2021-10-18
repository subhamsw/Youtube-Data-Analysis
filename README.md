# Youtube-Data-Analysis
import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

comments = pd.read_csv(r"/GBcomments.csv", error_bad_lines=False)

comments.head()

from textblob import TextBlob

TextBlob("It's more accurate to call it the M+ (1000) be...").sentiment.polarity

comments.isna().sum()

comments.dropna(inplace=True)

polarity=[]

for i in comments["comment_text"]:

  polarity.append(TextBlob(i).sentiment.polarity)
  
comments["polarity"]=polarity

comments.head(20)

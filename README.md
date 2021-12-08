# Detecting Fringe Financial Advice.
## An NLP-based classification tool for advisors and private investors. 
---
##### Nicholas Van Bergen <br> General Assembly Data Science Immersive <br> Cohort 0927-Remote

# Combating _Fringe_ Financial Advice on Reddit, Executive Summary:

Using Webscraping and Natural Language Processing techniques, we have developed a tool to help investment advisors combat notions of positive investment returns on so-called _meme trades_ primarily and nearly exclusively made by users in the subreddit community `r/wallstreetbets` (WSB). 

### Problem statement:
We consider the majority of _advice_ within WSB to be of poor quality, that is more likely to lead to financial ruin than prosperity. We apply webscraping and NLP classification techniques to build a product that will alert our target audience if some web clipping came from WSB or some other source. 

### Solution:
Using Multinomial Naive Bayes classification algorithm we have developed the minimum viable product (mvp) for such a system.  

### Results:
| **Metric**| **_Null Model_**|**Multi.Naiive Bayes<br>(MNB)**| **Random Forest Classifier<br> (RFC)**| $$\Delta$$ RFC - MNB| **Extra Trees Classifier<br> (ETC)**| $$\Delta$$ ETC-mnb| 
| :--------- |:-----------: | :---------:| :---:| :-------:|:---------------:| :---------------------------:| 
 | **Accuracy**| 0.50|Training: 0.808 <br> Testing: 0.783|Training: 0.997 <br> Testing: 0.792|Training: 0.189 <br> Testing: 0.009|Training: 0.997 <br> Testing: 0.799|Training: 0.189 <br> Testing: 0.016 |
|**Type I error**| \---| 1,413 | 1,925 | 492| 2,321 | 908|
|**Type II error**| \---| 1,301 | 1,175 | -120| 847 | -454|
|**Sensitivity**| \---| 0.792 | 0.811 | 0.019| 0.864 | 0.072|
|**Precision**| \---| 0.778 | 0.727 | 0.051| 0.699 | -0.079|
|**F1**| \---| 0.785 | 0.766 | -0.019| 0.773 | -0.012|
|**ROC AUC**| \---| 0.865 | 0.84 | -0.025| 0.848 | 0.017|


### Conclusion
The prototype mvp has been promising. Additional tuning of the model and testing should be completed to improve model accuracy and reduce Type One errors from the testing and training data. 

The extensibility of this product is vast. The vision for this product is to be an end-to-end advice confidence tool that will tell investors (not just investment advisors) a actionable ranking of the advice being input into the tool. In other words, we envision a system that will take natural language inputs, scan investment message boards, review track records of the users/bots offering the advice and then determine if that propositional investment is viable. 

Our mvp product is the first step to such a useful and helpful (and potentially lucrative) tool. 

---

### Structure of project notebooks. 
Our research conducted over two notebooks in JupyterLab.
1. Ingestion<br>
In this notebook we design a way to collect, clean, and vectorize parsed text data. 
2. Modeling <br>
In this notebook we pass our cleaned data through many models. 

#### Contents
Jupyter project is broken into 3 folders. Main, Code and Presentation
Main files:
1. Code <br>
This folder is where our notebooks are saved.
2. Data <br>
In this folder we store our data as it is cleaned, saved for later use by our modeling process. 
3. Presentation <br>
This folder contains the copy of our product presentation. 

---


#### About the API

Pushshift's API is fairly straightforward. For example, if I want the posts from [`/r/boardgames`](https://www.reddit.com/r/boardgames), all I have to do is use the following url: https://api.pushshift.io/reddit/search/submission?subreddit=boardgames

To help you get started, we have a primer video on how to use the API: https://youtu.be/AcrjEWsMi_E

---

---




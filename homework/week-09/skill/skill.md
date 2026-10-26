---
name : SVM Model Fitting Skill
description : Run SVM Model Fitting and then make a table explaining choices and results and return one page report of font 11 size and it is only invoked when a user requests the use of this skill 
month: october 
---

## Step to follow to construct report 

Make sure to follow this order exactly and don't assume in any situation and do your best to pull from the dataset and given data from user and ALWAYS follow the steps properly and NEVER miss any parts of this steps 

1. First you are going to take the given dataset and review the dataset to see if it works for a SVM model fitting including thinking of things like if data is either seperable linear or non-linear, data is in numerical vectors and each response has neat structured predicators value, etc 

2. Next you should consider different kernels including linear, polynomial(2,3,4) degrees, and radical basis and the linear help with linearly seperable one and other one help with those not linear


3. In terms of parameters to be tuned like cost C, gamma, etc based on the specfic kernel and any other params which you would believe would be important and use method  cross validation to tune the parameters 

4. For evaulation method use cross validation mean error, a ROC curve, or mix of these for better results which helps provide evidence for the final model 

5. Make sure to include a good graph and summary table to showcase the justification behind the choices and descisions you made 

6. interprut the fit through the what different tuning params or settings do, the important information learnt about the boundr it picked based on data, etc and finally pick out the important numerical results based on values that help justify or showcase the model's accuracy and what it does well and summary or snapshot


## Output

Make sure to write all the results gathered from the above steps into a 1 page report of font size 11 and make it detailed but still keep it compact enough that person can get a clean summary 

Make sure to format it well so it easy to follow and understand for anyone 

## Important things to remember 

NEVER exceed 1 page 
dont look at test set when training 

# CollisionTracker

### Summary

The purpose of this project is to use machine learning algorithms to predict the locations of traffic collisions, based on the current state of traffic flow through a city.  To do so, two tables are used, corresponding to traffic counts at select intersections throughout the city of Montreal, and a comprehensive list of all traffic collisions which occurred in Montreal, both running from 2012 to 2019.  After considerable data cleaning, I was able to grid search over various combinations of machine learning models and hyperparameters, and found that a decision tree classifier of max depth 5 yields optimal test accuracy.  I then show how this classifier can be used to make probabilistic predictions about the locations of collisions.

### The Data

- Traffic counts are collected from the [Montreal Open Data Portal](https://donnees.montreal.ca/ville-de-montreal/comptage-vehicules-pietons#data), initially in three separate CSV files.  They are read into Pandas DataFrames, where each row corresponds to the number of vehicles which passed through an intersection over a 15 minute time period.
- Collisions are collected from [Canada Open Data]( https://open.canada.ca/data/en/dataset/cd722e22-376b-4b89-9bc2-7c7ab317ef6b) as a single dataset.  It is read into a Pandas DataFrame, where each row corresponds to a collision which occurred in the city of Montreal.


### Project Workflow

1. Script1_Traffic_Cleaning.ipynb
    - This script cleans and combines the original traffic datasets into a single DataFrame that can be used for modelling.
   
2. Script2_Collsions_Cleaning.ipynb
    - This script cleans the collisions dataset into a nicely formatted DataFrame, which can be combined with the cleaned version of the traffic dataset. 
    
3. Script3_Joining.ipynb
    - This script joins the cleaned versions of the traffic and collisions datasets.  The final DataFrame is what can be used for building models.
    
4. Script4_Modelling_And_Visualization.ipynb
    - This is the script where the grid search is ran over different combinations of models and hyperparameters.  It uses the cleaned and joined dataset which is the output of Script3.  
    
5. Script5_Predicting.ipynb
    - This script still requires work (both in terms of code, and commenting), but attempts to show how such models might be used in practice.

### Movies-Dataset
### Take Home Assignments #1 and #2

## Part I: 

_Scenario_ 

Given franchises discovered from task #1, suppose someone wants to predict the success of a sequel that is to be launched, and she/he will partner with you for the task. The ask here is not to develop a prediction model, rather, you need to develop data analysis notebooks for the following subtasks:

```
1. Create ground truth for training dataset, similar to the following output: movieId, franchiseId, 0 or 1
2. 0 means “not successful”, “1” means successful.
3. You need to provide a clear and reasonable definition of “success”.
4. Come up with features that can be predictive of sequel success, for each feature, demonstrate why it is predictive or not.
5. Create training dataset that consists of feature vector and ground truth. No need to do train-test split.
```

## Part II: 

_Clear and reasonable definition of "success"_

Reading research related to movie success prediction modeling, it's clear there are many ways to interpret, and various methods to approach determining a set of features, that make a sequel successful. Dr. Dursun, and Dr. Sharda, of Oklahoma State University, reference a neural network model with independent variables such as MPAA rating, cast, genre, competition, and number of screens (_[1]_)  while Matt Vitelli, of Stanford, attempts to improve upon a baseline (1 layer) type of prediction model to include revenue but, in a different way. Typically revenue prediction will utilize regression as a continuous quantity however, Mr. Vitelli shows how you can bucket revenue as a discrete quantity (_[2]_). In addition, Mr. Vitelli also discusses release date as a "powerful" feature, as "high-grossing films are typically releaseed during the winter or summer seasons" (_[2]_). 

Revenue and release date will be the two features present in the ground truth training set. Due to time constraints for this assignment, I did not include genres, or keywords but, do have that data ready in a draft notebook of which I vectorized and added in an OLS summary on revenue for future reference however, this notebook still needs to include reasoning as to why these categorical variables would be statistically significant for the ground truth. I am also close to completing actor and director features of which I would like to also include in the franchise datset for further analysis. 

In conclusion, the ground truth dataset prepared includes a success column of 0 or 1 that will refer to franchises, that were filtered by order noted below, on the following criteria:
    
```
       1. top 500 grossing franchises from movies-dataset
       2. franchises that had sequels only
       3. sequel films that had greater revenue than its prequel film
       4. sequel films that had greater popularity, rating, and vote average than its prequel film
       5. sequel films that were released within 2 years of its prequel
```

## Built With

* [Jupyter Notebooks](https://jupyter.org/)
* [Pandas](https://pandas.pydata.org/)
* [Movies-Dataset](https://www.kaggle.com/rounakbanik/the-movies-dataset) 

## Authors

* **Mariam Joan** 

### References:
    1. Sharda, R., Dursun, Delen, 2006, "Predicting box office success of motion pictures with neural networks, Expert Systems with Applications 30 243-254, Retrieved from: http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.85.679&rep=rep1&type=pdf
    2. Vitelli, Matt, 2015, "Predicting Box Office Revenue for Movies", Stanford University, CS224w, Retrieved from: http://snap.stanford.edu/class/cs224w-2015/projects_2015/Predicting_Box_Office_Revenue_for_Movies.pdf

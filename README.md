# Na-ve-Bayes-Mushroom

## 1.Data Input
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午3.59.47.png)
## 2.Data Visualization
For mushroom dataset:
I show data distribution by value frequency of every feature.  
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午4.00.07.png)
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午4.01.09.png)
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午4.01.23.png)


For Iris dataset:
I show the data distribution by average, standard deviation, and value frequency(binning might be needed) of every feature.  

Also split data based on their labels (targets) and visualize each feature again.  
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午4.01.52.png)
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午4.02.05.png)
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午4.02.15.png)
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午4.02.23.png)

## 3.Data Preprocessing
Drop features with any missing value, and transform data format and shape, then shuffle data

## 4.Model Construction
I construct two Naïve Bayes classifiers for the two datasets WITHOUT any package-provided model.  
Naïve Bayes divider 𝑀 in log-space:
𝑀(𝐪)=argmax𝑌∈𝕋[log𝑃(𝑌)+∑𝑚𝑖=1log𝑃(𝑋𝑖|𝑌)]
where 𝐪={𝑋1,𝑋2,...,𝑋𝑚} is a sample to be predicted, whose features are 𝑋1 to 𝑋𝑚. 𝕋 is the set of all possible labels.  

For the mushroom dataset, whose features are all categorical, 𝑃(𝑋𝑖|𝑌) was computed with and without Laplace smoothing for result comparison.  

Without Laplace smoothing:
𝑃(𝑋𝑖|𝑌)=𝑁(𝑋𝑖|𝑌)𝑁(𝑌). 

Laplace smoothing:
𝑃(𝑋𝑖|𝑌)=𝑁(𝑋𝑖|𝑌)+𝑘𝑁(𝑌)+𝑘𝜏. 

where 𝜏 is the number of all possible events of feature 𝑋𝑖. 

For Iris dataset, whose features are all numerical, assume 𝑃(𝑋𝑖|𝑌) follows a 1D-Normal(Gaussian) distribution.  

𝑃(𝑋𝑖|𝑌)=1𝜎2𝜋√𝑒−(𝑥−𝜇)22𝜎2
where 𝜇,𝜎 are the mean and standard deviation of feature 𝑋𝑖 respectively, while label 𝑌 is determined.  

## 5.Train-Test-Split
I implement two validation methods:  

### a.Holdout validation with the ratio 7:3. 

### b.K-fold cross-validation with 𝐾=3. 

And then obtain the final performance by averaging all folds’ performance.

Show the performances using:  

### a.Confusion matrix  

### b.Accuracy. 

### c.Sensitivity(Recall). 

### d.Precision. 
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午4.00.50.png)
![Image text](https://github.com/skyMei-J/Image/blob/main/截圖%202021-09-04%20下午4.02.42.png)
## 6.Comparison & Conclusion

## Data

## 1. Mushroom dataset

Data can be downloaded here:
https://archive.ics.uci.edu/ml/datasets/mushroom  

the first column is the label (edible=e, poisonous=p)

Data Set Information:
This data set includes descriptions of hypothetical samples corresponding to 23 species of gilled mushrooms in the Agaricus and Lepiota Family (pp. 500-525). Each species is identified as definitely edible, definitely poisonous, or of unknown edibility and not recommended. This latter class was combined with the poisonous one. The Guide clearly states that there is no simple rule for determining the edibility of a mushroom; no rule like ‘‘leaflets three, let it be’’ for Poisonous Oak and Ivy.

## 2. Iris dataset

Data can be downloaded here:
https://archive.ics.uci.edu/ml/datasets/iris  


Data Set Information:
This is perhaps the best known database to be found in the pattern recognition literature. Fisher’s paper is a classic in the field and is referenced frequently to this day. (See Duda & Hart, for example.) The data set contains 3 classes of 50 instances each, where each class refers to a type of iris plant. One class is linearly separable from the other 2; the latter are NOT linearly separable from each other. Predicted attribute: class of iris plant. This is an exceedingly simple domain.

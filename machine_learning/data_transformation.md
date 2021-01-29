# Preparing Data For Machine Learning 

**Keywords**: discretization, normalization, continuous feature, data minining, classification 

Machine Learning algorithms make assumptions to the data. 

In order to prepare the data based on the assumptions

1. Load the dataset

2. Split dataset into the input and output variables for Machine Learning
   algorithm. 

3. Apply a pre-processing transform to the input variables

4. Summarize the data to show change. 


## Data Smoothing

The method is used to remove nosie from a dataset. 

Noise defines as the distorted and meaningless data within the dataset. 

Smoothing uses algorithms to highlight the special features in the data. 

After removing noise, Machine Learning algorithms can detect any small changes to the data to
detect special patterns. 


## Data Aggregation 

Aggregation is the process of collecting data from a variety of sources and storing it in a single format.

Here, data is collected, stored, analyzed and presented in a report or summary format. It helps in gathering more information about a particular data cluster.The method helps in collecting vast amounts of data.

This is a crucial step as accuracy and quantity of data is important for proper analysis. Companies collect data about their website visitors. This gives them an idea about customer demographics and behaviour metrics. This aggregated data assists them in designing personalized messages, offers and discounts.


## Discretization 

Discretization is the process of converting continuous data into a set of data intervals. Continuous attribute values are substituted by small interval labels. This makes the data easier to study and analyze.

If a continuous attribute is handled by a data mining task, then its discrete values can be replaced by constant quality attributes. This improves the efficiency of the task.

This method is also called data reduction mechanism as it transforms a large dataset into a set of categorical data. Discretization also uses decision tree-based algorithms to produce short, compact and accurate results when using discrete values.


Supervised discretization considers class information; while unsupervised
discretization does not considers class information. 

### Binning

Binning is the simplest method to discretize a continuous valued attribute by creating a specified number of bins. The bins can be created by **equal-width** and **equal-frequency**.  A means to produce nominal values from continuous values.

#### Equal Width

- a type of binning

- width =  (x_max - x_min)/k 

- k is the number of equally sized bins
    
- Bin boundaries, or thresholds, at x_min + ib where i = 1, 2, ... ,k

- Outliers take extreme values. One solution can be to remove the outliers using a threshold.

- Equal Width Discretization does not improve the spread. 

- Equal Width Discretization is useful when combined with categorical
  encodings.


Sample Python code snippet: 
```python
# import libaries 
import pandas as pd 
from sklearn.preprocessing import KBinsDiscretizer

# load data 
data = pd.read_csv("your_data.csv")

# create the discretizer object with strategy uniform and 8 bins
discretizer = KBinsDiscretizer(n_bins=8, encode="ordinal", strategy="uniform")

# fit the discretizer to the train set
discretizer.fit(train)

# apply the discretization
train = discretizer.transform(train)
test = discretizer.transform(test)
```

#### Equal Frequency

- a type of binning 

- Equal Frequency Discretization improves the value spread.

- The arbitrary binning may disturb the relationship with the target. 

- Handles outliers well

- Useful when combined with categorical encoding


Sample Python code snippet: 
```python
# import libaries 
import pandas as pd 
from sklearn.preprocessing import KBinsDiscretizer

# load data 
data = pd.read_csv("your_data.csv")

# create the discretizer object with strategy uniform and 8 bins
discretizer = KBinsDiscretizer(n_bins=8, encode="ordinal", strategy="quantile")

# fit the discretizer to the train set
discretizer.fit(train)

# apply the discretization
train = discretizer.transform(train)
test = discretizer.transform(test)
```
### Clustering

#### K-Means Clustering

The discretization method of applying K-Means clustering to the continuous
data. Then each cluster is considered as a bin. 

#### Quick review of K-Means Clustering Algorithm

1. Create k random points. These poinst will be center of clusters

2. Associate every data with the closest center (using some distance metric
   like Euclidean distance). 

3. Finally re-compute each center position in the center of its associated
   points. 

> Step 2 and 3 are repeated until a convergence of a new center position is
> reached.

#### Applications of K-Means Clustering Algorithm
- Color Quantization (is a type of vector quantization) is the task for
  reducing the color paletee of an image to a fixed number of colors k.


### ID3 type - ID3 and C4.5 
- Popular algorithms for decision tree induction that uses entropy measures. 

- The algorithm construct an inductive decision tree by selecting a feature if
  its branching results in the overall minimum entropy at the next layer of the
  decision tree. 

- Binarizes a range of values while building a decision tree

- When used in discretization, entropy is usually used in a supervised manner. 


### D2. 
- The discretization method applies entropy measure to find a potential
cut-point to split a range of continuous values into two intervals. 

- D2 is a static method that discretizes the whole spaces.

- Usually used for building a classifier. 

### Discretization Summary 

Simple Discretization
- Equal Width
- Equal Frequency Width (or a form of binning)

### Discretization References 
[Discretization: An Enabling Technique](https://sci2s.ugr.es/keel/pdf/algorithm/articulo/liu1-2.pdf)
[Supervised and Unsupervised Discretization of Continuous Features](http://robotics.stanford.edu/users/sahami/papers-dir/disc.ps)
|              	|                                                                                Global                                                                                	|                                            Local                                           	|
|:------------:	|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------:	|:------------------------------------------------------------------------------------------:	|
|  Supervised  	| 1RD (Holt) </br> Adaptive Quantizers </br> ChiMerge (Kerber) </br> D-2 (Catlett) </br> Fayyad and Irani / Ting </br> Supervised MCC </br> Predictive Value Max </br> 	| Vector Quantization </br> Hierarchical Maximum Entropy </br> Fayyad Irani </br> C4.5 </br> 	|
| Unsupervised 	|                                            Equal width interval </br> Equal frequency interval </br> Unsupervised MCC                                                    	|                                     K-Means Clustering                                     	|




## Generalization 

In this process, low-level data attributes are transformed into high-level data attributes using concept hierarchies. This conversion from a lower level to a higher conceptual level is useful to get a clearer picture of the data. For example, age data can be in the form of (20, 30) in a dataset. It is transformed into a higher conceptual level into a categorical value (young, old).

Data generalization can be divided into two approaches – data cube process (OLAP) and attribute oriented induction approach (AOI).

## Attribute construction 

Attribute construction create new attributes from an existing set of
attributes. 

## Normalization - Rescale Data

Normalization refers to rescaling each observation (row) to have a length of 1
(called a unit norm or vector with the length of 1 in Linear Algebra.)


Using Normalization as a pre-processing method can be useful for sparse
datasets (lots of zeros) with attributes of varying scales.

Normalization is useful in the following Machine Learning Algorithms
- Algorithms that weight input values 
    - Neural Networks

- Algorithms that use distance measures
    - K-Nearest Neighbors 

Popular normalization methods are 
- Min-max normalization
- Decimal scaling
- Z-score normalization.

### Standardize Data

Standardization is a useful technique to transform attributes with a Gaussian
distribution and differing means and standard deviations to a standard Gaussian
distribution with a mean of 0 and a standard deviation of 1. 

Assuming a Gaussian distribution in the input variables, these algorithms are
suitable for Standardization such as Linear Regression, Logistic Regression,
and Linear Discriminate Analysis. 

```python
# Standardize data (0 mean, 1 stdev)

from sklearn.preprocessing import StandardScaler
from pandas import read_csv
from numpy import set_printoptions
filename = 'pima-indians-diabetes.data.csv'
names = ['preg', 'plas', 'pres', 'skin', 'test', 'mass', 'pedi', 'age', 'class'] dataframe = read_csv(filename, names=names)
array = dataframe.values

# separate array into input and output components
X = array[:,0:8]
Y = array[:,8]
scaler = StandardScaler().fit(X)
rescaledX = scaler.transform(X)

# summarize transformed data
set_printoptions(precision=3)
print(rescaledX[0:5,:])
```
```text
[[ 0.64 0.848 0.15 0.907 -0.693 0.204 0.468 1.426]
[-0.845 -1.123 -0.161 0.531 -0.693 -0.684 -0.365 -0.191]
[ 1.234 1.944 -0.264 -1.288 -0.693 -1.103 0.604 -0.106]
[-0.845 -0.998 -0.161 0.155 0.123 -0.494 -0.921 -1.042]
[-1.142 0.504 -1.505 0.907 0.766 1.41 5.485 -0.02 ]]
```

### Binarize Data (Make Binary)

Transforms data using a binary threshold. 

All values above the threshold are marked 1 and all equal to or below are
marked as 0. This is called binarizing data or thresholding data. 

Binarizing data is useful when 
- when you have probabilities

- during feature engineering, when adding a new feature that indicate something
  meaningful. 

```python
from sklearn.preprocessing import Binarizer
from pandas import read_csv 
from numpy import set_printoptions

names = ['preg', 'plas', 'pres', 'skin', 'test', 'mass', 'pedi', 'age', 'class']

dataframe = read_csv(filename, names=names)

array = dataframe.values

# separate array into input and output components
X = array[:,0:8]
Y = array[:,8]

binarizer = Binarizer(threshold=0.0).fit(X)
binaryX = binarizer.transform(X)

# summarize transformed data
set_printoptions(precision=3)
print(binaryX[0:5,:])

```
You can see that all values equal or less than 0 are marked 0 and all of those above 0 are marked 1.
```text
[[1.1. 1. 1. 0. 1. 1. 1.] 
[ 1. 1. 1. 1. 0. 1. 1. 1.] 
[ 1. 1. 1. 0. 0. 1. 1. 1.] 
[ 1. 1. 1. 1. 1. 1. 1. 1.] 
[ 0. 1. 1. 1. 1. 1. 1. 1.]]
```






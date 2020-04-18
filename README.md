# Boston-Housing-Pt2

## Question 1
Give me a brief analysis

```python
import numpy as np
import pandas as pd
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
from sklearn import metrics
#from sklearn.tree import export_graphvis
from sklearn.externals.six import StringIO  
from IPython.display import Image  
from sklearn.tree import export_graphviz
import pydotplus

df = pd.read_excel('/Users/Charles/Desktop/BostonHousing.xlsx', header=0)

X = df.iloc[:, range(13)]
y = df['CAT. MEDV']

dy = df.iloc[:, 14]

cf = DecisionTreeClassifier(max_depth = 2)

#tree = cf.fit(X, y)plot_tree(tree)

for n_leaves in range(2, 10):     


    cf = DecisionTreeClassifier(max_depth = n_leaves)   

tree = cf.fit(X, y)   

accuracy = tree.score(X, y)    

print('Tree with {} leaves has an accuracy of {}'.format(n_leaves, accuracy))

```
## Tree with 9 leaves has an accuracy of 1.0

>Utilizing the coding above, we can see that after the decision tree has made the required splits and finally reaches 9 decision leaves, we will have 100% accuracy with how the program can classify our Boston Housing Data. 

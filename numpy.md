import numpy as np

x = np.array([1, 2, 3])  # generate an numpy array

# np.reshape((dim1, dim2))
# data[i, j]   refernce element in a numpy array
Example
>>> data = np.random.randn(3, 3, 3)
>>> data.shape
(3, 3, 3)
>>> data[1,1,1]
1.4715475830719211

X_flatten = X.reshape(X.shape[0], -1).T  # flatten np array to 1d array

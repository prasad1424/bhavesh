import math
import numpy as np

# Function to calculate the Pearson correlation coefficient manually
def correlationCoefficient(X, Y, n):
    # Calculating sum of the elements of array X and Y
    sum_X = sum(X)
    sum_Y = sum(Y)
    
    # Calculating sum of the squares of the elements of array X and Y
    squareSum_X = sum([x**2 for x in X])
    squareSum_Y = sum([y**2 for y in Y])
    
    # Calculating the sum of the products of elements in X and Y
    sum_XY = sum([X[i] * Y[i] for i in range(n)])
    
    # Use formula for calculating correlation coefficient
    corr = (n * sum_XY - sum_X * sum_Y) / \
            math.sqrt((n * squareSum_X - sum_X * sum_X) * (n * squareSum_Y - sum_Y * sum_Y))
    
    return corr

# Driver function for manual calculation
X = [15, 18, 21, 24, 27]
Y = [25, 25, 27, 31, 32]

# Find the size of the arrays
n = len(X)

# Function call to correlationCoefficient
print(f'Manual Pearson correlation coefficient: {correlationCoefficient(X, Y, n):.6f}')

# Using NumPy for comparison
x = np.array([1, 2, 3, 4, 5])
y = np.array([2, 3, 5, 7, 11])

correlation = np.corrcoef(x, y)[0, 1]
print(f'Pearson correlation coefficient (NumPy): {correlation}')

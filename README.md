# Experiment-3-Correlation-and-Regression-for-Data-Analysis

# Aim: 
	To analyse given data using co-efficient of correlation and regression line 
  
  <img width="1180" height="120" alt="image" src="https://github.com/user-attachments/assets/62ba8618-34f6-4718-9233-b36f6ca975ff" />
  
# Software Required: Python 

# Theory
1. Correlation measures the strength and direction of the relationship between two variables (say, X and Y).
  
2. If one variable changes, correlation tells us how the other variable changes on average.
   
3. The correlation coefficient (r) ranges from –1 to +1: +1 means perfect positive correlation, –1 means perfect negative correlation, and 0 means no correlation.
   
4. Regression shows how one variable (Y) depends on another variable (X). It provides a line (equation) that best fits the data.
   
5. The regression line of Y on X is expressed as:  Y = a + bX,  where a is the intercept and b is the regression coefficient (slope).
   
# Algorithm 

<img width="1143" height="477" alt="image" src="https://github.com/user-attachments/assets/d3d41b8d-bee6-4b5f-a6fe-ef6997126cf2" />

# Program

Name: YUVASREE S
Slot-name:3P1-1

import numpy as np
import math
import matplotlib.pyplot as plt

# Input x and y values
x = [int(i) for i in input("Enter x values (space separated): ").split()]
y = [int(i) for i in input("Enter y values (space separated): ").split()]

# Check equal length
if len(x) != len(y):
    raise SystemExit("Error: x and y must have the same number of values.")

N = len(x)

# Initialize sums
Sx = Sy = Sxy = Sx2 = Sy2 = 0

# Compute sums
for i in range(N):
    Sx += x[i]
    Sy += y[i]
    Sxy += x[i] * y[i]
    Sx2 += x[i] ** 2
    Sy2 += y[i] ** 2

# Correlation coefficient r
den = math.sqrt((N * Sx2 - Sx ** 2) * (N * Sy2 - Sy ** 2))
if den == 0:
    raise SystemExit("Denominator zero when computing correlation.")

r = (N * Sxy - Sx * Sy) / den
print("The Correlation coefficient is %0.3f" % r)

# Regression coefficient (slope) of Y on X
byx = (N * Sxy - Sx * Sy) / (N * Sx2 - Sx ** 2)

# Means
xmean = Sx / N
ymean = Sy / N

print("The Regression line Y on X is :::")
print("y = %.3f + %.3f (x - %.3f)" % (ymean, byx, xmean))

# Scatter plot
plt.scatter(x, y)

# Regression function
def Reg(xv):
    return ymean + byx * (xv - xmean)

# Regression line plot
x_plot = np.linspace(min(x), max(x), 100)
y_plot = Reg(x_plot)
plt.plot(x_plot, y_plot, 'r')

plt.xlabel('x-data')
plt.ylabel('y-data')
plt.legend(['Regression Line', 'Data Points'])
plt.grid(True)
plt.show()

https://colab.research.google.com/drive/18iW8j5_KuycRt2zbG14p2f3-pK2UPv4_#scrollTo=cWhWifdWw7Bc



# Output

<img width="750" height="624" alt="Screenshot 2025-11-17 135307" src="https://github.com/user-attachments/assets/5ebeff07-f051-4c4a-8dd9-25663e7979cd" />



# Result
  The correlation and regression for data analysis of objects from feeder using probability distribution are calculated.





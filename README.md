# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Startv the program.
2. import numpy as np.
3. Give the header to the data.
4. Find the profit of population.
5. Plot the required graph for both for Gradient Descent Graph and Prediction Graph.
6. End the program.


## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by   : Shivaram M.
RegisterNumber : 212223040195
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd


data=pd.read_csv("/Users/home/Desktop/Workspace/College/Semester_4/Machine_Learning/Experiments/EX03/50 Startups.csv",header=None)

plt.scatter(data[0],data[1])
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of city (10,000s)")
plt.ylabel("Profit ($10,000")
plt.title("Profit Predication")

def computeCost(x,y,theta):
  m=len(y)
  h=x.dot(theta)
  square_err=(h-y)**2
  return 1/(2*m)*np.sum(square_err)
  
data_n=data.values
m=data_n[:,0].size
x=np.append(np.ones((m,1)),data_n[:,0].reshape(m,1),axis=1)
y=data_n[:,1].reshape(m,1)
theta=np.zeros((2,1))
computeCost(x,y,theta)

def gradientDescent(x,y,theta,alpha,num_iters):
  m=len(y)
  J_history=[]
  for i in range(num_iters):
    predictions=x.dot(theta)
    error=np.dot(x.transpose(),(predictions-y))
    descent=alpha*1/m*error
    theta-=descent
    J_history.append(computeCost(x,y,theta))
  return theta,J_history
  
theta,J_history = gradientDescent(x,y,theta,0.01,1500)
print("h(x) ="+str(round(theta[0,0],2))+" + "+str(round(theta[1,0],2))+"x1")

plt.plot(J_history)
plt.xlabel("Iteration")
plt.ylabel("$J(\Theta)$")
plt.title("Cost function using Gradient Descent")


plt.scatter(data[0],data[1])
x_value=[x for x in range(25)]
y_value=[y*theta[1]+theta[0] for y in x_value]
plt.plot(x_value,y_value,color='r')
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City (10,000s)")
plt.ylabel("Profit ($10,000")
plt.title("Profit Prediction")

def predict(x,theta):
  predictions= np.dot(theta.transpose(),x)
  return predictions[0]
  
predict1=predict(np.array([1,3.5]),theta)*1000
print("For population = 35,000, we predict a profit of $"+str(round(predict1,0)))

predict2=predict(np.array([1,7]),theta)*1000
print("For population = 70,000, we predict a profit of $"+str(round(predict2,0)))
*/
```

## Output:
<img width="1680" alt="Screenshot 2025-05-23 at 1 16 33 PM" src="https://github.com/user-attachments/assets/bdfc50dc-5baf-409e-9654-c7ce6ba406d8" />
<img width="678" alt="Screenshot 2025-05-23 at 1 16 46 PM" src="https://github.com/user-attachments/assets/4e578787-c2a4-4b77-8cff-23b7bd547359" />



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.

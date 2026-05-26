# Correlation and regression for data analysis
# Aim : 

To analyse given data using coeffificient of correlation and regression line
![image](https://user-images.githubusercontent.com/104613195/168224136-d6b64e64-7d3d-4775-9337-c8f96fe41f2d.png)


# Software required :  

Python

# Theory:

Correlation describes the strength of an association between two variables, and is completely symmetrical, the correlation between A and B is the same as the correlation between B and A. However, if the two variables are related it means that when one changes by a certain amount the other changes on an average by a certain amount.  

If y represents the dependent variable and x the independent variable, this relationship is described as the regression of y on x. The relationship can be represented by a simple equation called the regression equation. The regression equation representing how much y changes with any given change of x can be used to construct a regression line on a scatter diagram, and in the simplest case this is assumed to be a straight line.

# Procedure :

![image](https://user-images.githubusercontent.com/104613195/168225866-ac8f6610-bdc3-4ac2-a24e-2b24ba08e189.png)

# Program :
```

for i in range(N):
  Sum_x+=x[i]
  Sum_y+=y[i]
  Sum_xy+=x[i]*y[i]
  Sum_x2+=x[i]*x[i]
  Sum_y2+=y[i]*y[i]

den=math.sqrt((N*Sum_x2-Sum_x**2)*(N*Sum_y2-Sum_y**2))
if den==0:
  raise SystemExit("Denominator is zero")

r=(N*Sum_xy-Sum_x*Sum_y)/den
print(f"The correlation coefficient is {r:.3f}")

m=(N*Sum_xy-Sum_x*Sum_y)/(N*Sum_x2-Sum_x**2)

xmean=Sum_x/N
ymean=Sum_y/N

c=ymean-m*xmean

print(f"The equation of line is y={m:.3f}x+{c:.3f}")

plt.scatter(x,y)

def Reg(xv):
  return ymean+m*(xv-xmean)

x_plot=np.linspace(min(x),max(x),51)
y_plot=Reg(x_plot)

plt.plot(x_plot,y_plot,'r')

plt.xlabel('x')
plt.ylabel('y')
plt.legend(['Regression Line','Data points'])
plt.grid()
plt.show()
```


# Result

# Output 
<img width="700" height="149" alt="image" src="https://github.com/user-attachments/assets/aae5bdac-14b4-4697-bf6f-2940de26157e" />


<img width="803" height="690" alt="image" src="https://github.com/user-attachments/assets/d6b64b26-05d7-4cbc-aea4-49737a153521" />


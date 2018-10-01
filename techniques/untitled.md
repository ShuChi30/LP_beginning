---
description: Simple start with gurobi
---

# Python+Gurobi

{% code-tabs %}
{% code-tabs-item title="Transportation\_Problem" %}
```python
from gurobipy import*
m = Model("Transpertation problem2")

#parameters
I,d = multidict({1:80,2:270,3:250,4:160,5:180})
J,M = multidict({1:500,2:500,3:500})
c = {(1,1):4,(2,1):5,(3,1):6,(4,1):8,(5,1):10,
    (1,2):6,(2,2):4,(3,2):3,(4,2):5,(5,2):8,
    (1,3):9,(2,3):7,(3,3):4,(4,3):3,(5,3):4
}

#variables
x = {}
for i in I:
    for j in J:
        x[i,j] = m.addVar(lb=0,vtype='C')
        
#constraints        
for i in I:
    m.addConstr(quicksum(x[i,j] for j in J) == d[i])
    
for j in J:
    m.addConstr(quicksum(x[i,j] for i in I) <= M[j])
    
m.update()

#objective 
m.setObjective(quicksum(c[i,j]*x[i,j] for (i,j) in x),GRB.MINIMIZE)

m.optimize()

#output

print("opt. value =",m.ObjVal)
for i in I:
    for j in J:
        print("%4d from factory %d to customer %d"%(x[i,j].X,j,i))
```
{% endcode-tabs-item %}

{% code-tabs-item title="0-1 Knapsack\_Problem" %}
```python
from gurobipy import*

m = Model("Knapsack")

#collection of values
#item,value
J,v = multidict({1:16,2:19,3:23,4:28})

#Information of Items
#(1,j):weight,(2,j):volume
a = {(1,1):2,(1,2):3,(1,3):4,(1,4):5,
    (2,1):3000,(2,2):3500,(2,3):5100,(2,4):7200
    }

#collection of constraint
#b:constraint bound
I,b = multidict({1:7,2:10000})

#variables
x = {}
for j in J:
    x[j] = m.addVar(vtype='B', name="x(%d)" % j)
    
m.update()

#constraints
for i in I:
    m.addConstr(quicksum(a[i, j] * x[j] for j in J) <= b[i])

m.setObjective(quicksum(v[j] * x[j] for j in J), GRB.MAXIMIZE)
m.update()

m.optimize()

print("opt value=",m.ObjVal)
EPS = 1.e-6
for v in m.getVars():
    #if v.X > EPS:
        print(v.VarName,v.X)  

```
{% endcode-tabs-item %}

{% code-tabs-item title="Facility\_Problem" %}
```python
from gurobipy import*
x = {}
y = {}
c = {}
d = {}
M = {}
f = {}
#i:factory,j:customer
#cost(i,j)
c = {(1,1):10,(2,1):20,(3,1):30,(4,1):40,
    (1,2):24,(2,2):16,(3,2):22,(4,2):30,
    (1,3):36,(2,3):14,(3,3):12,(4,3):8
    }
#demand
d[1]=22; d[2]=14; d[3]=26;
#capacity (of factory i)
M[1]=28; M[2]=20; M[3]=24; M[4]=24;
#facility(static)cost
f[1]=23; f[2]=12; f[3]=18; f[4]=32;

model = Model("Facility")
#variables
#x[i]:open or closed
#y[i,j]:transpotation volume
for i in range(1,5):
    x[i] = model.addVar(vtype="B",name="x(%s)"%(i))
    for j in range(1,4):
        y[i,j] = model.addVar(lb=0,vtype="I",name="y(%s,%s)"%(i,j))
        
model.update()

for a in range(1,5):
    model.addConstr(quicksum(y[i,j]for (i,j) in y if i==a)<=M[a])
for b in range(1,4):
    model.addConstr(quicksum(y[i,j]for (i,j) in y if j==b)>=d[b])
for i in range(1,5):
    for j in range(1,4):
        model.addConstr(100000*x[i]-y[i,j]>=0)
        
model.setObjective(quicksum(x[i]*f[i] for i in x)+quicksum(y[i,j]*c[i,j] for (i,j) in y),GRB.MINIMIZE)
model.optimize()

print("opt value:",model.ObjVal)
for i in I:
    print(i,x[i].X)
model.write("out.lp")
```
{% endcode-tabs-item %}
{% endcode-tabs %}











## Linear Optimization

Objective Function:

$$
min Z=3x+4y
$$

```text
model.setObjective(3*x+4*y,GRB.MINIMIZE)
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

```
// Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```




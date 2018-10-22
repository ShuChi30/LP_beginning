# paper study

## About Maintenance & Scheduling

## Multi-objective production scheduling of probe process in semiconductor manufacturing

Production Planning & Control The Management of Operations Volume 11, 2000 - Issue 7

_Young Hoon Lee, Byung Ki Lee & Bongju Jeong_

{% embed url="https://www.tandfonline.com/doi/abs/10.1080/095372800432124" %}

In probe process, 

Different devices can be processed in the same machines. Each combinations have different capacity \(production rate\).

The utilization are ~95% is the most practical in mfg line, because 6-10%of machine time is contributed to machine failure or preventive maintenance time.

To meet the monthly production target, also objective to minimize the number of machines. \(In order to reduce the probability of machine failure\)

### Problem1: Monthly production planning

Objective function: $$Min \Sigma  \Sigma x_{i,j} $$ 

 $$x_{i,j}$$: the number of machines of type  $$i$$ to process device $$j$$ 

Constraints: 1.Machine capability 2.Production Target 3. Equipment Availability

### Problem2 : Daily production planning and scheduling

using Heuristic Scheduling Algorithm\*4

1.PR \(maximize production volume and progress\)

2.UT \(maximize utilization of machines\)

3.HB \(Hybrid heuristic for maximize both\)

4.LP \(LP-based heuristic for maximize both\)

Multi-objective: 1.Production Volume Rate 2.Utilization --&gt; Weighted

### Results

LP-based heuristic has the best performance. 

## Optimal Preventive Maintenance Scheduling in Semiconductor Manufacturing

 Xiaodong Yao, Member, IEEE, Emmanuel Fernández-Gaucherand, Senior Member, IEEE, Michael C. Fu, and Steven I. Marcus, Fellow, IEEE

{% embed url="https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=1321132" %}

Semiconductor PM scheduling challenge:

1. **Highly integrated system**: A PM schedule on one tool can have significant impact on upstream or downstream tools.
2. **Cluster Tools**: A cluster tool is a highly integrated machine that is composed of several chambers and robots, where different PM tasks on different chambers have to be coordinated carefully in order to maximize the availability \(therefore, throughput\) of the entire tool.

![Cluster Tool](../.gitbook/assets/image.png)

### Consideration:

**Interdependence of PM tasks** : The entire tool's availability is dependent on each chamber.

**Uncertainty of WIP**  : PM tasks should be avoided when a large amount of work is expected to arrive soon.

time window policy --&gt; “pull” or “push” a planned PM task beyond a certain period 

Besides...

better to **Consolidate** PM tasks

**Tool failures, costs for supplies, lost production, technician availability constraints**, should also be accounted for

### Hierarchical PM Planning and Scheduling

#### 1. Long-term horizon: PM planning model

Considering **technical state** \(conventional\) information  ,e.g.age of machines

and **operating state** information , e.g.demand pattern

formulated as MDP \(**Markov Decision Process**\) due to feature of underlying stochastic processes and sequential decision epoches.

--&gt; Output : **Optimized time window policy**

#### 2. Short-term horizon: PM scheduling model

1. Interdependence of different PM tasks in terms of their joint impact on the entire tool’s throughput.
2. **Match up** between the tool’s availability and projected incoming WIP.

![ Two-level hierarchical modeling framework](../.gitbook/assets/ying-mu-kuai-zhao-20180926-xia-wu-1.17.19.png)

### Background

two types of PM : Calendar-based, Operation-based

Even if a PM window is operation-based, e.g., “2000 wafers 10%” since last PM, it will be converted to a calendar basis. If an optimization model were to track wafer count, this would lead to a very high level of computational complexity. _\[HOW TO convert, see reference 15\]_

### MIP of PM scheduling

MIP\(Mixed Integer Programming\) model

Target : To determine the best time for doing each PM

Input : configuration matrix for a cluster tool

A set of PM tasks need to be placed within the time window.

Objective : Max overall tool availability, Min WIP

...

## 

{% embed url="https://www.hindawi.com/journals/mpe/2012/875641/" %}



{% embed url="https://onlinelibrary.wiley.com/doi/full/10.1111/j.1937-5956.2000.tb00465.x" %}


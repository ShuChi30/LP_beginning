# List

## About Maintenance & Scheduling

## Multi-objective production scheduling of probe process in semiconductor manufacturing

Production Planning & Control The Management of Operations Volume 11, 2000 - Issue 7

_Young Hoon Lee, Byung Ki Lee & Bongju Jeong_

{% embed data="{\"url\":\"https://www.tandfonline.com/doi/abs/10.1080/095372800432124\",\"type\":\"link\",\"title\":\"Multi-objective production scheduling of probe process in semiconductor manufacturing\",\"description\":\"Semiconductor products are manufactured through the process of wafer fabrication, probe or electrical die sorting, assembly and final test. In particular, in this study we deal with the wafer probe process which requires several types of equipment with different capacities. As a connecting procedure of the fabrication and the assembly, the probe process may determine the capacity of whole semiconductor manufacturing. The throughput needs to be maximized as for most manufacturing lines. Because of unexpected machine failure and planned preventive maintenance, the utilization of machines has to be kept at a certain range for stabilizing the process. Hence, the production progress for each device and the utilization of machines are objectives to be maximized simultaneously, while both tend to work in opposite directions because of changeover time loss.\",\"icon\":{\"type\":\"icon\",\"url\":\"https://www.tandfonline.com/favicon.ico\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://www.tandfonline.com/doi/cover-img/10.1080/095372800432124\",\"width\":110,\"height\":146,\"aspectRatio\":1.3272727272727274}}" %}

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

{% embed data="{\"url\":\"https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=1321132\",\"type\":\"link\",\"title\":\"Optimal preventive maintenance scheduling in semiconductor manufacturing - IEEE Journals & Magazine\",\"description\":\"Preventive maintenance \(PM\) scheduling is a very challenging task in semiconductor manufacturing due to the complexity of highly integrated fab tools and s\",\"icon\":{\"type\":\"icon\",\"url\":\"https://ieeexplore.ieee.org/favicon.ico\",\"aspectRatio\":0}}" %}

{% embed data="{\"url\":\"https://onlinelibrary.wiley.com/doi/full/10.1111/j.1937-5956.2000.tb00465.x\",\"type\":\"link\",\"title\":\"COMBINED PRODUCTION AND MAINTENANCE SCHEDULING FOR A MULTIPLE‐PRODUCT, SINGLE‐ MACHINE PRODUCTION SYSTEM - SLOAN - 2000 - Production and Operations Management - Wiley Online Library\",\"icon\":{\"type\":\"icon\",\"url\":\"https://onlinelibrary.wiley.com/favicon.ico\",\"aspectRatio\":0}}" %}



{% embed data="{\"url\":\"https://www.hindawi.com/journals/mpe/2012/875641/\",\"type\":\"link\",\"title\":\"Genetic Algorithm for Job Scheduling with Maintenance Consideration in Semiconductor Manufacturing Process\",\"description\":\"This paper presents wafer sequencing problems considering perceived chamber conditions and maintenance activities in a single cluster tool through the simulation-based optimization method. We develop optimization methods which would lead to the best wafer release policy in the chamber tool to maximize the overall yield of the wafers in semiconductor manufacturing system. Since chamber degradation will jeopardize wafer yields, chamber maintenance is taken into account for the wafer sequence decision-making process. Furthermore, genetic algorithm is modified for solving the scheduling problems in this paper. As results, it has been shown that job scheduling has to be managed based on the chamber degradation condition and maintenance activities to maximize overall wafer yield.\",\"icon\":{\"type\":\"icon\",\"url\":\"https://www.hindawi.com/images/apple-touch-icon-144x144.png\",\"width\":144,\"height\":144,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://images.hindawi.com/images/social/MPE.jpg\",\"width\":1200,\"height\":630,\"aspectRatio\":0.525}}" %}


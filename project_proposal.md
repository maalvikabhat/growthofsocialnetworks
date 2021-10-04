Visualizing the Growth of Social Networks

Using a SNAP dataset, which holds a Wikipedia network of top categories with 1791489 nodes and 28511807 edges, we will  represent the online encyclopedia as a directed graph. 
Additionally, we hope to identify how core certain words are to the network, which is how much the network would change if that node is removed. Resilience is the ability of the network to remain minimally affected by behavior of individual nodes.


Annotated Bibliography: 

Social Resilience in Online Communities: the Autopsy of Friendster 
https://dl.acm.org/doi/10.1145/2512938.2512946
This paper discusses analysis of social networks using k-core analysis and measurement of resilience. We plan to implement k-core analysis in our initial experiment. 
 
Preferential attachment in the growth of social networks: the internet encyclopedia Wikipedia 
https://arxiv.org/pdf/physics/0602026.pdf
The authors present an analysis of the statistical properties and growth of Wikipedia. The topological properties of this graph are in close analogy with those of the World Wide Web, but they point out that there is a very different growth mechanism. We plan to identify a growth mechanism in our experiment. 
Wikipedia growth can be described by local rules such as the preferential attachment mechanism, though users can act globally on the network. 
 
Improving the Robustness of Online Social Networks: A Simulation Approach of Network Interventions 
https://doi.org/10.3389/frobt.2020.00057 
This paper explores methods of controlling how robust an online social network is. 
They define robustness as the average coreness of each node, or how much effect removing that node would have on the system. Our end goal in the experiment is to identify coreness of different nodes (words) in the Wikipedia ecosystem.
Their model incorporates benefit and cost functions to model whether a node will remain in the network. Their analysis explores ways to keep users in the network. 
They conclude that keeping a few core nodes in the network is more effective than keeping many outer nodes in the network at improving the robustness of the network. 

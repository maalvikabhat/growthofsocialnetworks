# Visualizing the Growth of Social Networks
#### Maalvika Bhat, Hyunkyung Rho

### Abstract
Using a SNAP dataset, which holds a Wikipedia network of top categories with 1791489 nodes and 28511807 edges, we will represent the online encyclopedia as a directed graph. 
Additionally, we hope to identify how core certain words are to the network, which is how much the network would change if that node is removed. Resilience is the ability of the network to remain minimally affected by behavior of individual nodes. Thus, we expect to discover different "cores" from the Wikepedia network apart from philosophy (as previously explored in the class).

### Areas of Concern
One of the criterias for a good project asks for available data and supporting materials. Howeer, the Wikipedia network dataset that we plan on using is a big dataset that has a high probability of taking a long time for processing. If we were to scale the dataset down by getting rid of a portion of the nodes and the connections between them, we would be losing the integrity of the results from analyzing the experiments on the Wikipedia network. Therefore, we plan on using the Facebook network dataset (which is smaller in scale compared to the Wikipedia network dataset) in case the processing takes too long. 

### Annotated Bibliography 
- Social Resilience in Online Communities: the Autopsy of Friendster 
https://dl.acm.org/doi/10.1145/2512938.2512946
This paper discusses analysis of social networks using k-core analysis and measurement of resilience. Coreness is a measure that can help identify tightly interlinked groups within a network. A k-core is a maximal group of entities, all of which are connected to at least k other entities in the group. 
 
- Preferential attachment in the growth of social networks: the internet encyclopedia Wikipedia 
https://arxiv.org/pdf/physics/0602026.pdf
The authors present an analysis of the statistical properties and growth of Wikipedia. The topological properties of this graph are in close analogy with those of the World Wide Web, but they point out that there is a very different growth mechanism. We plan to identify a growth mechanism in our experiment. 
Wikipedia growth can be described by local rules such as the preferential attachment mechanism, though users can act globally on the network. 
 
- Improving the Robustness of Online Social Networks: A Simulation Approach of Network Interventions 
https://doi.org/10.3389/frobt.2020.00057 
This paper explores methods of controlling how robust an online social network is. 
They define robustness as the average coreness of each node, or how much effect removing that node would have on the system. Our end goal in the experiment is to identify coreness of different nodes (words) in the Wikipedia ecosystem.
Their model incorporates benefit and cost functions to model whether a node will remain in the network. Their analysis explores ways to keep users in the network. 
They conclude that keeping a few core nodes in the network is more effective than keeping many outer nodes in the network at improving the robustness of the network. 

### Experiment Plan

We plan to implement k-core analysis in our initial experiment to help identify small interlinked core areas on a network. 

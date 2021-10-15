# Visualizing the Growth of Social Networks
#### Maalvika Bhat, Hyunkyung Rho

### Abstract
Using a SNAP dataset, which holds a Wikipedia network of top categories with 1791489 nodes and 28511807 edges, we will represent the online encyclopedia as a directed graph. 
Additionally, we hope to identify how core certain words are to the network, which is how much the network would change if that node is removed. Resilience is the ability of the network to remain minimally affected by behavior of individual nodes. Thus, we expect to discover different "cores" from the Wikepedia network apart from philosophy (as previously explored in the class). After completing the representation of our model, we intend to conduct different analysis such as the k-core analysis or the significance of preferential attachment.

### Areas of Concern
One of the criterias for a good project asks for available data and supporting materials. However, the Wikipedia network dataset that we plan on using is a big dataset that has a high probability of taking a long time for processing. If we were to scale the dataset down by getting rid of a portion of the nodes and the connections between them, we would be losing the integrity of the results from analyzing the experiments on the Wikipedia network. Therefore, we plan on using the Facebook network dataset (which is smaller in scale compared to the Wikipedia network dataset) in case the processing takes too long. 

### Annotated Bibliography 

-A Generative Algorithm for Modeling Social Networks with Trait Spaces
- https://cdr.lib.unc.edu/concern/honors_theses/j6731806k
The algorithm in this paper is loosely based on the Barabasi-Albert algorithm for scale-free graph generation. 
However, this model includes some additional parameters that play key roles in social networks, including a means of assigning attributes to individuals in the network.
The algorithm is intuitive in its implementation and easily adaptable to a variety of situations. 
Furthermore, the algorithm exhibits structural traits present in social networks but not produced by the Barabasi-Albert model. 
This paper is the one we will model for our initial implementation -- specifically 3.1 which explores undirected Strickland graphs. 

- Social Resilience in Online Communities: the Autopsy of Friendster 
https://dl.acm.org/doi/10.1145/2512938.2512946
This paper discusses analysis of social networks using k-core analysis and measurement of resilience. Coreness is a measure that can help identify tightly interlinked groups within a network. A k-core is a maximal group of entities, all of which are connected to at least k other entities in the group. 
We plan to implement k-core analysis in our initial experiment. From incorporating the k-core analysis in our Wikipedia network, we intend to use the same interpretation as such that if an article does not have more than k linked neighbors, it "declines" due to the lack of traffic. The consequences of shutting down of an article in our Wikipedia network would be an interesting phenomenon to observe and analyze. This paper concludes that thek-core analysis enables to quantify social resilience in online social networks, utilizing the CCDF of node coreness.
 
- Preferential attachment in the growth of social networks: the internet encyclopedia Wikipedia 
https://arxiv.org/pdf/physics/0602026.pdf
The authors present an analysis of the statistical properties and growth of Wikipedia. The topological properties of this graph are in close analogy with those of the World Wide Web, but they point out that there is a very different growth mechanism. We plan to identify a growth mechanism in our experiment. Wikipedia growth can be described by local rules such as the preferential attachment mechanism, though users can act globally on the network. This paper concludes that being able to observe preferential attachment in the Wikipedia network is due to the difficulty of identifying the optimal information to refer to from a node, which results in favoring the "rich-get-richer" behavior.
 
- Improving the Robustness of Online Social Networks: A Simulation Approach of Network Interventions 
https://doi.org/10.3389/frobt.2020.00057 
This paper explores methods of controlling how robust an online social network is. They define robustness as the average coreness of each node, or how much effect removing that node would have on the system. Our end goal in the experiment is to identify coreness of different nodes (words) in the Wikipedia ecosystem. Their model incorporates benefit and cost functions to model whether a node will remain in the network. Their analysis explores ways to keep users in the network. They conclude that keeping a few core nodes in the network is more effective than keeping many outer nodes in the network at improving the robustness of the network. 

### Experiment Plan

We plan to implement k-core analysis in our initial experiment to help identify small interlinked core areas on a network. Additionally, we hope to identify a specific growth mechanism. Our final report will also inculde robustness, or the average coreness of each node. We are looking to understand how much effect removing one node would have on the Wikipedia system in its entirety. 

#### This might look like the following: 

![image](https://user-images.githubusercontent.com/42943695/135956178-7be28d2a-271f-4671-aac8-302259e1a3d1.png)
![image](https://user-images.githubusercontent.com/42943695/135956215-19eee954-1169-4363-a9cb-19e8463c47d7.png)
![image](https://user-images.githubusercontent.com/42943695/135956190-6796ebc6-929d-44a6-9b9c-ffba262a9b7d.png)
![image](https://user-images.githubusercontent.com/42943695/135956199-d2c1c30f-b044-4708-8633-9c61139cd3d8.png)
An example of the interpretation of the k-core analysis results would be for us to distinguish the nodes that still remain after the analysis versus the nodes that disappear after the analysis; this enables us to take a look at the nodes that are weakly linked to the rest of the network and also to use this to measure the coreness of our network.

### Next Steps
The immediate individual goals in front of us is to thoroughly go over the three annotated bibliography on our own first so that we start off with some level of understanding and come up with questions for discussion (e.g. what components to implement to our model). For our group goal for the first week, we aim to implement the BA model with preferential attachment with (hopefully) the Wikipedia dataset and get it working. Even better, we would have made little explorations of incorporating parts from the two other papers.
Plus, we have a task board up and running under the *Projects* bar in this repository!

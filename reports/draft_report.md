## Visualizing the Growth of Social Networks
#### Maalvika Bhat, Hyunkyung Rho

### Abstract
To understand how social networks, like Facebook, act differently than networks like Wikipedia in graph generation, we compared algorithms for both sample datasets. We implemented a method for reliable generation of random networks that model known social networks and compared them to graph generation in other networks. Our algorithm is loosely based on the Barabasi-Albert algorithm for scale-free graph generation. However, our model includes additional parameters that play key roles in social networks, including a means of assigning attributes to individuals in the network, which allows for the exploration of networks in which there is a certain degree of
diversity. We have only implemented undirected versions of the algorithm, and have examined how the algorithm compares to other networks, like Wikipedia. Additionally, we discuss extensions of the model that could further enrich its modeling capabilities. 

### Process
In this project, we began by modeling Facebook data in an undirected Strickland algorithm. 
The undirected Strickland algorithm produces an undirected graph built iteratively node by node. It requires the following parameters: 
n — the desired final size of the network.
m0 — the size of the initial seed network.
F — the desired Global F which defined the variance of the traits.
P — a skew term, which pushes the trait beta distribution left or right. P is a value between 0 and 1
and represents the mean trait of the network.
m — the number of connections each new node should make.
The steps of the algorithm are enumerated below. The logic and meaning of the steps are explained after
the model is covered.
1. a seed network of size m0 is generated via the Erdos-Renyi algorithm.
2. a new node x is added to the network repeated recursively until the network reaches size n.

Then, we repeated this experiment with Wikipedia data. Facebook is a social network, while Wikipedia is not. 
We compared the two outcomes of running the algorithm with different data sets to see how social networks and other network graphs act differently.
This was our extension of the initial experiment. 

Lastly, we performed k-core analysis on the Wikipedia dataset. Coreness is a measure that can help identify tightly interlinked groups within a network. 
A k-core is a maximal group of entities, all of which are connected to at least k other entities in the group. 

### Weaknesses of the Model 
A large part of our project was implementing a model we read about in "A Generative Algorithm for Modeling Social Networks with Trait Spaces." This meant, first, we had to make sense of dozens of equations, algorithms, implementations, and thought processes. To extend this model meant filling in gaps in scientific understanding with our own knowledge. While we tried our best to do so, there might be pieces missing in creating the most accurate and precise model possible. 
If we were to redo this project, we would try to replicate the algorithm on several different datasets to see if we could identify repeated patters between social networks and other networks. 

### Annotated Bibliography 

- A Generative Algorithm for Modeling Social Networks with Trait Spaces https://cdr.lib.unc.edu/concern/honors_theses/j6731806k
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



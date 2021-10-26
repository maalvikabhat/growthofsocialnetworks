## Graph Generation in Social Networks vs. Other Networks
#### Maalvika Bhat, Hyunkyung Rho

### Abstract
To understand how social networks like Facebook act differently than non-social networks like Wikipedia in graph generation, we generated each network using the undirected Strickland algorithm and compared them. The Strickland algorithm combines a trait weighting system from the Balding-Nichols model to preferential attachment from the Barabási-Albert model make the resulting model more realistic. 
We implemented a method for reliable generation of random networks that model known social networks and compared them to graph generation in other networks. Our algorithm is loosely based on the Barabasi-Albert algorithm for scale-free graph generation. However, our model includes additional parameters that play key roles in social networks, including a means of assigning attributes to individuals in the network, which allows for the exploration of networks in which there is a certain degree of
diversity. We have only implemented undirected versions of the algorithm, and have examined how the algorithm compares to other networks, like Wikipedia. Additionally, we discuss extensions of the model that could further enrich its modeling capabilities. 

### Motivation Behind Algorithm
The Strickland algorithm is motivated from the shortcoming that results from Erdos-Renyi, Barabasi-Albert, and Watts-Strogatz models assuming that there are no distinctions between the nodes except for the degree. To produce a model that better reflects how the nodes are in reality, the Strickland algorithm incorporates differences between the nodes when building the network by creating a continuous trait space, which is the space of possible differences between people. Here, a continuous trait space is used over a discrete trait space as it is unrealistic to categorize nodes--which would be people for the Facebook network and articles for the Wikipedia network--and to even count the different categories there may be. Each node is randomly assigned a particular F-trait which is used to determine the likelihood that some node *x* is a member of another node *y*'s community.  

### Experiment
We begin by modeling Facebook data with an undirected Strickland algorithm. The algorithm produces an undirected graph that starts with a given initial size of an Erdos-Renyi model. The algorithm then builds node by node to the base model using a combination of preferential attachment and trait weighting system.

The following parameters are required: 
n — the desired final size of the network.
m0 — the size of the initial seed network.
F — the desired Global F which defined the variance of the traits.
P — a skew term, which pushes the trait beta distribution left or right. P is a value between 0 and 1
and represents the mean trait of the network.
m — the number of connections each new node should make.

Then, we repeated this experiment with Wikipedia dataset using the undirected Strickland algorithm. The Facebook network might seem to have the very similar traits as the Wikipedia network, but they differ. Facebook is a social network, while Wikipedia is not. In context, BA model's preferential attachment is based on how popular a person or an article is. With the addition of an extra feature, F-traits, to the process of preferential attachment, we a more realistic scenario for each of the models are created. A person or an article that is heavily connected to other nodes may not have any overlapping similarities as a new node, which is the concern that the addition of F-traits takes care of. Therefore, we compared the two outcomes of running the algorithm with different data sets to see how social networks and other network graphs act differently.
This was our extension of the initial experiment. 

### Results & Interpretation


### Concerns
A large part of our project was implementing a model we read about in "A Generative Algorithm for Modeling Social Networks with Trait Spaces." This meant, first, we had to make sense of dozens of equations, algorithms, implementations, and thought processes. To extend this model meant filling in gaps in scientific understanding with our own knowledge. While we tried our best to do so, there might be pieces missing in creating the most accurate and precise model possible. As an example, the paper that outlines the Strickland algorithm mentions a variable *p*, a skew term that pushes the trait beta distribution left or right. However, the paper does not mention how they decided the p-values and when they chose to tweak their p-values in the algorithm; therefore, this part is left to our own exploration and testing. If we were to redo this project, we would try to replicate the algorithm on several different datasets to see if we could identify repeated patters between social networks and other networks. 

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


### Next Steps
We will work on debugging our code to produce the results we're hoping to see. Once our Facebook data is accurately modeled, we will replicate the algorithm using our Wikipedia data. Then, we will compare the BA graphs produced by both datasets. Additionally, we hope to perform k-core analysis on the Wikipedia dataset. This will allow us to identify tightly interlinked groups within the Wikipedia network. 

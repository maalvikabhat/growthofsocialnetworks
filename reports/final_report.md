## Graph Generation with Trait Weighting System in Social Networks vs. Non-Social Networks
#### Maalvika Bhat, Hyunkyung Rho

Link to the Colab Notebook: https://colab.research.google.com/drive/1txt6TTI7uh34hdpZmIDjNbB8YJFsKQlJ?usp=sharing

### Abstract
To understand how social networks like Facebook act differently than non-social networks like Wikipedia in graph generation, we generated each network using the undirected Strickland algorithm and compared them. The Strickland algorithm combines a trait weighting system from the Balding-Nichols model to preferential attachment from the Barabási-Albert model to make the resulting model more realistic. The addition of the trait weighting system incorporates the notion of the differences between people, and that people of similar traits are more likely to belong in the same community. This is implemented by assigning attributes to individuals in the network, which allows for the generation of the network with an extra area of diversity. Our model only contains the undirected version of the algorithm as both Facebook and Wikipedia networks do not have directionality. Additionally, we discuss extensions of the model that could further enrich its modeling capabilities. 

### Motivation Behind Algorithm
The Strickland algorithm is motivated from the shortcoming that results from Erdos-Renyi, Barabasi-Albert, and Watts-Strogatz models assuming that there are no distinctions between the nodes except for the degree. To produce a model that better reflects how the nodes are in reality, the Strickland algorithm incorporates differences between the nodes when building the network by creating a continuous trait space, which is the space of possible differences between people. Here, a continuous trait space is used over a discrete trait space as it is unrealistic to categorize nodes--which would be people for the Facebook network and articles for the Wikipedia network--and to even count the different categories there may be. Each node is randomly assigned a particular F-trait which is used to determine the likelihood that some node *x* is a member of another node *y*'s community.  

### Experiment
We begin by modeling Facebook data with an undirected Strickland algorithm. The algorithm produces an undirected graph that starts with a given initial size of an Erdos-Renyi model. The algorithm then builds node by node to the base model using a combination of preferential attachment and trait weighting system.

##### The following parameters are required: <br/>
**n** — the desired final size of the network. <br/>
**m0** — the size of the initial seed network. <br/>
**F** — the desired Global F which defined the variance of the traits. <br/>
**P** — a skew term, which pushes the trait beta distribution left or right. P is a value between 0 and 1 and represents the mean trait of the network. <br/>
**m** — the number of connections each new node should make. <br/>

When BA model's preferential attachment was purely based on the degree, the Strickland algorithm alters the significance of the degree by computing the product of the F-trait and the degree of a node. This results in different probabilities of connecting to each node, which is put together in a probability vector. The edges to be connected are then selected from the probability vector. We repeat this process until the desired network size is reached. 

Then, we replicated this experiment with Wikipedia dataset using the undirected Strickland algorithm. The Facebook network might seem to have the very similar traits as the Wikipedia network, but they differ. Facebook is a social network, while Wikipedia is not. In context, BA model's preferential attachment is based on how popular a person or an article is. With the addition of an extra feature, F-traits, to the process of preferential attachment, we a more realistic scenario for each of the models are created. A person or an article that is heavily connected to other nodes may not have any overlapping similarities as a new node, which is the concern that the addition of F-traits takes care of. Therefore, we compared the two outcomes of running the algorithm with different data sets to see how social networks and other network graphs act differently.

### Results & Interpretation
The generative algorithm, or the undirected Strickland algorithm, in *A Generative Algorithm for Modeling Social Networks with Trait Spaces* paper for modeling social networks with trait spaces is another approach of the preferential attachment in the Barabási-Albert model by incorporating a trait weighting system that was inspired from the Balding-Nichols model. As this project's baseline was a variation and an improvement of the BA model, we compare the representation of the Facebook dataset by the BA model and our  Strickland model. 

We thus compare the representation of the Wikipedia dataset by the BA model and our Strickland model as well. 

![fbpmf](https://github.com/maalvikabhat/growthofsocialnetworks/blob/main/fb_strickland_plot.png) <br/>
The above is the comparison between the actual degree distribution of a Facebook network and the Facebook network modeled with the Strickland algorithm. For both networks (Facebook and Wikipedia) modeled with the Strickland algorithm, we can see that there is a relatively even distribution of the degrees as given with the low slope of the trendline that fits through the plot. This is most likely resulting from the part of the paper that requires that each new node makes at least *m* edges to pre-existing nodes in the network. Regardless of tweaking the *f*, *p*, and the *m0* value, the degree distribution plot had a same trend, only varying in the height of the plot. This makes us assume that the parameter *m* overpowers *f*, *p*, and *m0* when generating a Strickland model.

![wikipmf](https://github.com/maalvikabhat/growthofsocialnetworks/blob/main/wiki_strickland_plot%20(1).png) <br/>
The above is the comparison between the actual degree distribution of a Wikipedia network and the Wikipedia network modeled with the Strickland algorithm. The number of degrees that each node is connected to in the Wikipedia Strickland model is small in comparison to the Facebook dataset because we ran this plot with a very small *m* value for runtime purposes.

![fbwikicomparison](https://github.com/maalvikabhat/growthofsocialnetworks/blob/main/pmf_wiki_fb%20(1).png) <br/>
The above is the degree distribution of the Facebook dataset and the Wikipedia dataset. Although the Wikipedia dataset has been shrunken for processing time and memory management, it is visible that the trend of the Wikipedia dataset still follows the Facebook dataset with the downward slope that indicates that there are a greater number of people/articles with small number of edges connected to them and a small number of people/articles with a great number of edges connected to them.

### Concerns
A large part the roadblocks of our project were: wrangling with the insanely large Wikipedia dataset, and implementing the preferential attachment with the trait weighting system. This meant that first, we had to create a data processor that would cut down the size of the Wikipedia dataset so that it can be processed in a reasonable time and not clutter Colab's RAM while maintaining the integrity of the network. We slimmed the Wikipedia dataset to have 7425 nodes, 12000 edges from the original dataset's size of 1791489 nodes and 28511807 edges.

Second, we had to make sense of the equations used and the motivation for deciding to use them. To extend this model meant filling in gaps in scientific understanding with our knowledge. One example of this area was the usage of the beta distribution to assign F-traits, and the decision behind choosing a beta distribution over other functions that randomly generates a value between 0 and 1. Another example is that the paper mentions a variable *p*, a skew term that pushes the trait beta distribution left or right. However, the paper does not mention how they decided the p-values and when they chose to tweak their p-values in the algorithm; therefore, this part is left to our exploration and testing. While we tried our best to replicate the model, there are incongruent pieces from our model and the model described in the paper. 

### Annotated Bibliography 

- *A Generative Algorithm for Modeling Social Networks with Trait Spaces* <br/>
https://cdr.lib.unc.edu/concern/honors_theses/j6731806k <br/>
The algorithm in this paper is loosely based on the Barabasi-Albert algorithm for scale-free graph generation. 
However, this model includes some additional parameters that play key roles in social networks, including a means of assigning attributes to individuals in the network.
The algorithm is intuitive in its implementation and easily adaptable to a variety of situations. 
Furthermore, the algorithm exhibits structural traits present in social networks but not produced by the Barabasi-Albert model. 
This paper is the one we will model for our initial implementation -- specifically 3.1 which explores undirected Strickland graphs. 

- *Social Resilience in Online Communities: the Autopsy of Friendster* <br/>
https://dl.acm.org/doi/10.1145/2512938.2512946 <br/>
This paper discusses analysis of social networks using k-core analysis and measurement of resilience. Coreness is a measure that can help identify tightly interlinked groups within a network. A k-core is a maximal group of entities, all of which are connected to at least k other entities in the group. 
We plan to implement k-core analysis in our initial experiment. From incorporating the k-core analysis in our Wikipedia network, we intend to use the same interpretation as such that if an article does not have more than k linked neighbors, it "declines" due to the lack of traffic. The consequences of shutting down of an article in our Wikipedia network would be an interesting phenomenon to observe and analyze. This paper concludes that thek-core analysis enables to quantify social resilience in online social networks, utilizing the CCDF of node coreness.
 
- *Preferential attachment in the growth of social networks: the internet encyclopedia Wikipedia* <br/>
https://arxiv.org/pdf/physics/0602026.pdf <br/>
The authors present an analysis of the statistical properties and growth of Wikipedia. The topological properties of this graph are in close analogy with those of the World Wide Web, but they point out that there is a very different growth mechanism. We plan to identify a growth mechanism in our experiment. Wikipedia growth can be described by local rules such as the preferential attachment mechanism, though users can act globally on the network. This paper concludes that being able to observe preferential attachment in the Wikipedia network is due to the difficulty of identifying the optimal information to refer to from a node, which results in favoring the "rich-get-richer" behavior.
 
- *Improving the Robustness of Online Social Networks: A Simulation Approach of Network Interventions* <br/>
https://doi.org/10.3389/frobt.2020.00057 <br/>
This paper explores methods of controlling how robust an online social network is. They define robustness as the average coreness of each node, or how much effect removing that node would have on the system. Our end goal in the experiment is to identify coreness of different nodes (words) in the Wikipedia ecosystem. Their model incorporates benefit and cost functions to model whether a node will remain in the network. Their analysis explores ways to keep users in the network. They conclude that keeping a few core nodes in the network is more effective than keeping many outer nodes in the network at improving the robustness of the network. 


### Next Steps
One specific next step that we want to take is exploring the behavior of the beta distribution when the distribution's two parameters, alpha and beta, equal 0. According to the paper, the model generated from the Strickland algorithm should behave just like a BA model when the output from the beta distribution is 0. However, we encountered an anomaly in the behavior of the model as the algorithm failed to execute the beta distribution when alpha and/or beta was 0. Due to time constraints, we modify 0 with an extremely small nonzero value. If given more time, we desire to explore this anomaly.

#### Question:  What is your understanding of the experiment the team is replicating?  What question does it answer?  How clear is the team's explanation?
It seems like that the team is taking another take at the traditional reaction-diffusion model by varying the shape of each cell in the grid from a square to a hexagon.
Therefore, the team looks like they are intending to answer the effect of different cell shapes of a grid on a reaction-diffusion model. Their explanation was very clear and the pictures
substituted in the experiments section really helped the understanding. One part that I am still left confused is the definition of "tokens" and what they are doing in the model.

#### Methodology: Do you understand the methodology?  Does it make sense for the question?  Are there limitations you see that the team did not address?
The upper-level view of the methodology makes a lot of sense! It seems like the team put in good effort to try to deliver it as clear as possible. On the lower-level view, I'm wondering
if the team implemented the 6-directional movement by limiting the degree of freedom through not taking 2 neighbors into account (is the team implementing the paper in a regular square grid-cell
and performing the change in the grid-cell shape by changing the number of neighbors?). If so, how did you determine which 2 neighbors to disregard and would this selection process somehow affect
your end result?

#### Results: Do you understand what the results are (not yet considering their interpretation)?  If they are presented graphically, are the visualizations effective?  Do all figures have labels on the axes and captions?
What the results are seem very clear without considering what implementation was taken to produce those results. It would be nice if there were more information in the images themselves, 
such as labeling the axis or a caption (so that the images could be more self-standing). 

### Interpretation: Does the draft report interpret the results as an answer to the motivating question?  Does the argument hold water?
It is exciting to see that the team got some implementation working and produced some meaningful graphical representation of their result. It would be great if the team included an
analysis on the images (the diffusion in 4 directions and in 6 directions): maybe on why you think the 6-direction diffusion image is behaving like it is, what the noticeable difference
between the 4-directional one and the 6-directional one is, etc. It's awesome that the team got to confirm that the shape of the grid cell does have an effect on the diffusion behavior,
but I'm unsure of what the effect is. 

### Replication: Are the results in the report consistent with the results from the original paper?  If so, how did the authors demonstrate that consistency?  Is it quantitative or qualitative?
From the report, the team has varying results for the models and are in the stage of modification. So I believe that this is not the adaquate stage to discuss whether the team's
results are consistent with the results from the original paper, but I can definitely see that the authors are confident in the way they are heading with the implementation. But
if I were to discuss about their results, it is rather more qualitative as of now since they are graphing their result.


### Extension: Does the report explain an extension to the original experiment clearly?  Can it answer an interesting question that the original experiment did not answer?
I think I'm confused on how the spreading of tokens to 8 different directions is different from the traditional reaction-diffusion model. Assuming that it is different, the report 
clearly states the extension the team is planning to take and I believe that it is definitely an interesting question to explore different grid-cell shapes with varying numbers of eges.

### Progress: Is the team roughly where they should be at this point, with a replication that is substantially complete and an extension that is clearly defined and either complete or nearly so?
It seems like the team is at a great standpoint currently, with a working baseline implementation that produces a result! Thus, the team seems very confident and clear in their understanding of the 
measures taken in the paper (and also the places where they have to figure things out).

### Presentation: Is the report written in clear, concise, correct language?  Is it consistent with the audience and goals of the report?  Does it violate any of the recommendations in my style guideLinks to an external site.?
The report was written very clearly and was easy to follow through. The underlying expectation of the audience's knowledge level also seemed consistent throughout. 

### Mechanics: Is the report in the right directory with the right file name?  Is it formatted professionally in Markdown?  Does it include a meaningful title and the full names of the authors?  Is the bibliography in an acceptable style? 
The report correctly follows the format instructions and is labeled with the right file name. Thus, the title of the report succinctly expresses what the team is going over in their exploration.
After going over the report and then looking at the report title, it made a lot of sense to me how the team chose this title to their report.

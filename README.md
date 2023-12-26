# solve_hub design intent

1. combine common problem solving methodologies into one representation
2. use user-defined tags to serve as a type of coordinate system of each phenomena
3. use command pattern to create a versioned diagram

## Problem Solving Model

In manufacturing there are a few key methods for determining what the team must change to fix a problem.

### Existing Methodologies

1. The 5 why's method -> consists of observing a phenomena, and determining the cause of that phenomena, then repeating 5 times
2. The Root Cause Tree -> consitsts of observing a phenomena, determining possible causes for the phenomena, then repeating for each possbile cause
3. Potential Failure Modes and Effects Analysis -> consists of determining all possible failure modes of a system then using the reverse of the FTA to determine possible impacts of each failure mode
4. Fishbone Diagram - > similar to the Root Cause Tree but the first set of nodes is the (now 6) 4Ms - and the rest is just a RCA

There are a few phenomena that emerge when teams try to use these tools

### Observed Issues 

1. Custom and sometimes difficult to use custom implementations of these problem solving methodologies
2. Difficulty reporting progress on the problem solving activities
3. Teams having difficulty agreeing on which 4Ms to select (this is a source of inter-deparmental conflict)
4. A lack of a clearly useful body of knowledge generated as a result of the efforts
5. A lack of medium-term results due to high spin-up overhead
6. Difficulty switching between potential-effects analyisis and potential-cause analysis in the software when this is what the brain wants to do
7. Difficulty tracking evidence for each hypothesis

Anything that can be observed is a phenomena. Any guess about the meaning of a phenomena is a hypothesis.
Typically, we connect any two phenomena with a hypotheses.
These two elements are common to all the different problem solving methodologies

### Fundamentals

1. The **5 Why's** Methodology consists of a ```hypothesis-phenomena``` hybrid node which is connected to a single next hypothesis, and another
2. The **RCA Tree** Consists of ```phenomena``` connected by ```hypotheses``` where the hypotheses are merely causal - the key tree is the tree where the all the phenomena in the specific branch of the tree are true at the same time
3. The **Potential Failure Modes and Effects Analysis** Methodology lists out ```phenomena``` and then generates ```hypotheses``` about what ```phenomena``` may occur as a result
4. The **Fishbone Diagram** first sets up a categorical framework for ```phenomena``` where they can be one of the 6 ```categories``` in the 4M that represent the different types of elements of a process. It is unclear whether this ```categorizatization``` applies to the first level ```phenomena``` or to the lowest level (primary ```phenomena```)

### Data Model

So then we need ```hypotheses``` to contain evidence about the connection between ```phenomena``` and categories for each ```phenomena``` to help us ensure we investigating all elements of the process where we observe the ```phenomena```
Instead of using a simple set of categories, the 4M, we will provide the user the ability to mix and match tags and also create a data model of the tags.
The data model is to allow us to determine possible combinations of tags that must exist.

1. As users define tags, we can automatically adjust the scope of the diagram so that related items are all that is dispayed
2. We can estimate the teams progress based on the phenomena they have described from the set of possible tags

# development plan

1. Review and refine the idea a few times 2023-01-10
2. Build some basic dom interactions to remove and add elements 2023-01-30
3. Build key features 2023-02-28
4. Get feedback from other engineers on the data model 2023-03-15
5. Build in refinements 2023-03-30
6. Turn into a loadable web application 2023-04-30
7. Serve for free to the web 2023-05-30
8. Determine a business model to support further development 2023-06-30


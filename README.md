## Simulating spreading of Coronavirus in a town with Python

This post attepmts to model the spreading of novel SARS-CoV-2 into a small Romanian town (Slatina, Olt County) by appling different [comportamental model in epidemiology.](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology)

Due to [small world network](https://en.wikipedia.org/wiki/Small-world_network) effect, where a signfiant part of network elements are neighbors of one another, spreading of a disease can happen faster in small to medium communites. This post is entirely based on [network-based diffusion analysis](https://en.wikipedia.org/wiki/Network-based_diffusion_analysis) which is a quantifier for transmision / diffusion of a behaviour into a social network.  

The analysis was made using Python and open source libaries (detailed below). **The post is aimed to show benefits of social distancing (from a statistical point of view)**

### !!Disclaimer!! This is not a medical article. Analysis is made entirely using statistical and probabilistic modelling and may not reflect the truly evolution of the disease. 

# Fetching the network

In order to obatain the network topology I used [OpenStreetMap](https://www.openstreetmap.org/#map=7/45.996/24.981) together with opensource library [osmnx](https://github.com/gboeing/osmnx). 

<img src="slatinaGraph.PNG" class="img-responsive" alt="">

In this topology each edge represent a road and each node is represented by either an intersection ar a cul-de-sac. Information difussion is modelled by assigning different weights to each node by it's importance (with higher weights asigned to more central nodes - e.g. trasnportation hubs, city center, markets). 

After this operation, the output will be a [networkx object](https://networkx.github.io/documentation/stable/tutorial.html#creating-a-graph) which can be further converted into Shapefile or GraphML files to implement other GIS analysis.

# Modelling the transmision

For network diffusion analysis [NDlib opensource library](https://ndlib.readthedocs.io/en/latest/overview.html) will be used. 

For modelling the disease diffusion I will use SEIR model. As a short introduction, SEIR model is a compartmental model which show how a disease spreads through a population. It’s an acronym for Susceptible, Exposed, Infected, Recovered. This model is extending the SIR model by adding "Exposed" state as being a period during which the individual has been infected but is not yet infectious themselves

<img src="SEIR.png" class="img-responsive" alt="">

SEIR model was succesfully aplied in modelling transmision of SARS virus during 2003 epidemic. 

### SEIR model:
<img src="model.svg">

Luckily, paramteres for SEIR model were already estimated in a [recent study by Hellewell et al. 2020](https://www.thelancet.com/journals/langlo/article/PIIS2214-109X(20)30074-7/fulltext):
  * α = 0.2 (Median incubation period is 5 days)
  * R0 = 3.5
  * γ = 0.5
  * β = 1.75

# Running simulation

<p float="left">
  <img src="SEIR without Social Distancing.PNG" width="400" />
  <img src="SEIR prevalence withou Social Distancing.PNG" width="400" /> 
</p>


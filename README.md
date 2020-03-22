## Simulating spreading of Coronavirus in a town with Python

This post attepmts to model the spreading of novel SARS-CoV-2 into a small Romanian town (Slatina, Olt County) by appling different [comportamental model in epidemiology.](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology)

Due to [small world network](https://en.wikipedia.org/wiki/Small-world_network) effect, where a signfiant part of network elements are neighbors of one another, spreading of a disease can happen faster in small to medium communites. This post is entirely based on [network-based diffusion analysis](https://en.wikipedia.org/wiki/Network-based_diffusion_analysis) which is a quantifier for transmision / diffusion of a behaviour into a social network.  

The analysis was made using Python and open source libaries (detailed below)

### !!Disclaimer!! This is not a medical article. Analysis is made entirely using statistical and probabilistic modelling and may not reflect the truly evolution of the disease.

# Fetching the network

In order to obatain the network topology I used [OpenStreetMap](https://www.openstreetmap.org/#map=7/45.996/24.981) together with opensource library [osmnx](https://github.com/gboeing/osmnx). 

<img src="slatinaGraph.PNG" class="img-responsive" alt="">

In this topologiy each edge represent a road and each node is represented by either an intersection ar a cul-de-sac. Information difussion is modelled by assigning different weights to each node by it's importance (with higher weights asigned to more central nodes - e.g. trasnportation hubs, city center, markets)

# Modelling the transmision

For modelling the disease diffusion I will use SEIR model. As a short introductio, SEIR model is a compartmental model for modeling how a disease spreads through a population. It’s an acronym for Susceptible, Exposed, Infected, Recovered. This model is extending the SIR model by adding "Exposed" state as being a period during which the individual has been infected but is not yet infectious themselves

<img src="https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#/media/File:SEIR.PNG" class="img-responsive" alt="">

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/bTudose/bTudose.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

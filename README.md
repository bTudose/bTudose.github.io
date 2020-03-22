## Simulating spreading of Coronavirus in a town with Python

This post attepmts to model the spreading of novel SARS-CoV-2 into a small Romanian town (Slatina, Olt County) by appling diffrent [Comportamental model in epidemiology.](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology)

Due to [small world network](https://en.wikipedia.org/wiki/Small-world_network) effect, where a signfiant part of network elements are neighbors of one another, spreading of a disease can happen faster in small to medium communites. This post is entirely based on [network-based diffusion analysis](https://en.wikipedia.org/wiki/Network-based_diffusion_analysis) which is a quintifier for transmision / diffusion of a behaviour into a social network.  

The analysis was made using Python and open source libaries (detailed below)

### !!Disclaimer!! This is not a medical article. Analysis is made entirely using statisticall modelling and may not reflect the truly evolution of the disease

# Fetching the network

In order to obatain the network topology I used [OpenStreetMap](https://www.openstreetmap.org/#map=7/45.996/24.981) together with opensource library [osmnx](https://github.com/gboeing/osmnx).


<img src="slatinaGraph.PNG" class="img-responsive" alt="">


Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

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

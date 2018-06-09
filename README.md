<head>
    <style type="text/css">
       a:link {color: blue;}      /* unvisited link */
       a:visited {color: blue;}   /* visited link */
       a:hover {color: blue;}     /* mouse over link */
       a:active {color: blue;}    /* selected link */
    </style>
</head>

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

### Purpose

The goal of this project is to improve upon the self-assembly algorithm presented by Rubenstein, Cornejo, and Nagpal in the paper <i>Programmable self-assembly in a thousand-robot swarm</i>. Their algorithm "guarantees that a large group of robots, with limited capabilities and local communication, can cooperatively assemble into any 1-connected user-specified shape (with some restrictions)." Informally, this means it works on shapes having no "holes" or "cutouts". My goal in particular is to extend their algorithm to work on any 1-connected shape in general, including those having holes or cutouts.

### Original Algorithm

It is assumed that each agent has the ability to communicate with and estimate the distances to other agents within a given radius, "neighbors." Thus, each agent can
1. move along an edge (by maintaining fixed distance to the center of the nearest neighbor),
2. estimate its own coordinates (as those which minimize the discrepancy between the observed distances to neighbors and the distances calculated using neighbors' estimations of their own coordinates), and
3. estimate its distance from the source (the source has gradient value zero, and each agent generates a gradient value as one more than the minimum of the gradient values of its neighbors).

$$\int \frac{1}{2} dx$$

Where it fails in non

### Extended Algorithm

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

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/jpskycak/Programmable-Self-Assembly/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

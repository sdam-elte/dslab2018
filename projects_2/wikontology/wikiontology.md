# Ontology based on wikipedia

In this project is based on the work of Suchanek at al

- Link to the Suchanek et al. paper: [www](https://www.sciencedirect.com/science/article/pii/S1570826808000437) 

### Introduction 

Wikipedia is a large and growing knowledge database, where information is collected, 
reviewed and improved by several contributors from around the world. 
All concepts (words, topics) in wikipedia are labeled with a special tag: one or more categories.
These categories are orgranized into a hierarchical relationship network: there are links
from more general concepts to more special ones (e.g. all dogs are vertebral animals, therefore, there is
a directed path from vertebral animals to dogs). But wikipedia is constructed by several independent 
contributors, therefore the conceptual hierarchy is correct only locally. On a large scale (e.g. more than
6 levels in the English wikipedia) editors cannot guarantie the consistency of this hierarchy:
due to some false contributions there are loops in the category tree. In this project you can try
to find such inconsistency and give a meaningful resolution for them.

### Tasks

#### 1. Data exploration 
Select an appropriate edition of wikipedia, which fits to your available computational resources.
Extract the category tree from this wikipedia.

#### 2. Explore the network of categories and related pages
Find directed loops in the category network! Identify related articles to the categories, participating
in a loop, and propose meaningful solution to break the loops and creating a real ontologycal Directed
Acyclic Graph of the wikipedia categories! Try to find similarities between the category networks of 
different laguages!

#### 3. Dataset

Wikipedia dumps are awailable for download or online evaluation at the wikipedia archives.

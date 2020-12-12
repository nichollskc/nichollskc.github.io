---
permalink: /other/
title: "Other projects"
---

I enjoy finding ways to use programming and statistics outside of research.

## Learning Haskell

I've been following [this course](https://www.seas.upenn.edu/~cis194/fall16/) on Haskell, which is good fun. I'm working on a rubik's cube solver, as a nice project to force me to really understand functional programming.

## Cool compiler

I've often wondered how compilers actually work, and found [this course]( http://openclassroom.stanford.edu/MainFolder/CoursePage.php?course=Compilers) really interesting as it encourages you to write a compiler for a language called '*Cool*'. Fun fact about Cool: there are more compilers written for it than programs written for it to compile, since it was designed as a toy language for people to write compilers for. As with many things, it's not until you try and actually write the code that you realise how much you didn't understand.

I was going to try and write a compiler for heraldry, since heraldry essentially has its own grammar, but one [already exists](https://drawshield.net/).

Compilers and grammar have some interesting applications in computational biology, such as representations for molecules. A valid molecule can be produced by a series of steps, starting from the empty molecule and using rules such as 'a hydrogen can be replaced by a carbon attached to 3 hydrogens'. This is called the [Molecular Hypergraph Grammar, Kajino 2019](http://proceedings.mlr.press/v97/kajino19a/kajino19a.pdf)

## NFL prediction

To combine my love of statistics and the NFL ([Skol!](https://www.vikings.com/)) I want to build up a repetoire of predictors capable of aiding selection of an NFL fantasy team. I'm hoping to include:

* A simple baseline e.g. just using last week's performance as a prediciton of this week's performance
* Using constructed features with a simple predictor
* Message passing in a graphical model to accurately predict e.g. run offense or pass defense of each team

## Video construction

My fiance writes narrative poetry and we are working on a video format to help them reach a broader audience. I've written a snakemake pipeline to write the text into slides that are then compiled along with public domain artwork into full videos. I also maintain the website for that project.

## Visualisation for Gloomhaven

Gloomhaven is a 'choose your own adventure' type board game, where players play through scenarios and make decisions about the course they take through the game. To be able to quickly visualise the route taken through the game so far, and pick out good scenarios to complete next, I wrote a quick tool using python's graphviz package to make a pdf using dot that shows the links between the scenarios.


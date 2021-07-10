# Week 1. Introduction and Background Concepts

## Module 1. Objectives and Background

### What is a model?

A model is a representation of reality or part of reality, but not of the full system. 

- Simplified abstration of reality (or part of it, but never the full system) allowing us to better describe it and understand it;
- Ans abstraction in which only the essential ingredients are retained, according to the question we ask about the question;
- It is the representation of a phenomena in a mathematical or computer-based language;

## Module 2. Modelling and Simulation

### Why do we need a model?

- Describe, classify, understand, predict and control some representation of reality

### Levels of Reality

Whenever we are dong modelling, we need to take into consideration a certain level of reality in a sense that according to a scale at which you want to describe a given process. 

You should adapt your model level to the question and the scale it to which you want to answer your problem. 

It is not always easy to identify these important ingredients and to indentify hoe these ingredients mutually interact. That is whay domain knowledge is important: you need it to understand the relationships between the main ingredients of your model. 

-------

## Module 3. Modelling Space and Time

Natural processes occur in space and evolve over time.

### Time Evolution

To capture the temporal dimensions in a model, there are several ways:
- Time takes any real values. Only mathematical approaches can deal with this through differentcial equations);
- Otherwise, the duration of the process is broken up in small time intervals ``\delta_t`` and one describes the state of the system at ech of these **time-steps** ``t_0 = 0, t_1 = \delta_t, ..., t_n = n \delta_t...``
- The time is discretised, but the process is followed continuously iver the duration;
- Alternatively, we can only focus on the interesting moments of a process;
- The time ``t`` at which an event occurs can be any real value
- Time is not discretised by the evolution of the system is broken up according to events
- This is called *Discrete-Event Simulation (DES)* approach.


### Modeling Space: Euclidean Approach

To include the spatial dimensions in a model, there are also different ways.

- One can take the point of view of an observer who is sit at a fixed position ``\bar{x}`` in space and records what he sees;
- **Euclidean-Approach:** attach a property of the system at each spatial location;
- Space can be continuous (mathematical models) or discretised in cells, forming a mesh covering the region of interest;

### Modeling Space: Lagrangian Approach

Alternatively, one can give the position of all the ojects of interest, as a function of time;

### Beyond the Physical Space: Complex Networks

In many systems, it is not so much the exact spatial positions of the components of a system that matters. It is rather whether these components see each other or can interact. These approaches are usualy modelled in a **graph**. 

- Graph topology imposes a rich spatial structure which constraints the dynamics;
- Many quantities characterise the graph topology and can be related to some global properties of the system: degree distribution, clustering coefficient, centrality measures, assortativity, etc.

## Module 5. Monte Carlo Methods I

### Background

The goal of Monte Carlo methods is the sampling of a process in order to determine some statistical properties;

For instance, we toss a coin 4 times. What is the probability to obtain 3 tails and 1 head?

Mathematics gives us the solution

<img src="https://render.githubusercontent.com/render/math?math=P(3 head)=\begin{pmatrix}
        4\\
        3
    \end{pmatrix}
    \left(\frac{1}{2}\right)^3\left(1-\frac{1}{2}\right)^1=\frac{1}{4}">

But we could also do a simmulation:
```python
from random import randint

success=0

attempts=10000
for i in range(attempts):
   if randint(0,1) + randint(0,1)+randint(0,1)+randint(0,1) == 3:
      success+=1
   
print("Number of attempts= ", attempts)
print("Number of success= ", success)
```





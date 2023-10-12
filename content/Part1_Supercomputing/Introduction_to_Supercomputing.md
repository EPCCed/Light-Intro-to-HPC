<!-- Need to link these sections into later sections -->
<!-- Would like this introduction to be an overview of what is to come. -->
<!-- Also, how do I make it less boring and wordy? -->

# Introduction to Supercomputing

<!-- After completing, reword and check this...  -->
In this part you will be introduced to the key principles of supercomputing: 
* What is a supercomputer? 
* Why do we need them? 
* What do they do? 

To begin, let's watch this UKRI video where Prof. Mark Parsons, Director of EPCC, gives an overview of why high performance computing is an important aspect of modern scientific research. 

```{raw} html
<iframe width="700" height="400" src="https://www.youtube.com/embed/NEgbVNIo560" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

This video shows you what a real supercomputer might look like and highlights some of the complexities required to support such systems. Later on in the course, we will explain the different hardware components of a supercomputer and what makes them different to general-purpose computers.

<!-- Can I format this so it pops out like a note? -->
```{note}

The term "High Performance Computing" or "HPC" is used commonly throughout the video and this course. In the field of supercomputing, HPC is a general term that includes all the activities and components associated with supercomputers, including aspects such as software and data storage as well as the bare supercomputer hardware.

```


```{figure} ./images/large_hero_5149d40f-0a9b-42af-a930-413d00bc1c6c.jpg
© iStock.com/shironosov
```

## What is a supercomputer? 

A supercomputer is a high performance computing (HPC) system, essentially a computer with very high-level computational capabilities in comparison to a general-purpose computer such as a personal desktop or laptop. Throughout the history of supercomputing, the definition of a supercomputer has been a moving target - today’s laptop would have been a supercomputer only a couple of decades ago! But, no matter how fast today’s general-purpose computers are, there will always be a need for more powerful machines. 


## Why do we need supercomputers? 

<!-- Maybe want to reword this... -->
Over recent decades, computers continue to become larger and more powerful. But, why do we need computers with such high levels of computational power? Why do we need to keep pushing for higher performance computing? 

First, let's look at what these supercomputers are actually doing. 

### The third pillar of science

To do science in the real world we often have to build complicated instruments for each experiment: vast telescopes for astronomers to look deep into space, powerful particle accelerators so physicists can smash atoms together at almost the speed of light, enormous wind tunnels where engineers can study how an aeroplane wing will operate in flight.

However, some problems are actually too large, too distant or too dangerous to study directly: we cannot experiment on the earth’s weather to study climate change, we cannot travel thousands of light years into space to watch two galaxies collide, and we cannot dive into the centre of the sun to measure the nuclear reactions that generate its enormous heat. 

Instead, scientists can develop computer simulations to perform experiments on the real world in a virtual environment on a computer. Compared to disciplines such as chemistry, biology and physics the study of computer science is a relatively new area of research which has been around for a matter of decades rather than centuries. This new area, which many view as a third pillar of science extending the two traditional approaches of theory and experiment, is called **computational science**.

<!-- Can I format this so it pops out like a note? -->
```{note}

It’s important to be clear about the difference between computational science and computer science. Computer science is the scientific study of computers: it is through the work of computer scientists that we have the hardware and software required to build and operate today’s supercomputers. In computational science, however, we use these supercomputers to run computer simulations and make predictions about the real world. 

```

It is important to understand that large-scale computer simulation has applications in industry, applied engineering and commerce as well as academia. Modern cars and aeroplanes are designed and tested almost entirely by computer before they are ever constructed. A new car must pass crash safety tests before going to market: destructive testing of a new car is an expensive process in itself, but not nearly as expensive as having to redesign it should it fail the test. Computer simulation enables us to design new products that are much more likely to work correctly the very first time they are built.

### Examples 

<!-- Include some ARCHER2 Image Competition entries here -->

```{figure} ./images/large_hero_e0df48e4-9b4d-422c-a18f-d7898b9578d8.jpg

Computer simulation covering multiple physical phenomena and machine learning algorithms can predict how dinosaurs might have moved. The laws of physics apply for extinct animals exactly as they do for living ones.

© 2016 ARCHER image competition
```

## How do supercomputers work? 

<!-- Need an intro sentance, maybe based on the examples? -->
<!-- How do they work? How are they faster than a general-purpose computer?  -->


### Number crunching

The main application for supercomputers is to perform large-scale numerical computations. Let's look at some simple calculations: 

``` bash
123 + 765 = 888

or

1542.38 x 2643.56 = 4077374.07
```

To solve these equations, you don’t need a supercomputer, in fact you don’t even need a personal computer as pencil-and-paper or a simple calculator can do the job. 

What if you needed to solve 1,000 of these calculations? It would take a very long time when using pencil-and-paper, instead you might want to use a general-purpose computer to speed things up. 

What if you wanted to predict tomorrow's weather? Weather-forecasting simulations are fundamentally based on simple numerical calculations that could each be done on a calculator. However, the sheer size of these computations and the levels of accuracy required means that almost unimaginably large numbers of individual calculations are needed to do the job. To produce an accurate weather forecast, the total number of calculations required is measured in the quintillions, where a quintillion is one with 18 zeroes after it: 1,000,000,000,000,000,000!

Computations like this could take several days, weeks or years to finish. Do you want to wait while you can’t do anything else because the computation uses up all the resources of your computer? Are you prepared to wait for years before being able to collect all the results? Probably not, especially if the result you’re after is tomorrow’s weather. This is where supercomputers come into their own, finishing a job within a few hours or days when it would take many years on a general-purpose computer.


### The key to performance: Parallelism

In order to utilise their high performance computing capabilities and speed-up calculations, supercomputers use parallel computing. Performing computations in parallel means carrying out many calculations simultaneously. It is like having thousands of general-purpose computers all working for you on the same problem at the same time. This is in fact an excellent analogy for how modern supercomputers work - you will learn more about the details of how it is done later in the course.

<!-- Need to add something to finish, maybe an image? -->

<!-- © SURFsara

## Introducing Wee Archie

```{raw} html

<iframe id="kaltura_player" width="700" height="400" src="https://cdnapisec.kaltura.com/p/2010292/sp/201029200/embedIframeJs/uiconf_id/32599141/partner_id/2010292?iframeembed=true&playerId=kaltura_player&entry_id=1_vrq8zch9&flashvars[streamerType]=auto&amp;flashvars[localizationCode]=en&amp;flashvars[leadWithHTML5]=true&amp;flashvars[sideBarContainer.plugin]=true&amp;flashvars[sideBarContainer.position]=left&amp;flashvars[sideBarContainer.clickToClose]=true&amp;flashvars[chapters.plugin]=true&amp;flashvars[chapters.layout]=vertical&amp;flashvars[chapters.thumbnailRotator]=false&amp;flashvars[streamSelector.plugin]=true&amp;flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&amp;flashvars[dualScreen.plugin]=true&amp;flashvars[Kaltura.addCrossoriginToIframe]=true&amp;&wid=1_jh4xeojf" width="400" height="285" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" sandbox="allow-downloads allow-forms allow-same-origin allow-scripts allow-top-navigation allow-pointer-lock allow-popups allow-modals allow-orientation-lock allow-popups-to-escape-sandbox allow-presentation allow-top-navigation-by-user-activation" frameborder="0" title="Introducing_Wee_Archie_hd"></iframe>

```


```{solution} Transcript
0:31 - So ARCHER is the UK National Supercomputing Service that we house here in Edinburgh as part of the University. And it’s funded by the UK Research Councils. And it can do many, many calculations per second. Actually, if you took all the people on the planet, then it would be the equivalent of all these people doing many, many, many calculations per second.

1:17 - It’s absolutely crucially important for simulation, things like simulation of weather, simulation of the cosmology, things like cancer analysis, cancer research, all sorts of different applications that maybe you wouldn’t have foreseen.

1:47 - There’s a real keen push to encourage the next generation of scientists to get into science, and to get into computing in general.
```

In your mind, you probably already have an image of a supercomputer as a massive black box. Well, they usually are just that - dull looking cabinets connected by a multitude of cables. To make things more interesting, we introduce Wee ARCHIE!

Wee ARCHIE is a suitcase-sized supercomputer designed and built to explain what a supercomputer is.


```{figure} ./images/181107_ARCHER_30.jpg
```

We will return to Wee ARCHIE next week and use it, and its big brother ARCHER, to explain the hardware details of supercomputers.

You can find instructions on how to configure your very own Raspberry Pi cluster [here](https://epcced.github.io/wee_archlet/). -->

---

<!-- ## Terminology Recap

```{questions} Question 1
The term HPC stands for ?
```

```{solution}
High Performance Computing
```

```{questions} Question 1
Performing computations in _____
means carrying out many calculations simultaneously.
```

```{solution}
Parallel
```


```{questions} Question 3
The process of running a virtual experiment is called?
```

```{solution}
Computer simulation
```

```{questions} Question 4
The term number-crunching refers to large-scale ____ ____.
```

```{solution}
Numerical simulations
```

```{questions} Question 5
The typical power consumption of a supercomputer is in the order of several
____.
```

```{solution}
1) Megawatts
``` -->
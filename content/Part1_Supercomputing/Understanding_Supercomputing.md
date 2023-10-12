# Understanding Supercomputing 
<!-- This is a long part, might want to split this info up into multiple parts -->
<!-- Add a 'test' at the end? -->

The first supercomputers were introduced in the 1960s and have become invaluable for modern scientific research. The field of supercomputing has been accelerating ever since: the fastest supercomputer today is over 300 billion times faster than the first supercomputer. Later, we will discuss current trends and introduce a concept called Moore's Law. First, in order to discuss the history and evolution of supercomputers, we need to introduce a few key concepts. 
<!-- 3 MFlop/s vs 1 ExaFlop/s = 1,000,000,000,000,000,000/3,000,000 = 333,333,333,333 -->
<!-- Can we include a picture of an actual CPU? -->


## From laptops to supercomputers
<!-- Where do we intro memory? -->
It may surprise you to learn that supercomputers are built using the same basic elements that you normally find in your laptop: processors, memory and disk. The difference is largely a matter of scale. 

Let's start by looking at the most essential component of any computer: the **processor**. The processor, also commonly referred to as the CPU or Central Processing Unit, can be considered the brain of a computer as it carries out the instructions of a computer program. The slightly confusing thing is that a modern CPU actually contains several independent 'brains'; it is a collection of several separate processing units. Each independent processing unit is called a CPU-core or just core.

A modern domestic device (e.g. a laptop, mobile phone or tablet) will usually have a few CPU-cores (around 6 or 8), while a supercomputer has tens or hundreds of thousands of CPU-cores. This is really where a supercomputer get it's power from: many CPU-cores working together at the same time, working in **parallel**. Conversely, the mode of operation you are familiar with from everyday computing, in which a single CPU-core is doing a single computation, is called serial computing.

To give an example of scale: as of 2023 the UK's national supercomputer, [ARCHER2](https://www.archer2.ac.uk/), has 750,080 CPU-cores! That's 750,080 'brains' which can work together to solve a problem! 


### From gaming to supercomputers 

Are you surprised that supercomputers use the same basic elements as your mobile phone or laptop? The reason is quite simple: the cost of developing new hardware is measured in billions of euros, and the market for consumer products is vastly larger than the market for supercomputing, so the most advanced technology you can find is actually what you find in general-purpose computers.

For example, let's look at GPUs: the Graphics Processing Unit (GPU) is a special-purpose processor which can be used as an accelerator to increase the power of a computer. In contrast to a CPU, which has a small number of powerful general-purpose cores, a GPU has many specialised cores. Many of today's most powerful supercomputers use GPUs to accelerate their performance. We will discuss this in more detail later in the course. 

```{figure} ./images/large_hero_8408f33c-87f5-4061-aec7-42ef976e83fd.webp

A typical CPU has a small number of powerful, general-purpose cores; a GPU has many more specialised cores. © NVIDIA

```

You may have heard of GPUs because they are commonly used to improve computer graphics for gaming at home. The global video game industry is a billion-dollar business and has been for many years. The boom of this industry has accelerated the development of GPUs and vastly contributed to accelerating our supercomputing power at the same time.  


## Understanding performance 

So far, we have been discussing how supercomputers are "powerful". But how do we measure this? How do we grant the title of "Fastest Supercomputer in the World"?  

Now, let's introduce the concept of performance. 

In supercomputing, we are normally interested in numerical computations: what is the answer to 0.234 + 3.456, or 1.4567 x 2.6734? Computers store numbers like these in floating-point format, so they are called floating-point numbers. A single instruction like addition or multiplication is called an operation, so we measure the speed of supercomputers in terms of floating-point operations per second or Flop/s, which is sometimes written and said more simply as Flops.

So how many Flops can a modern CPU-core perform? Let’s take a high-end processor like the AMD EPYC Zen2 (Rome) 7F32 CPU (which happens to be the processor used in the Snellius system at SURFsara). The way a processor is normally marketed is to quote its clock frequency, which here is 3.7 GHz. This is the rate at which each CPU-core operates. Clock speed is expressed in cycles per second (Hertz), and the prefix Giga means a billion (a thousand million), so this CPU-core is working at the almost mind-blowing rate of 3.7 billion cycles per second. Under favourable circumstances, an AMD EPYC CPU-core can perform 16 floating-point operations per cycle, which means each CPU-core can perform 16 x 3.7 billion = 59.2 billion floating-point operations per second.

So, the peak performance of one of our CPU-cores is 59.2 GFlops.

We say peak performance because this is the absolute maximum, never-to-be-exceeded figure which it is very hard to achieve in practice. However, it’s a very useful figure to know for reference.

Clearly, with many thousands of CPU-cores we’re going to encounter some big numbers so here is a table summarising the standard abbreviations you’ll come across:

|Ops per second  |	Scientific Notation | Prefix	| Unit |
|---|---|---|---|
| 1 000	| 10^3  |	Kilo	| Kflops |
| 1 000 000 |	10^6|	Mega |	Mflops |
| 1 000 000 000	| 10^9 |	Giga |	Gflops |
| 1 000 000 000 000 |	10^12 |	Tera |	Tflops |
| 1 000 000 000 000 000 |	10^15 |	Peta |	Pflops |
| 1 000 000 000 000 000 000 |	10^18 |	Exa | Eflops |


### Benchmarking - Rpeak and Rmax 

If we are going to compare performance we need some standard measure. To measure supercomputer performance the test drive is how fast it can run a standard program, and this process is called benchmarking.

In the supercomputer world, two terminologies are often used to measure the performance of a system, **Rpeak** and **Rmax**. Rpeak is the theoretical peak performance, which is just the peak performance of a CPU-core multiplied by the total number of CPU-cores. Rmax is the maximum performance achieved while running the **LINPACK benchmark**. LINPACK involves running a standard mathematical computation called an LU factorisation on a very large square matrix of size Nmax by Nmax. The matrix is just a table of floating-point numbers, and the rules of the benchmark allow you to choose how big Nmax is. For example, when running the LINPACK benchmark ARCHER2 used a Nmax of 5,816,959 - imaging working with a spreadsheet with nearly 6 million rows and 6 million columnns! 


## The Top500 list

The [Top500 list](https://www.top500.org/) ranks the fastest 500 supercomputers in the world. By fastest, we mean most powerful with the highest **Rpeak** and **Rmax**.

The first Top500 list was published in June 1993, and since then the Top500 project publishes an updated list of the supercomputers twice a year: 
1. June at the [ISC High Performance conference](https://www.isc-hpc.com/) in Germany. 
2. November at the [Supercomputing conference](https://sc23.supercomputing.org/) in the USA.

As of June 2023 the fastest supercomputer is **Frontier**. This is a supercomputer in the US at the Oak Ridge National Laboratory with 135,936 total CPUs, each with 64 CPU-cores each with an overall total of 8,699,904 CPU-cores. Frontier has recorded: 
* LINPACK performance (Rmax) of 1,194 PFlop/s = 1 194 000 000 000 000 Flop/s 
* Theoretical Peak Performance (Rpeak) of 1,679.82 PFlop/s = 1 679 820 000 000 000 Flop/s
* Power consumption of 22,703 kW = 22,703,000 W

The Frontier system was the first supercomputer to record performance at the Exascale, recording an Rmax of 1,194 PFlop/s which is equivalent to 1.1 ExaFlop/s. Reaching the exascale ushers in a new era of supercomputing and is a significant point in the history of supercomputing. 

You will notice that the power of each supercomputer is also quoted in the Top500 list. This leads to the creation of another list - **[the Green 500](https://www.top500.org/lists/green500/)** - which ranks supercomputers on their fuel economy in terms of Flops perWatt. Despite its massive power bill, Frontier is quite power-efficient and holds 6th position on the Green 500 (as of June 2023).

Have a look at the most recent top500 list and briefly comment on the following questions:
* What manufacturers produce the world’s largest supercomputers?
* What types of processors do they use?
* What fraction of peak performance is typically achieved for the LINPACK benchmark?
* Play with the statistics tool on top500.org and think about the trends in current HPC systems. For example, how many supercomputers in the Top500 are classed as being for use by industry?


### Supercomputing Word Search

To help you familiarise with the supercomputing terminology we have prepared a word search for you to print out!

```{figure} ./images/large_hero_9748869f-e962-4c23-a6b6-8216e757920c.png
```

The word search contains 19 words that have been mentioned in the previous steps. Can you find all of them? Do you know how to explain all of them?


---

## The evolution of supercomputers

How did computers become so powerful so quickly? Are there any fundamental limits to how fast a supercomputer can be? To answer these questions, we need to understand what CPUs are made of.

### What is inside a CPU? 

We measure the performance of a CPU-core based on the number of floating-point operations it can carry out per second, which in turn depends on the clock speed. CPUs are built from Integrated Circuits that consist of very large numbers of transistors. The transistors are connected by extremely small conducting wires which can carry an electric current. By controlling whether or not an electric current goes through certain conducting lines, we are able to encode information and perform calculations.

Most transistors nowadays are created with silicon, a type of semiconductor. A semiconductor is a material that can act as both a conductor (a material that permits the flow of electrons) and an insulator (that inhibits electron flow), which is exactly the characteristics we want a transistor to have. The maximum physical size of a processor chip is limited to a few square centimetres, so to get a more complicated and powerful processor we need to make the transistors smaller.

### Moore's Law 

In 1965, the co-founder of Fairchild Semiconductor and Intel, Gordon E. Moore, made an observation and forecast: he noticed that manufacturing processes were continually improving: 

> **“The number of transistors that could be placed on an integrated circuit was doubling approximately every two years.”**

Moore predicted that this would continue into the future. This observation is now called Moore’s law. Although it is really a forecast and not a fundamental law of nature, the prediction has been remarkably accurate for over 50 years: the first CPU from Intel (the i4004) introduced in 1971 had 2000 transistors, and Intel’s Core i7 CPU introduced in 2012 had 3 billion transistors. This is in excess of a million times more transistors, but is actually in line with what you would expect from the exponential growth of Moore’s law over around 40 years. 

It turns out that, as we pack our transistors closer and closer together, every time we double the density of transistors we can double the frequency. So, although Moore’s law is actually a prediction about the density of transistors, for the first four decades it also meant that:

> **“Every two years the CPU clock frequency doubled.”**

We saw clock speeds steadily increasing, up to GHz (a billion cycles per second), but then this growth stopped and clock speeds have remained at a few GHz for more than a decade. So, **did Moore’s law stop**?

The problem is that increasing clock frequency comes at a cost: it takes more power. Above a few GHz, our processors become too power hungry and too hot to use in everyday devices. But Moore’s law continues because, rather than increasing the frequency, we put more processors on the same physical chip. We call these CPU-cores, and we now have multicore processors. For the last decade, Moore's law has meant that: 

> **“Every two years, the number of CPU-cores in a processor now doubles.”**

Now, the trend of doubling transistors in integrated circuits is showing signs of slowing down. It’s no longer every two years but perhaps every three years, but the overall trend still continues. 

So what happens if the CPU-cores are not getting any faster and the number of CPU-cores on a processor stop increasing? How are we going to build faster supercomputers to cope with the increasing size and complexity of our computer simulations? The current trend in the supercomputing world is that supercomputers are getting bigger not faster. Since the speed of a single CPU-core cannot be increased any more, having more and more cores working together is the only way to meet our computational requirements.


### Moore's law in practice

To investigate Moore's Law in practice, we will now introduce a simple example: calulating the world's yearly income. This is simply solved by adding up all of numbers. But there are 7 billion of them! The real question is: how long would it take?

In this video David describes how to tackle the calculation in serial on his laptop. In the next step we will discuss how long it might take.

```{note}

We will use this example in other steps on this course to better illustrate some of the key concepts, so make sure you understand how it works.

```

<iframe id="kaltura_player" width="700" height="400" src="https://cdnapisec.kaltura.com/p/2010292/sp/201029200/embedIframeJs/uiconf_id/32599141/partner_id/2010292?iframeembed=true&playerId=kaltura_player&entry_id=1_tpqo25kw&flashvars[streamerType]=auto&amp;flashvars[localizationCode]=en&amp;flashvars[leadWithHTML5]=true&amp;flashvars[sideBarContainer.plugin]=true&amp;flashvars[sideBarContainer.position]=left&amp;flashvars[sideBarContainer.clickToClose]=true&amp;flashvars[chapters.plugin]=true&amp;flashvars[chapters.layout]=vertical&amp;flashvars[chapters.thumbnailRotator]=false&amp;flashvars[streamSelector.plugin]=true&amp;flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&amp;flashvars[dualScreen.plugin]=true&amp;flashvars[Kaltura.addCrossoriginToIframe]=true&amp;&wid=1_1ms2y7b4" width="400" height="285" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" sandbox="allow-downloads allow-forms allow-same-origin allow-scripts allow-top-navigation allow-pointer-lock allow-popups allow-modals allow-orientation-lock allow-popups-to-escape-sandbox allow-presentation allow-top-navigation-by-user-activation" frameborder="0" title="worlds_yearly_income_hd"></iframe>

```{solution} Transcript

0:11 - Here, we’re going to introduce a very simple example, of calculating the world’s yearly income. It’s a bit of a toy example. But, we’re going to imagine that we have a list of the incomes, the salaries, of everybody in the entire world, and we’re going to add them all up to work out what the total income of the world is. Now this is obviously a very simple example, and slightly artificial. But, we’ll actually use it, and come back to it, in a number of contexts. First of all, it is very useful as a specific example of a real calculation, where we can illustrate how much faster calculations have got, through the developments in processor technology over the years.

0:46 - We talk about megahertz, gigahertz, and all kinds of things like this, but if we focus on a specific calculation, it will maybe become more obvious what that actually translates into. Also we’ll come back to this example later on in the course, to see how you might implement it in parallel. How would you use multiple CPU cores to do the calculation faster? So, let’s imagine we have a list. It’s going to be a long list of the salaries of everybody in the world, ordered alphabetically by country and person. So, right at the top of list we have a couple of people, Aadel and Aamir Abdali, who live in Afghanistan. Unfortunately, people in Afghanistan, the average wage is quite low.

1:23 - But they earn just under 1,000 pounds a year each. We carry on down the list, we get a couple of representative people from the UK, Mark and Mary Hensen, a couple who live in the north of England, earning 20,000 or 30,000 pounds each. And there’s me, that’s my salary– oh there seems to be a small error there, you can’t quite see what my salary is, but anyway, I’m on the list as you’d expect. And way down at the bottom– we’re assuming there are seven billion people in the world, which is a reasonable estimate– a couple of brothers from Zimbabwe, Zojj and Zuka Zinyama, who run a successful garage and motor repair business, earning 3,500 and 1,000 pounds each.

1:58 - So what are we going to do to add up all these numbers? What we’re going to do is, we’re going to write a computer programme. Now, as I’ve said before, this isn’t a programming course, we don’t expect you to be a computer programmer. However, this is very simple, and it will serve to illustrate the way that computers work, and allow us to translate these megahertz and gigahertz frequencies we’ve been talking about into actual elapsed time in seconds. So how do we add it up? Well, first of all, we have a running total which we set to zero. And, we start at the top of the list, and we go through the numbers in order.

2:29 - So, we add the income to the total. We go to the next item in the list– the second, the third, the fourth, the fifth. And then we repeat, if we’re not at the end of the list. So if we’re not at the end of the list, but not at the seven billionth entry, we have to go back, add the next income to the total, go to the next item, and then keep repeating, repeating. So we repeat these three steps, three individual steps, we repeat them seven billion times. And once we’ve finished at the end, we can print the total out. So, it’s a very simple prescription, in some kind of pseudo-language of the computer program to add up these incomes.

3:04 - But, the most important point is the core loop, the one that’s executed seven billion times, has three distinct steps in it. And, we’re going to assume that each one of these corresponds to a single instruction issued by the CPU, by the processor. Now, it’s quite a naive assumption, but it’s perfectly OK for our purposes here.

```

How long does it take to add up 7 billion numbers? Well, it depends on what you are using to add them… In this video David uses the income calculation example to illustrate the impact of Moore's Law. 

<iframe id="kaltura_player" width="700" height="400" src="https://cdnapisec.kaltura.com/p/2010292/sp/201029200/embedIframeJs/uiconf_id/32599141/partner_id/2010292?iframeembed=true&playerId=kaltura_player&entry_id=1_4zab4d0l&flashvars[streamerType]=auto&amp;flashvars[localizationCode]=en&amp;flashvars[leadWithHTML5]=true&amp;flashvars[sideBarContainer.plugin]=true&amp;flashvars[sideBarContainer.position]=left&amp;flashvars[sideBarContainer.clickToClose]=true&amp;flashvars[chapters.plugin]=true&amp;flashvars[chapters.layout]=vertical&amp;flashvars[chapters.thumbnailRotator]=false&amp;flashvars[streamSelector.plugin]=true&amp;flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&amp;flashvars[dualScreen.plugin]=true&amp;flashvars[Kaltura.addCrossoriginToIframe]=true&amp;&wid=1_1mhy9m0z" width="400" height="285" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" sandbox="allow-downloads allow-forms allow-same-origin allow-scripts allow-top-navigation allow-pointer-lock allow-popups allow-modals allow-orientation-lock allow-popups-to-escape-sandbox allow-presentation allow-top-navigation-by-user-activation" frameborder="0" title="Moores_Law_hd"></iframe>

```{solution} Transcript

0:12 - So the question is, how long does this calculation take? So, what I’m going to do is I’m going to do a bit of history. I’m going to look at the history of processors over about the past five decades to see how long it would have taken to do this calculation on a particular processor from that time. I’m going to focus on Intel as a manufacturer. Intel is a very successful manufacturer today of processors– they are very prevalent in desktops and laptops– but there are other designers or manufacturers of processors you may have heard of. ARM, for example, who design a lot of the processors which go into mobile devices like mobile phones, and Nvidia who produce graphics processors.

0:48 - There’s also IBM, International Business Machines, who actually design their own processors, and AMD, who also make their own processors. But I’m going to look at Intel, the main reason is because they have a long history and we can look way back many decades to see how these things have gone on. Now, I’m starting in 1966, which might seem like a strange starting point, but that when I was born. So there I am in 1966. How long does it take me to do this calculation. Now I have 100 billion neurons– that’s a lot of neurons in my brain– but unfortunately these neurons aren’t particularly good at doing mechanical floating-point operations.

1:21 - So I reckon I could issue operations at the rate of one Hertz. So that’s the frequency one Hertz, which is one operation per second, or one second per operation. Now remember, the core loop had three steps in it. So at one operation per second, or one second per operation, it’s going to take me three seconds to do that loop. And it turns out it would take me 650 years to add up the salaries of all 7 billion people in the world. And that’s really, for one person, it’s just not going to even complete in a lifetime. So it’s a completely untenable calculation.

1:54 - Now back in 1971, Intel introduced what is now considered to be the first modern integrated microprocessor, the Intel 4004, and it had 2000 transistors. Not many transistors compared to my 100 billion neurons, but these transistors are very good at doing floating-point calculations. The frequency of this machine with about 100 kilohertz– 100 kilohertz is 100,000 operations per second, or one operation every 10 microseconds– a microsecond is a millionth of a second. So every millionth of a second, this chip could do one operation. Now, remember, there are three steps, so it’s going to take 30 microseconds to do each loop. So, the total time to do that seven billion times is two and a half days.

2:35 - So even over four decades ago, microprocessors were able to translate what would have been a completely unfeasible calculation for one person to do into something which can be done in a few days. Which is a major step forward. But if we fast forward another two decades, we see the impact of Moore’s law. Moore’s law is this exponential increase, this regular doubling of the number of transistors you can get on a microprocessor, and in 1993 Intel released the Pentium, and in the intervening decades the manufacturing technology had increased to such an extent that they could now put 3 million transistors on the Pentium. This extra density of transistors translates into the ability to run these at a faster frequency.

3:15 - The Pentium had a frequency of 60 megahertz. That’s 60 million operations per second, or the time per operation is 17 nanoseconds, where a nanosecond is a billionth of a second. Now it’s worth thinking about that for a while. A nanosecond is an extremely short period of time. Let’s imagine a ray of light. Light is the fastest thing there can be in the universe and every nanosecond, light only travels about 30 centimetres. So, each time that the Pentium issues an operation, it issues an operation every 17 nanoseconds. In those 17 nanoseconds, light has only travelled about five metres, about the width of a room. Now it takes three steps per loop.

3:56 - So the time loop is 50 nanoseconds, which means, in 1993, it would have taken six minutes to add up the salaries of everybody in the whole world. So, you can see, in a couple of decades a calculation which would have taken several days, has gone to something which you could just set the computer going, and go off and have a cup of coffee and come back, and it would be finished. So, let’s fast forward to 2012, another two decades. And Intel then released the core i7 processor, which had three billion transistors– not three million but three billion. It could operate at a frequency of three gigahertz, which is three billion operations per second.

4:29 - The time per operation is a third of a nanosecond. So each time that the core i7 could issue an operation, every third of a nanosecond, light could only travel 10 centimetres. So, you can see we’re approaching some fairly fundamental physical limits here, in how fast processors can go. The time per loop was one nanosecond. That meant that to add up all seven billion salaries would have taken seven seconds. So, again, in the intervening two decades from 1993 to 2012, we’ve gone from a calculation where you would have to go away and wait to have a cup of coffee for it to finish, to something you could just sit and it would be ready almost instantaneously.

5:05 - So, hopefully that illustrates the impact of Moore’s law. How, from 1971 to 2012, over the period of four decades, this relentless increase in the speed of CPUs has gone from a calculation taking two and a half days, to taking seven seconds.

```



# Parallel Computers
<!-- # How does your laptop work? -->

In a sense, your personal laptop is actually a mini supercomputer because it is a *parallel computer*. Both have the same essential components: a processor, Random Access Memory (RAM) for temporary storage of data and a hard-disk for long-term storage of programs and files. However, there is a key difference in the way the memory is configured - this is what we will be discussing over the next few parts. 

First, let's explore how your laptop works in parallel. 

## What do modern CPUs look like? 

To discuss how the modern CPU evolved, let's recap Moore's Law. 

Moore's law was the observation made in 1965 that **"every two years, the CPU clock frequency doubled."**. This was because CPU manufacturers were doubling the density of transisors on a CPU and therefore doubling the CPU Clock frequency. However, around 2005, the increase in clock speed stopped and frequencies started to plateau at around a couple of GHz. The reason was simple: the amount of electrical power required to run processors at these speeds had become so large that they were becoming too hot for the domestic market (could not be cooled by a simple fan) and too expensive to run for the commercial market (large electricity bills and expensive cooling infrastructure). So, manufacturers needed to innovate and find other ways to make their computers go faster. 

**Hence, the multicore CPU was invented.** Instead of doubling the number of transistors on a CPU, manufacturers put two CPUs on the same silicon chip. This was again doubled to 4, 8, 16, 32 and more! Now, Moore's Law can be interpreted as: **“Every two years, the number of CPU-cores in a processor now doubles.”**

```{note}
Let's review the terminology: for the remainder of this course we will refere to entire multicore CPUs (i.e. silicon chips with more than one CPU on them) as CPUs or processors. To avoid confusion, we will call each individual CPU a CPU-core. So, a quad-core CPU (or quad-core processor) has four CPU-cores.
```

We now have two complementary ways of building a parallel computer: we can build a single multicore computer using a processor with many CPU-cores, or we can take lots of separate computers, each with their own processor and memory, and link them together using a high-speed network. These two approaches are called  **shared-memory architecture** and **distributed-memory architecture** and we will now look at them in detail.

What do you think the main differences between these two approaches are? Can you think of any advantages and/or disadvantages for both of them?

---

## Shared Memory Architecture

The fundamental feature of a shared-memory computer is that all the CPU-cores are connected to the same piece of memory.

```{figure} ./images/hero_2160d5f2-d404-4b10-b77e-e7b2a04ac529.png
```

This is achieved by having a memory bus that takes requests for data from multiple sources (here, each of the four separate CPU-cores) and fetches the data from a single piece of memory. The term bus comes from the Latin omnibus meaning for all, indicating that it is a single resource shared by many CPU-cores.

A good analogy here is to think of four office-mates or workers (the CPU-cores) sharing a single office (the computer) with a single whiteboard (the memory). Each worker has their own set of whiteboard pens and an eraser, but they are not allowed to talk to each other: they can only communicate by writing to and reading from the whiteboard.

```{figure} ./images/hero_55c8a23e-686f-42a9-b7e9-de0a12208486.jpg
© iStock.com/oonal
```

Later on, we’ll start to think about how we can use this shared whiteboard to get the four workers to cooperate to solve the same problem more quickly than they can do it alone. However, the analogy already illustrates two key limitations of this approach:

1) **Memory capacity**: there is a limit to the size of the whiteboard that you can fit into an office, i.e. there is a limit to the amount of memory you can put into a single shared-memory computer;
2) **Memory access speed**: imagine that there were ten people in the same office - although they can in principle all read and write to the whiteboard, there’s simply not enough room for more than around four of them to do so at the same time as they start to get in each other’s way. Although you can fill the office full of more and more workers, their productivity will stall after about 4 workers because the additional workers will spend more and more time idle as they have to queue up to access the shared whiteboard.

It turns out that both of these limitations to the whiteboard analogy apply to shared-memory machines. If we look at the processor diagram above, you’ll see that all the CPU-cores share the same bus: the connection between the bus and the memory eventually becomes a bottleneck and there is simply no point in adding additional CPU-cores. Coupled with the fact that the kinds of programs we run on supercomputers tend to read and write large quantities of data, it is often memory access speed that is the limiting factor controlling how fast we can do a calculation, not the floating-point performance of the CPU-cores.

An overcrowded office clearly illustrates the fundamental challenges of this approach if we require many hundreds of thousands of CPU-cores.

```{note}

Despite its limitations, shared memory architectures are universal in modern processors. What do you think the advantages are?
```


## Simple Parallel Calculation

Let's look at a simple parallel calculation to discuss why and how we might use multiple CPU-cores. Again, let's return to our trusty calculation: computing the average income of the entire world's population. 

If we’re a bit less ambitious and think about several hundred people rather than several billion, we can imagine that all the individual salaries are already written on the shared whiteboard. Let’s imagine that the whiteboard is *just* large enough to fit 80 individual salaries. Think about the following:

- How could four workers cooperate to add up the salaries faster than a single worker?
- Give a rough estimate for how long a single worker would take to add up all the salaries.
- How long would 4 workers take for the same number of salaries?
- How long would 8 workers take (you can ignore the issue of overcrowding)?
- Would you expect to get exactly the same answer as before?

We’ll revisit this problem in much more detail later but you know enough already to start thinking about the fundamental issues.

## Why do I need a multicore laptop?

Your laptop will have a processor with multiple cores, Random Access Memory (RAM) for temporary storage of data and a hard-disk for long-term storage of programs and files. 

You might think the answer to our question is obvious: surely two CPU-cores will run my computer program twice as fast as a single CPU-core? Well, it may not be apparent until we cover how to parallelise a calculation in the next part, but it turns out that this is not the case. It usually requires manual intervention to enable a computer program to take advantage of multiple CPU-cores. Although this is possible to do, it certainly wouldn’t have been the case in 2005 when multicore CPUs first became commonplace.

So what is the advantage for a normal user who is not running parallel programs? 

## Operating system

The important point is that, as a user, you don’t actually say please run this program on that CPU-core. There is a piece of software that sits between you and the hardware that isolates you from direct access to the CPU-cores, memory etc. This is called the the Operating System or OS. There are several common OS’s around today - e.g. Windows, macOS, Linux and Android - but they all perform the same basic function: you ask the OS to execute a program, and it then decides if and when to actually run it on a physical CPU-core.

```{figure} ./images/hero_6d93ece3-84b2-495f-b5c5-0e0f652196ea.png
```

This enables even a single CPU-core machine to appear to be doing more than one thing at once - it will seem to be running dozens of programs at the same time. What is actually happening is that the OS is running one program for, say, a hundredth of a second, then stopping that program and running another one for a hundredth of a second, etc. Just like an animation running at many individual frames per second, this gives the illusion of continuous motion.

The important point is that all the CPU-cores within a CPU are under the control of a single OS. This means that your computer can genuinely run more than one program at the same time. It’s a bit more complicated for the OS - it has to decide not just which programs to run but also where to run them - but a good OS performs a juggling act to keep all the CPU-cores busy.

```{figure} ./images/hero_4a65543e-9635-4624-9811-5da1a0ab431e.png
```

This means that you can run a web browser, listen to music, edit a document and run a spreadsheet all at the same time without these different programs slowing each other down. Because of the shared memory, the OS can stop a program on CPU-core 1 and then restart it later on CPU-core 3: all the workers can read and write to the same shared whiteboard so can easily pick up where someone else has left off.

A shared-memory computer looks like a more powerful single-core computer: it operates like a single computer because it has a single OS, which fundamentally relies on all the CPU-cores being able to access the same memory. It is this flexibility that makes multicore shared-memory systems so useful.

So, for home use, the Operating System does everything for us, running many separate programs at the same time. On the other hand, in supercomputing we want to run a single program but make it go faster - the OS can’t really help us here and we’ll see that we have to work a bit harder.

In your opinion what are the downsides of this more advanced ‘single-core computer’ approach?


## In practice: how your laptop uses multiple CPU-cores

<iframe id="kaltura_player" width="700" height="400" src="https://cdnapisec.kaltura.com/p/2010292/sp/201029200/embedIframeJs/uiconf_id/32599141/partner_id/2010292?iframeembed=true&playerId=kaltura_player&entry_id=1_3g4n1c0n&flashvars[streamerType]=auto&amp;flashvars[localizationCode]=en&amp;flashvars[leadWithHTML5]=true&amp;flashvars[sideBarContainer.plugin]=true&amp;flashvars[sideBarContainer.position]=left&amp;flashvars[sideBarContainer.clickToClose]=true&amp;flashvars[chapters.plugin]=true&amp;flashvars[chapters.layout]=vertical&amp;flashvars[chapters.thumbnailRotator]=false&amp;flashvars[streamSelector.plugin]=true&amp;flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&amp;flashvars[dualScreen.plugin]=true&amp;flashvars[Kaltura.addCrossoriginToIframe]=true&amp;&wid=1_vf0ln82e" width="400" height="285" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" sandbox="allow-downloads allow-forms allow-same-origin allow-scripts allow-top-navigation allow-pointer-lock allow-popups allow-modals allow-orientation-lock allow-popups-to-escape-sandbox allow-presentation allow-top-navigation-by-user-activation" frameborder="0" title="Laptop_Multiple_CPU-cores_hd"></iframe>

```{solution} Transcript

0:15 - This short video is just a screencast to capture a session I’m running. And it’s really just to illustrate this diagram, here. We’ve seen here that the way that a shared memory machine works is that you have a single block of memory, and multiple CPU cores connected to that memory. But I’m really interested, here in the role that the operating system plays. And we’ve seen here that the user sits outside this bubble, here, and really just asks the operating system to run programs, run applications, and it’s the operating system that schedules these programs onto the different CPU cores.

0:47 - So, I thought it would be quite nice just to take a real example, run it on my machine, and we can just see how it works in practice. So, what I’m going to have to do, is I’m going to have to close down a lot of my applications, just to make sure that I have the minimum of activity going on in the background. So, I’ll close my web browser. I’ll even turn off the networking, so we have the minimum of interference. Now, I’m running here on a Linux laptop, running Ubuntu, but you get very similar effects on any system. So, the first thing I’m going to show is, I have a performance monitor here.

1:22 - And, what we can see here, is that this monitor has different schematics for what’s going on. But we have four CPUs here– CPU one, CPU two, CPU three, and CPU four– and they’re coloured different colours. Now, although there’s nothing going on, you might wonder, why is there so much activity. This is running at about 20%. Well, that’s because the screen recording software, the screen grabbing software I’m running is actually taking up significant amounts of CPU. So, we do have some background rate there.

1:54 - So, what I’ve done, is, I’ve written a program which adds up various salaries to work out a total income. Now, what I’m doing here is, I’m actually adding up 1,000 salaries. Now, from the back of the envelope calculation we did last week, where we thought each cycle would take about a nanosecond, that means that 1,000 cycles adding up 1,000 salaries, is going to take about a millionth of a second. Now that’s clearly too short a time to measure. So, I’m actually repeating this calculation 10 million times. And if we work that out– 10 million times a millionth of a second– we expect this calculation should take about 10 seconds. That will be our back of the envelope estimate.

2:30 - And, just a quick clarification– although this says CPU one, CPU two, CPU three, CPU four, in our terminology it would be CPU-cores. I would call this a single CPU with four cores here. So, let’s just run the program, which as I said, does this calculation of adding up 1,000 salaries, repeating it 10 million times, and see what our load monitor shows us. So, I’ve run it. Very quickly we should see– yes. The blue CPU, here, is taking up the slack. Oh, but it’s quickly being replaced by the orange CPU. The orange CPU here is running 100%, and, now it’s switched to another CPU and it’s gone down to zero. So, that’s a very, very interesting graph which illustrates two things.

3:12 - First of all, that this program can only run on one CPU at a time, but– one CPU core at a time– but the operating system has decided to move it. So it started out running this program on the blue CPU, CPU four, and then it moved it to the orange CPU. But, you can see that, overall, the time was about 10 seconds, as we expected. So, that does show that the operating system does actually move these programs around. A single process, which is what this program is, can only run on one CPU core at once, but the operating system can decide to move it around.

3:47 - Now, let’s see what happens if we run three of these programs at once. So, I’ve got multiple copies of my program, income 1K. I’ll run income 1K number one, number two, and number three, I’ll run them all at once. I can run them all at once. And let’s see what the load monitor does. I’m running them. And, almost immediately, we see that the CPUs become very, very heavily loaded. Now, in fact, almost all the CPUs become heavily loaded, because although I’m only running three copies of the program, my income program, we are also running the screen grabbing software, so it’s kind of shuffled off to the final CPU.

4:19 - But, we can see there, that what happened was– there were two interesting things to note. One was, that all these CPUs were active at the same time, but also that the calculation still took about 10 seconds. So, what the operating system was able to do, was it was able to run three copies of the same program, at the same time, by putting them on different CPUs.

4:43 - So, now you might ask, what happens if I run more applications, more programs, or more processes, than there are physical CPU-cores. So, here you can see I’ve actually got six copies of the program, and I’m going to run them all at once. And let’s see what happens.

4:59 - So, you’ll see almost immediately the CPU load jumps up, and all the four CPU-cores are very, very heavily loaded. So, this looks similar to what we had before. But there’s a subtle difference– that these CPU-cores are running more than one process. Not only is the operating system scheduling processes to different CPU-cores, it’s swapping them in and out, on the same CPU-core. And, the effect of that is, the calculation no longer takes 10 seconds, it takes more than 10 seconds. Because, each of these applications, each of these processes, is having to time share on the CPU-core. And, as we see here, it takes almost twice as long. It takes about 20 seconds, which is what you might have expected.

5:35 - So, that is quite interesting, that although the CPU, the processor, can do more than one thing at once, if there are four cores, and there are more than four programs to run, it can’t run them all at the same time. It has to time slice them in and out. And the main thing, here, is that we see that processes interact with each other, they affect each other, and it slows the runtime down. So, we’re able to run three of these programs in 10 seconds, which is the same time that one of them took, but six took about 20 seconds.

6:02 - And, the reason I’m talking about three and six and not four and eight, when I have four CPU-cores, is because I’m trying to leave one of the CPU-cores free to run the screen grabbing software, which seems to be taking up about the whole of one CPU-core equivalent.

```

This video shows a simple demo to illustrate how modern operating systems take advantage of many CPU-cores.

Watch what happens when David runs multiple copies of a simple income calculation program on his quad-core laptop. Do you find this behaviour surprising?

## Memory caches

```{figure} ./images/hero_f158c8fd-2092-4272-a9dc-e4806b44f9cc.png
```

As discussed in the whiteboard analogy, memory access speeds are a real issue in supercomputing. So, how are we able to still adhere to Moore's law whilst adding more and more CPU-cores to the same memory bus? Surely this would just make the contention even worse? 

The standard solution is to have a memory cache. This is basically a small amount of scratch memory on every CPU-core, which is very fast. However, it is also quite small - well under a megabyte when the total memory will be more than a thousand times larger - so how can it help us?

Think of the analogy with many workers sharing an office. The obvious solution to avoid always queueing up to access the shared whiteboard is to take a temporary copy of what you are working on. Imagine that each worker has a small notebook: when you need to read data from the whiteboard, you fill your notebook with everything you need and then you can work happily on your own at your desk while other people access the whiteboard.

This works very well for a single worker: you can work entirely from your personal notebook for long periods, and then transfer any updated results to the whiteboard before moving on to the next piece of work.

<!-- ## Terminology Quiz

```{questions} Question 1

A system built from a single multicore processor (perhaps with a few tens of CPU-cores) is an example of the ____ ____
architecture, whereas a system composed of many separate processors connected via a high-speed network is referred to as the
____ ____ architecture.

```

```{solution}

1) shared memory

2) distributed memory


```

```{questions} Qestion 2

The two main limitations of the shared-memory architecture are: memory ____
and memory ____ ____. The hierarchical memory structure is used to improve the memory access speeds. The smallest but also the fastest memory is called ____
memory. And keeping the data consistent and up-to-date on all the CPU-cores is called ____ ____.

```

```{solution}

1) capacity

2) access speed

3) cache

4) cache coherency

```

```{questions} Question 3

The situation when multiple CPU-cores try to use the same resources, e.g. memory, disk storage or network buses, is called ____ ____.

```

```{solution}

1) resource contention

``` -->

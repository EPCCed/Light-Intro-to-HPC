Supercomputers are not only expensive to purchase, but they are also expensive to run because the power consumption can be huge. A typical supercomputer consumes multiple megawatts, and this power is turned into heat which we have to get rid of.


For example, the fourth on the top500 list, Tianhe-2 system has a peak power consumption of 18.5 megawatts and, including external cooling, the system drew an aggregate of 24 megawatts when running the LINPACK benchmark. If a kilowatt of power costs 10 cents per hour, Tianhe-2’s peak power consumption will be 2400 euros per hour, which is in excess of 21 million euros per year.

HPC system design... 
## HPC System Design

Now you understand the basic hardware of supercomputers, you might be wondering what a complete system looks like. Let’s have a look at the high-level architecture of supercomputer, mainly pointing out how it differs from a desktop machine.

The figure below shows the building blocks of a complete supercomputer system and how they are connected together. Most systems in the world will look like this at an abstract level, so understanding this simple figure will give you a good model for how all supercomputers are put together.

```{figure} ./images/large_hero_a3db6ae7-8a0e-4fe4-b2da-302380de963a.png
```

Let’s go through the figure step by step.

### Interactive Nodes

As a user of a supercomputer, you will get some login credentials, for example a username and password. Using these you can access one of the interactive nodes (sometimes called login nodes). You don’t have to travel to the supercomputer centre where these interactive nodes are located - you just connect from your desktop machine over the internet.

Since a supercomputer system typically has many hundreds of users, there are normally several interactive nodes which share the workloads, i.e. to make sure that all the users are not trying to access one single machine at the same time. This is where you do all your everyday tasks such as developing computer programs or visualising results.

### Batch System

Once logged into an interactive node, you can now run large computations on the supercomputer. It is very important to understand that you do not directly access the CPU-cores that do the hard work. Supercomputers operate in batch mode - you submit a job (including everything needed to run your simulation) to a queue and it is run some time in the future. This is done to ensure that the whole system is utilised as fully as possible.

The user creates a small file, referred to as a job script, which specifies all the parameters of the computation such as which program is to be run, the number of CPU-cores required, the expected duration of the job etc. This is then submitted to the batch system. Resources will be allocated when available and a user will be guaranteed exclusive access to all the CPU-cores they are assigned. This prevents other processes from interfering with a job and allows it to achieve the best performance.

It is the job of the batch scheduler to look at all the jobs in the queue and decide which jobs to run based on, for example, their expected execution time and how many CPU-cores they require. At any one time, a single supercomputer could be running several parallel jobs with hundreds waiting in the queue. Each job will be allocated a separate portion of the whole supercomputer. A good batch system will keep the supercomputer full with jobs all the time, but not leave individual jobs in the queue for too long.

### Compute nodes

The compute nodes are at the core of the system and the part that we’ve concentrated on for most of this week. They contain the resources to execute user jobs - the thousands of CPU-cores operating in parallel that give a supercomputer its power. They are connected by fast interconnect, so that the communication time between CPU-cores impacts program run times as little as possible.

### Storage
Although the compute nodes may have disks attached to them, they are only used for temporary storage while a job is running. There will be some large external storage, comprising thousands of disks, to store the input and output files for each computation. This is connected to the compute nodes using fast interconnect so that computations which have large amounts of data as input or output don’t spend too much time accessing their files. The main storage area will also be accessible from the interactive nodes, e.g. so you can visualise your results.



### Writing data
It also works very well for multiple workers if they only ever read data. Unfortunately, real programs also write data, i.e. workers will want to modify the data on the whiteboard. If two people are working on the same data at the same time, we have a problem: if one worker changes some numbers in their notebook then the other worker needs to know about it. The compromise solution is to let everyone know whenever you modify any results in your notebook. Whenever you alter a number, you have to shout out:

"I’ve just changed the entry for the 231st salary - if you have a copy of it then you’ll need to get the new value from me!"

Although this is OK for a small number of workers, it clearly has problems when there are lots of workers. Imagine 100 workers: whenever you change a number you have to let 99 other people know about it, which wastes time. Even worse, you have to be continually listening for updates from 99 other workers instead of concentrating on doing your own calculation.

This is the fundamental dilemma: memory access is so slow that we need small, fast caches so we can access data as fast as we can process it. However, whenever we write data there is an overhead which grows with the number of CPU-cores and will eventually make everything slow down again.

Keeping the data consistent and up-to-date on all the CPU-cores is called cache coherency. It means that we always have up-to-date values in our notebook (or, at the very least, that we know when our notebook is out of date and we must return to the whiteboard). Ensuring cache coherency is the major obstacle to building very large multicore processors.


```{figure} ./images/hero_f158c8fd-2092-4272-a9dc-e4806b44f9cc.png
```

Keeping all the caches coherent when we write data is the major challenge.

What do you think is the current state-of-the-art? How many CPU-cores do high-end processors have?



## Resource Contention

<iframe id="kaltura_player" width="700" height="400" src="https://cdnapisec.kaltura.com/p/2010292/sp/201029200/embedIframeJs/uiconf_id/32599141/partner_id/2010292?iframeembed=true&playerId=kaltura_player&entry_id=1_s0oh0v7t&flashvars[streamerType]=auto&amp;flashvars[localizationCode]=en&amp;flashvars[leadWithHTML5]=true&amp;flashvars[sideBarContainer.plugin]=true&amp;flashvars[sideBarContainer.position]=left&amp;flashvars[sideBarContainer.clickToClose]=true&amp;flashvars[chapters.plugin]=true&amp;flashvars[chapters.layout]=vertical&amp;flashvars[chapters.thumbnailRotator]=false&amp;flashvars[streamSelector.plugin]=true&amp;flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&amp;flashvars[dualScreen.plugin]=true&amp;flashvars[Kaltura.addCrossoriginToIframe]=true&amp;&wid=1_fhat1vsf" width="400" height="285" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" sandbox="allow-downloads allow-forms allow-same-origin allow-scripts allow-top-navigation allow-pointer-lock allow-popups allow-modals allow-orientation-lock allow-popups-to-escape-sandbox allow-presentation allow-top-navigation-by-user-activation" frameborder="0" title="Resource_Contention_hd"></iframe>

```{solution} Transcript

0:12 - Although it’s a very simple program, it can show some very interesting affects. Now, our key observation, was that we could run three copies of this program in the same time as if we ran one copy. In 10 seconds, we could run three copies on three CPU-cores in the same time as we ran one copy on one CPU core. However, this week we’ve been talking about the shared-memory architecture, how one of the critical features of it is that all the CPU-cores share access to the shared memory. There’s a single memory bus that they have to go through. And so, they can affect each other, they can slow each other down. Why didn’t that happen here?

0:48 - Well, it didn’t happen here, because we were summing up a very, very small number of numbers. We were summing up 1,000 incomes. And they were able to all fit into the cache. And, if you remember, each CPU-core has its own cache. And, so, for most of the time, when they were running, these CPU-cores could run completely independently of each other. However, we can look at a different situation, where the CPU cores do have to access main memory, and they will interact with each other. Programs running on different CPU-cores will slow each other down. So, what I’ve done is, I’ve written a version of this program, which doesn’t add up 1,000 numbers, it adds up a million numbers.

1:27 - So income 1M, I’m adding up a million numbers, here. Now, what I’m doing is I’m repeating this fewer times to get a runtime of around 10 seconds. But, what we’ll do is we’ll run this calculation once, and see what happens, see what our baseline time is. So, I run one copy of this program. Remember, it’s now adding up a million numbers, a million salaries each iteration, rather than 1,000. So, there we go. And we see the same effect that suddenly one of the CPU cores is very heavily loaded, in this case, the green CPU, CPU three. And, how long is it going to run for? Well, it’s actually switched onto CPU two, and switched onto another CPU again.

2:07 - But, overall, it’s running for about– just over 10 seconds. A bit more than 10 seconds, there, it was more like, maybe about 15 seconds. I’ll maybe run it again, to try and get a cleaner run, where it doesn’t switch around so much on different CPU-cores. Crank up again it’s on the– no, it is, it’s switching them all around. We’ll try and get another estimate of how long it takes. This is a bit nicer, it’s mainly on the orange CPU-core, there.

2:35 - So, that looks like it’s taking about 15 seconds. But I said that the big difference between this calculation is because it’s reading and writing large amounts of memory– then processes running on different CPU cores will affect each other, because they will be accessing the same memory bus. So if I now run three copies of this program, I would expect that, although we’ll see the same effect but all three CPU-cores will be 100% loaded, we would expect the total runtime to increase beyond the 15 seconds. So let’s run that, and see what happens.

3:09 - And, now bang, we’re up to 100% CPU. But, unlike the case where we’re accessing small amounts of memory, which sits in cache, we expect these to contend with each other. And, you can see yes, it is taking significantly longer than 15 seconds. Although you might think, in principle, these calculations are completely independent, they’re interacting by accessing the shared memory. And it looks like, in fact, they’re completely blocking each other out.

3:43 - And there, it took about 35 seconds. So, over twice the time to do the same calculation. So, you can see it’s absolutely clear from this simple experimental result, that, even on my laptop, this shared memory bus– which mediates the memory transactions from the CPU-core to the physical memory– is not capable of sustaining all the traffic from three very, very simple programs running at once.

```


This video shows a simple demo to illustrate what happens when multiple cores try to use the same resources at the same time.

As we have mentioned before, the situation when multiple CPU-cores try to use the same resources, e.g. memory, disk storage or network buses, is called resource contention. Here we look at memory access.

Watch what happens when three copies of a larger income calculation program are running on three CPU-cores at the same time. Is this what you expected?

Keep in mind that, although, the CPU-cores do affect each other it’s not because they exchange any data, but because they need the same data from the memory. In other words, the CPU-cores do not collaborate with each other i.e. they do not share the total work amongst themselves.

Note that I accidentally mis-spoke in the video and the larger calculation actually processes 100 million salaries and not 1 million - David

As for Step 2.6, I also re-ran the same calculations with the graphical monitor turned off so I had access to all 4 CPU-cores. Here are the timings for this large dataset where I reproduce the previous small dataset results for comparison.

<center>

|dataset | #copies | runtime (seconds)|
| --- | --- | --- |
|small |	1	| 9.7 |
|small |	4	| 11.1 |
|small |	8	| 22.2 |
|large |	1	| 10.7 |
|large |	4 |	28.5 |
|large |	8 |	57.0 |

</center>

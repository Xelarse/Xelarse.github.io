---
layout: post
title: "Dissertation Midpoint Update"
date: 2020-01-14 12:00:00
author: Alexander Allman
categories:
- Blog
- Creative Technologies
- Dissertation
img: blankBanner.png
thumb: c_thumb.jpg
published: true
---

### Midway Update!

After having a few months to work on my dissertation I reflect on my current progress.

<!--more-->
-----
The current iteration of the project is a reasonable success. The systems I have implemented work as intended although there is definitely room for improvement which will be looked into with further detail below.

To see the proposal of my dissertation please click [Here](/assets/docs/DisProposal.pdf)

To see the research put together for the dissertation please click [Here](/assets/docs/DisResearch.pdf)

To get a quick summary of how the project is progressing please view the video below:
{% include youtubePlayer.html id="QE63zN_n9iE" %}


#### Job System
As mentioned in the video the current Job system only has one major disadvantage currently and thats creating threads to use every update. There is a notable amount of overhead involved with the creating and destruction of threads every update so the proposed solution is thread pooling. The idea of this is that you create a thread and keep it running constantly; Once you have work for it you then find a thread that is available for it then send it on its way. If the thread isn't being used and isn't needed currently, then the thread will sleep until its required again. The thread will only get destroyed once the program has finished running. 

There are also plans to expand on this system to make it more friendly and flexible for the developer. The first of which involves the use of semaphores to allow the developer to batch and order jobs. For example, if a set of data relied on a different mutation being performed on it beforehand, the developer could task the needed mutation as "1" and the following one as "2". Then my Job system would ensure all "1" tasks are completed before "2" tasks. There will also be an option to leave this undefined to help prevent bottlenecking so that tasks that can be done without any reliance on other mutations can just run. The second improvement will be oriented around the thread pool and deciding how many threads to create. As I've mentioned in my [research](/assets/docs/DisResearch.pdf), there is a sheer falloff point in performance when having too many threads created and running; which revolves around frequent context switching. So to help fix this I will benchmark on the start of the program at which point the system does begin to drop of in terms of performance; take a few steps back and set that as a hard limit. Then the developer can decide how aggressively they want their software to use threads and depending on this, a ratio of the hard limit will be used to determine how many threads will be used in that software instance.

#### Memory Manager
The current memory allocator built for this project is based around a free linked list, allowing for flexible de/allocations. However, currently to ensure data is stored contigiously allocations aren't done on an individual basis, such as a single float but for a whole array of planned floats. This ensures that when using the Job system all the data thats being referred to is spacially local for quick reading. This also however makes it slightly more inflexible as these variables cannot be removed unless creating a whole copy of the buffer minus the variable to be deleted and then reordering it in the memory allocator. So until a system for this is developed currently the develop has to tag a variable by setting it to a value and checking against it. For example, if the NPC is dead set it's health to "-1" and when processing mutations on the data skip values of "-1".

Another large improvement to be made to the Memory Manager is revolving around accessing the data it has stored. Currently to get a reference to the data, the developer needs to give the manager a unique ID which it then has a a table it can lookup to find the corresponding void* to return. In a future iteration I want to develop a template system which automatically creates a GUID when the user creates the variable so that they don't have to keep track of this GUID. Then to get the base pointer of the memory allocation a static function will be used in the template class to take the current classes GUID, query the manager and then return the appropriate void*.

#### Conclusion
Considering this is the first time I've done anything with memory allocation and over a year since I touched threading I am very happy with the current progress and excited to further it. Data Oriented Design has definitely peaked my interest as its such an interesting development paradigm that when researched just makes sense on why can grant performance gains. Although my system will never be as performant as a pure Data Oriented program, mine is definitely showing promise in comparison to an Object Oriented one and might be a nice way to bridge the gap for new Data Oriented developers, or for Object Oriented developers who want that bit of extra performance.

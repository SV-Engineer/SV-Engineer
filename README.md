# Introduction
## Basic Information
Name
: Austin (@SV-Engineer)

Location
: Dallas, Tx

Contact
: systemverilogengineer@gmail.com

## Notes:
1. If you have found this page and are wondering why all of the repositories seem so sparse, I do have an answer. The answer is that I previously had a repository associated with my university email. That email has been deleted. For one, I didn't anticipate that git would lock me out and for two I truthfully did neglect it to some extent. One part of me wants to try and recover it and the other takes this as an opportunity to consolidate and rewrite. I cannot truthfully say I understood, let alone followed, good coding practices in university. The only code I believe worth recovering from that period includes:
   *  My independent implementation of an RTOS on an ARM M4 uProcessor. This was done in Mixed ARM Assembly and C.
   *  My implementation of a MIPS 32-bit processor including pipelining, data forwarding and hazard detection (VHDL).
   *  My various machine learning algorithms implemented in python with pytorch.

2. Some of the above mentioned were whole courses worth of work. Even if I did reproduce the code, some of it would likely have to remain private. Most importantly out of respect for the professors that enabled me to learn and secondarily (but not any less important) because of enabling current students to violate the student code of conduct; plagiarism.

## Coding Languages
* Embedded C
* C++
* Some ARM Assembly
* Python
* System Verilog

## Coding Philosophy
&nbsp;&nbsp;Despite the tedium it may add, I believe code should be written with the reader in mind. No, I don't mean to imply that I impede myself from getting work done in the short term. I mean to imply that I do as best as I can to balance the short term needs with the long term needs of whatever codebase I am working on. The work I do sometimes strays from this philosophy and I take great care to bring it back to compatibility. Why? Two main reasons that are not wholly independent. The first reason is that if I have to come back to my code months later, I want to be able to quickly get back up to speed on what decisions were made and how it is organized. The second reason is that I wish to enable someone else to understand what the code does in the event that I am not available. This all comes back to enabling the user to update and/or modify the code easily without completely breaking it.

&nbsp;&nbsp;Working in industry for more than four years has taught me the sheer importance of organization. Furthermore, it has taught me that I should stick to a philosophy of organization as best as I can. My understanding is that any coding language is purposefully barebones for the sake of being adaptable to the project at hand. There are tools available, such as typedefs, macros, packages, header files, and many debug related preprocessor statements that enable an individual or team to create a framework that suites the needs of their project and long term development.

&nbsp;&nbsp; For example, the update made to the standard libraries upon release of C99. Previous to the release of this standard, it became obvious that the axiomatic types in the "stdint.h" header were valuable as building blocks. They became part of the standard library. If a library of axioms such as defined in the `<stdint.h>` is not available for the language being used, perhaps it is valuable for a team of individuals to collaborate and agree upon primitives to be used. Where the main benefit is enabling discipline in the basics such as casting. Furthermore it allows users to build upon them to create data structures as needed. All in the name of organization and readability.

&nbsp;&nbsp;To expand upon my experience in industry, I would like to briefly discuss the tools that enable us to code as well. I think it important to understand how the compiler for the language you are using works; at an abstracted high level at minimum. It is immensely helpful to understand the steps that it takes as far as parsing preprocessor statements, keywords, and making its decisions. It is of utmost importance, I believe, that I be completely explicit in how I write my code such that the compiler never has to make a decision based upon ambiguity. For example, implicit casting is a tough issue to catch for inexperienced and experienced users alike. This is especially apparent in the case where warnings are suppressed from the compiler. One situation that implicit casting can be an issue is in bit-wise operations. For example in an embedded C project, if you are trying to concatenate two int16_t data types into a uint32_t data type for writing to a peripheral. If the steps look like:
```C
#include <stdint.h>
#define HWORD0_POS 0
#define HWORD1_POS 16

int main()
{
  int16_t a  = -58;
  int16_t b  = 7;
  uint32_t c = 0x0U;

  c = (((uint32_t) b) << HWORD1_POS) | (((uint32_t) a) << HWORD0_POS);

  return 0;
}
```
there is an implicit cast occuring on variables a and b. In the case of b, the implicit cast will result in what the writer intended because the sign bit is not set. In variable a, the implicit cast actually looks like: `(uint32_t) ((int32_t) a)` and sign extension occurs. Thus the upper half-word of c will always be 1's in the case of 'a' being a negative number. Based on the objective set, this is not the intended behavior and the compiler does not know any better. This can be a challenge to debug and this is a good example of not only why we should always be explicit in what we write, but also why it is important to know how the compiler itself works. There may be a compiler out there that has different rules than I have described. The above example is based upon experience with the ARM compiler.

# Elevator Speech
My name is Austin. I am an Electrical Engineering graduate from University of Florida; co 2020. On the professional side of things, I am a Digital Design Engineer + Embedded Engineer and I love to tinker and learn new concepts. An example of this is that I have recently discovered the composition approach in object oriented programming. This is similar to the traditional inheritance approach, yet it has it's own nuances. My current understanding of the main benefit of the composition approach is that alike data may be stored in contiguous memory, meaning that iterating through said data is more efficient because the CPU is enabled to fetch the data it needs (and only the data it needs). Furthermore, there is also a resultant reduction in branches, preventing the pipeline from being cleared. This directly implies that the branch prediction implemented in the pipeline is more meaningful. As less branching is done overall, there is less opportunity for a "miss." It is the act of learning that keeps me motivated and this kind of knowledge is what helps drive that behavior. Lastly, I cannot claim to know everything. I find myself constantly adjusting my views, in hopes that I may keep them aligned with what is correct; as opposed to being correct. I wish to surround myself with like minded people where ever I go.

# About
In general I consider myself a reasonably simple person. I enjoy interacting with my wife, our cats, and our friends. As far as hobbies go, I enjoy compelling stories, tinkering with things to discover what makes them work, and laughing at the various absurdities that present themselves to me in life. I do not have life entirely sorted out. I do realize that I am here and I want to make an impact; preferably in a way that guides us all in a positive way. 

My heroes include:
  * Nikola Tesla in his tireless endeavors to improve.
  * Cecilia Payne in her stalwart efforts in the face of adversity to convince the rest of the world that really, hydrogen is the most abundant element in the universe.
  * Albert Einstein in his pure force of will to consider all wrong possibilities until he got to the correct answer.
  * Christopher Hitchens in his endeavor to encourage people to think critically and his sincere compassion for others.
  * Neil Degrasse-Tyson and Bill Nye both in their patience as they try to educate as many people as they can.
  * Sophie Scholl in her fortitude to stand up; even when almost no one else would.

I originally set out to "change the world" in whatever way I could manifest after reading Nikola Tesla's autobiography [My Inventions](https://en.wikipedia.org/wiki/My_Inventions:_The_Autobiography_of_Nikola_Tesla). What that book meant to me was that even if we are struggling, we can still achieve; the struggle is what makes us grow. From there I went forward into the adventures of Community College and University. A fool with an open mind. In high school and before, I truly can claim the title of uneducated fool. I knew very little while being immensely adversarial. The hall-mark of a true fool. I took the math aptitude test, and tested at the lowest level offered at the community college; Intermediate Algebra. I knew how to add and subtract and multiply, though division I required a calculator. To be honest, I still don't know my times tables and I have to look up how long division works everytime it becomes necessary (looking at you partial fraction decomposition). Yet despite all of this, at some point or other, I demonstrated competency in Vector Calculus, Differential Equations, Physics, Circuit Analysis, and so much more. I have forgotten more about math than most people ever know exists.

# What Is Important To Me With Respect To Writing Code
I can summarize this topic in one main idea:

&nbsp;&nbsp;**Long term sustainability through effective organization**.

What does this mean? The idea stated above can be divided into (at least) three categories. Maintainability, Readability and Expandability. The goal of this repository is to develop my skills in these ideas through self-study. This includes reading the code of others. Furthermore, I am trying to understand what the empirically agreed upon industry standards are on this topic rather than relying on anectdotal evidence. The following sub-sections will dive deeper into these three concepts and attempt to provide examples of what I understand goes against the spirit of the ideas and examples that are in compliance with the ideas.

## Maintainability
Maintainability to me means how easy is it to make a change in the code base when the understanding of the design specification changes or heavens forbid _the design specification changes_.

## Readability 
By readability I intend to imply directly the meaning of the word. How readable is the code I am producing? Will it be easy for someone to understand the intent of my logic? Will they spend hours puzzling over what I have done because I failed to communicate effectively through coherency, comments and documentation how it works?

## Expandability
The term expandability can be further divided into two ideas. 
    
  1. Is the piece of code I am writing generic enough to be reused when the associated logic is called for without being so generic that the meaning is lost?
    
  2. Does the code I've written avoid things such as global variables and hard-coded values?

# Problem Solving Philosophy
This philosophy assumes that a coherent definition of a problem has been provided to the developer. In the case of a Design Specification, the requirements must all have clear definition. In general, no one should be developing in a professional environment, if a complete definition of the problem to be solved does not exist. The goals are:
  * Maintainability
  * Minimization of Technical Debt
  * Avoidance of duplication of effort
  * Reusability

## Step 0: Understanding The Problem
Complex questions are deserving of complex answers, at least initially. A reliable method of solving problems is the "brute-force-and-difficulty" (BFAD) method. The BFAD method certainly has its own draw backs and should be reserved for understanding difficult problems. If a developer needs to perform a simple problem such as writing a for loop to interate through a list of numbers and find the max value, they likely don't require BFAD. Because simple problems by their very nature are simple to solve, they are not within the scope of this discussion.

What is meant when suggesting BFAD? Perhaps the developer should be employing some bad coding practices[^1]. Confined to a prototyping file on a local branch. No functions, iteration ignored, no verbose comments. Spend the initial energy on writing bad code that solves the problem.

Now, if I've lost you at this point, allow me to bring you back. This methodology has a hard requirement of discipline. For example, the scope of employing bad practice shall be limited to a single prototyping file such that the case of committing garbage to a remote repository is avoided. The following sections will further define the discipline required to use BFAD and how avoidance of garbage in the remote shall be achieved.

## Step 1: Analysis - Building Off The Bad Code
Now that a base case or cases of the problem have been solved, stop writing code and start analyzing it. Make a commit on a local dev branch to create a checkpoint. If working with others, keep in mind if a rebase of your local branch becomes necessary. Take some time to use a tool such as Visio to make a flow chart of what the code does now. Then copy the flow chart and start modifying it into a state that the code should be in. If a flow chart can't be made, write some pseudo code of the desired final state.

As you analyze the bad code you wrote, ask yourself some or all of the following:
  * What code did I copy paste and how can I parameterize it and reuse it?
  * Do I need to `typedef` a data structure for complex data manipulation?
  * What is the common case of any `if-else` blocks?
  * Did any edge cases become apparent when working through it initially?
  * What are the discrete component steps to solving this problem?
  * What information am I missing to make this succinct?
  * Is the list of files I predict that require an update complete?

## Step 2: Abstraction and Documentation
At this point, it's time to practice the discipline planned for in the previous step. Abstract the pieces into functions and / or macros as necessary. Each function shall either perform a simple action, or call multiple functions to enable more complex behavior. Leverage the tools such as pointers (to include passing by reference), return values for error checking, and verbose logging.

If you aren't using a tool such as [Doxygen](https://www.doxygen.nl/) to automate the documentation generation, you should be. It is free for individuals and most[^2] companies have it on their Linux systems. This step also has expectation that the developer is documenting their solution reasonably coherently so that others are enabled to maintain the code in the long-term. A solution in the short-term that results in a module rewrite in the future is a bad solution; anything that leads to duplication of effort should be avoided if possible. There must be balance between short-term and long-term planning when managing a code base. If all decisions made are for the short term and no concern for the long term, the code base will reach a tipping point where all development time is spent on maintaining it and putting out fires caused by technical debt. Naturally the corollary is that if all effort is spent on long term planning that leads to analysis paralysis that results in goals not being met and deliverables left incomplete, the developer is at the opposite extrema.

With that subject discussed, let's turn our attention back to abstraction in the context of the feature and/or solution development. Abstraction is good. Too much abstraction is bad in the same way that no abstraction is bad. Each abstraction beyond 2 layers[^3] shall be evaluated for potential technical debt and necessity. Abstraction layers shall be limited to 4; anything beyond 3 layers shall face heavy scrutiny. The reader should be able to open the header file or package and quickly understand what the abstracted data types are composed of. This applies less to the project and code base as a whole, where modules may exist with their own dependency tree. The goal is to compartmentalize the abstraction.

## TL;DR
1. Brute force and difficulty the base case and note any edge cases that come up.
2. Identify the component steps from the base case.
3. Abstract the component steps into reusable pieces; where each abstraction is dependent on the previous abstractions.

[^1]: This methodology does not necessarily apply to any sanity checking unit tests being developed in tandem with solving the problem.
[^2]: This part of the statement is anectodal understanding.
[^3]: The built-in library types are the 0th layer.

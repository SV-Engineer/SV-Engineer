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
&nbsp;&nbsp;Despite the tedium it may add, I believe code should be written with the reader in mind. No, I don't mean to imply that I impede myself from getting work done in the short term. I mean to imply that I do as best as I can to balance the short term needs with the long term needs of whatever codebase I am working on. The work I do sometimes strays from this philosophy and I take great care to bring it back to compatibility. Why? Two main reasons that are not wholly independent. The first reason is that if I have to come back to my code months later, I want to be able to quickly get back up to speed on what decisions were made and how it is organized. The second reason is the direct corollary in that I wish to enable someone else to understand what the code does in the event that I am not available. This all comes back to enabling the user to update and/or modify the code easily without completely breaking it.

&nbsp;&nbsp;Working in industry for a few years has taught me the sheer importance of organization. Furthermore it has taught me that I should stick to this philosophy as best as I can. My understanding is that any coding language is purposefully barebones for the sake of being adaptable to the project at hand. There are tools available such as typedefs, macros, packages, header files, and all of the other preprocessor statements that enable an individual or team to create a framework that suites the needs of their project and long term development. An example of this can be found in C regarding the C99 standard library. Previous to the release of the C99 standard, it became obvious that the primitive types in the "stdint.h" header were valuable as building blocks and became part of the standard library when the C99 standard was released. If a library of primitives like this is not available for the language being used, then it may be valuable for a team of individuals to collaborate and agree upon primitives to be used. To enable casting and to build upon to create relevant data structures as needed. All in the name of organization and readability.

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

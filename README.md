# operations_memory_state_manager

(very (very) rough notes: e.g. terminology used in some sections is A. 'deprecated' or B. that status is still unclear) 2026 09 22

Proto-Type
"No one-pattern is all-patterns."

Working Title "Proto-Type"
'A programming language with no features.'



- Not-a-Compiler
- Not-a-language

- terms?

---

When we say 'c' we are often referring to a language and to a compiler and maybe also to something else.

likewise, 

When we say 'Rust' we are often referring to a language and to a compiler and maybe also to something else.

By convention we have gotten use to arm-waving away the issues with not distinguishing between languages and compilers and with ignoring the other definitions assumptions and conventions involved in 'a language'

But with this 'proto-type' (for lack of a better working-title), we should likely dive into those distinctions.
(though it may make this (proto-type) difficult to describe...
a language-compiler-not-language-not-compiler
 



---
Memory-Safe Assembler Framework

(non-abstract physical memory static analysis)

(from a quick check online (the google) I cannot find any reference to memory-safety for assembly-language (the opposite: every page and post seems to re-iterate: 'of course there is zero memory safety for assembly language'


What is primary in this context:
- threads?
- lifetimes?

Possibly for specific types of uses:
There is no assumption that there is one single mode or equilibria that covers all situations.

Going back to 1900 (hilbert) 1913 (R&W Pricipia) 1931(Godel) 1936(T&T) 1938(T:Oracles & NP-Completeness) 2006 (Holzmann-10)
Aspects such as recursion may need to be pruned/punted.

Note:
In terms of what may be defined as a 'memory-model' or a 'memory optimization' it should be least be discussed that there is a non-monolythic set of perhaps in some ways nevertheless at least partially convergent diversity of approaches around 'modeling' (which is strangely simultaneously central to STEM and also something not directly addressed 'in mixed company'): 
Either how memory/threads/something are 'modeled' or how 'optimized performance' (vs. optimized size..., there is not just one thing to 'optimize' for) likely has a diversity of somewhat overlapping approaches where, as is the pattern: no one-pattern is all-patterns.
 
see:
https://github.com/lineality/granmo_model_nlp_classifier_rust

https://github.com/lineality/granmo_model_nlp_classifier_rust/blob/main/features_and_granmo_language_definition.md

https://github.com/lineality/granmo_model_nlp_classifier_rust/blob/main/granmo_model_projects_notes.md 

https://github.com/lineality/granmo_model_nlp_classifier_rust/blob/main/the_echo.md 


There are a number of ideas explored here, but the main long term focus should be on 'memory safety' (so far probably not well defined) for assembly-language or machine-code. If other areas are parsimonious and cross-reinforcing with possible-solutions for memory-analysis, great. If not, the focus is on memory-safety. 


- memory audit
- Q: "compile time" memory safety
- execution-time memory safety (?)
- error-messages
- "compiler"/static-analyzer error messages

- types of optimization
- performance optimization (specific areas?)
- size optimization (specific areas?)

- tracing type debugging
- gdb type debugging
- other representational debugging

At the same time usability is also key here.

The situation around 'c' is fascinating because it is in various ways 'still the least-worst option' for many situations,
but at the same time (e.g. see P.J.Plauger's 'insider' writings (and that was before LLVM!)) c was extremely confusingly dysfunctional even from early days, where how to use it or how use was not working was decade after decade elusive to even the 'top of the top' people who were using and writing it, and since then it has been strangely neglected: c courses, resources, package-libraries, tools, etc., are either non-existent or so rare that it is not obvious that c still exists at all, yet it is (e.g. the linux kernel) still both indirectly and directly critical to ~most (or many) real-world projects. E.g. Even in the 1990s (after c-89) Plauger was writing about how most software projects simply fail and no one can explain why - that is a significant problem and I suspect it may relate to 'static-analysis tool' vs. other feature focus.

Yes, it is convenient to have 'types' and 'functions' and 'packages' (sort of, even though most of the time projects fail and no one can explain how, to me that is not 'convenient' or 'elegant'),
but what if a development-framework (whether or not it is a "language") focused on performance and memory analysis and memory-safety static analysis? 

A possible example may be Mara Bos's 'Rust Atomics and Locks'
I have the impression that people want magic-abstractions to 'just make it all go away' when it comes to async and parallelism and concurrency: more glam-rock higher level abstractions to hide the underlying real life choices, but in reading that book it seems to me that Rust can do async safely, but there is no one-size-fits-all way that makes sense: each situation is different. However, there are so many factors that it is difficult AND there is no attempt (even in that book) to lay out the problem space and the tools (even if there are many of them).

Using assembly-language per-hardware rather than universal control-flow-abstractions and type-abstractions may be less fast and less easy on one level, but if instead there were a focus on testing and vetting functionality and memory-integrity in the program, then would there be slow and steady progress that did not mysterious explode into failure or hidden tech debt, rather than the 1970-2020 standard cycle of arm-waving-enthusiasm turning into bodies being hidden in the closet and never talked about again, with an inexplicable occasional unrepeatable success that is turned into a cargo cult (or "isomorphic mimicry" as the fancy people say). 






---

iGo, not Chess (illustrative vague analogy):
Avoiding the blinding psychology of obsessions with reified-abstractions. 

In iGo, you need to build functional configurations from low level primitives.

What are the 'rules' in this case? I am guessing this is focused around the semi-physical semi-logical parameters of "memory-safety", which I am guessing is partially well-defined, and partially conventional arm-waving that 'usually is fine' (but may not be fine here). E.g. if a 'memory model' pre-supposes an arbitrary ~symbolic framework that may be an artificial artifact mismatching a physical-memory-environment. 


Yes, people are 'thrilled' by the either the sportsmanship of chess or, more often, the hooliganism of chess, or, like the venerable Mondrian, the deliberate recreational abstraction of chess as 'art', this project is not meant to be a wastefully affectatious and ironic calvinist scapegoating of creative recreation. 

That said, the intended (who knows what will really happen) scope is to deliberately avoid chess-type high-level however-useful pre-defined 'abstraction-languages' and to primarily look at lower-level functional-configurations and the functional properties of functional-configurations.

'functional' may inadvertently be unclear here, as the term 'function' itself may be part of this soup:
- logic concept of function
- math concept of function
- algol-family concept of function
- church-haskel concept of 'function'

What I intend to mean by 'function' is to refer to an observed empirical outcome, a result of observed functionality, as opposed to an a priori declared framework of abstract definitions. As in definition-behavior studies and categories of types of systems (if that approach is at all useful) the attempt to focus on empirical phenomena may (if counter-intuitively) be inherently a "statistical" undertaking and a perhaps-different but largely familial type of modeling, where 'function-empirical' does not (declaratively) automatically jump to some root-language of reality itself (however much fundimentalist-types may salivate over that fantasy). 

It may be that while some might think this project is a minimalist low level bare-logic scope, it may be that this is inherently an intersection of statistics, data-science, and machine-learning (either symbolic or sub-symbolic) including a larger scope of automata, game-theory, information-theory, etc., with the previously dominant logic-linguistic-abstraction approaches. 

Nevertheless, iGo and physical memory are not superficially the same as operating on top of a 'clean abstract grammar' such as a c-rust-zig-odin 'memory-model' (as I understand it, maybe that is not correct).

It may be still unclear how to disambiguate this space:
'rules' for boolean logic or perhaps iGo can correspond to 'physical' constraints (or perhaps something like that, perhaps importantly not so simple), whereas high-level rules are both notably divorced from the 'functional' or 'empirical' phenomena and both allow for 'grammars of behavior' and also 'tendencies of delusional fantasy.' (How chess-itself usually results in games with no rule-based end 'players decide to just stop playing, because the game is fundamentally broken' and yet over thousands of years this ubiquitous behavior is itself taboo to point out to chess players who refuse to perceive it (and who would probably physically attack you for raising it (also the fate of journalists in ideological-extreamist-regimes)).)

A key focus here is the memory-safety (probably in need of clearer definition), performance, and other issues that have ravaged the STEM world while computer scientists with disdainful arrogance and supreme unconcern arranged the symbolic deck chairs on their titanic of high-level-languages: burning drowning suffocating plebians be damned. 


This is an exploration, not a presumption. Memory-safety (without garbage collection (which as Martin Kleppmann explains is a fundamental *cause* of (not prevention of) real world errors and memory problems at the network and application level (if not pedantically as the module level)) in the form of Rust, fil-c, and zig (if not contextually others) may be the best-only known route. 

But let's explore this problem space in case there are pragmatic experiments worth getting more data about.


---

The psychology of Chess vs. iGo:

abstraction-sport
vs.
functional assembly


What are the memory behaviors?
What does memory need to do?
What should memory not be allowed to do?

Maybe it is, but are 'value lifetimes' the correct model
for avoiding memory-violations?

---
'tokens...'

Models and memory
(data-science type 'model' types...)
properties of ...model-gramars?

...

optimization... without strict values or functions or set control flow options...



---


---

...

conditional compilation...

---

standard library

---

dimensionality... 

---


---

There are a lot of ideas here, the goal is not to arbitrarily combine them all, but to look for parsimonious functionality around specific functionalities (e.g. memory-testing for lower level control, supporting flexibility and performance; supporting static-analysis and memory analysis (if not run-time memory safety like fil-c, while more or less staying at the assembly language level; effectively supporting things like data structures and quasi-types, but staying non-abstract). 





---
..
rust example of modes and cases

A. the issue is not that modes are not hidden-built-in
it is that it feels like fighting against the language
to do something that needs to be done (not something that is optional)

B. Awa should not fight against handling modes and cases. 


..

Better name... (something that does not collide with normal terms)
Sometime that is somewhat meaningfully descriptive:

semble...
"Compsembler"
"protosembler"
"Comsembler"
Proto... "Proto" (collides with .proto)
primal... Shannon... Mathison... Stony... Applejack... ("Smells like almonds") 
Awa...
Pockets...
memory-state-assembly-management...
Globe-Theater
Sand


Language-Memory-State-Manager vs. 'compiler' 
Hardware-Memory-State-Manager
operations-memory-state-manager
operations_memory_state_manager

A Hardware-Memory-State-Management language and toolchain, not a "compiler".



memory-state-time-map

---

This is not meant to be a one-size-fits-all language.

This is meant to address one more area of, likely lower-level and or systems-programming oriented, software development that are especially precarious in 2026. 

---
Topic:

C's use of and need for the 'pre-processor'

e.g. around 1hr 38min
https://www.youtube.com/watch?v=ES5_IWG8rcw 

allows flexibility.. if too much? 'the curse of common lisp'


---

Schools of Thought since 1971:


1. Steve Gibson GRC: Program in Assembly-Language (still going in 2026)

2. J.E.Tomayako-G.Hopper: Socio-Psychology of Projects: Communication, Planning, Maintainability-Soundness-Sanity; project-type appropriate tools 

3. Small-Talk: High Level Abstractions are Primary/Exclusive; pro: anticipating many issues and concepts. ~Con: naively pushed to production while arguably not intended that way. This perhaps should be seen as a positive early-planning, brainstorming, R&D and pure-research approach, but not seen as a real-project management intent. This may be likened to the 'new age' section in bookstores where the open-ness to idea-discussion can be of value, but where open-inclusion being the goal for its own sake is not compatible with basic real project workflow overall (beyond the brainstorming phase) such as: make and deliver one MVP (not: try to explore every possible product and feature idea in an endless novelty loop).

4. Solo-Priestcraft: Unsocial, Anti-Social, culture of solitary developers who are primarily motivated by game-win-psychology events including extreme-aesthetics, extreme-minimalism, extreme arbitrary configuration specification, theological purity extremism, recreational obscurity for the sake of obscurity, for artificial job security, and in dysfunctional cycles of base boorish toxic bullying behavior. Cons include: having no concern for or concept of product-project management (teams, schedules, communication, goals, budgets, feedback, learning, learning from errors, long-term-outcomes, maintainability, etc.); domain or interdisciplinary study; willingness to use and hide resources-use for arbitrary ideological tasks; a tendency towards toxic-masculinity and institutional-capture. 



Various Recurring Issues since 1971:
1. cyber security
2. bloat
3. Unmanageable tech debt
4. poor IT project management: over-time, over-budget, over-promised & underdelivered, 
5. an astounding lack of educational and other resources (e.g. for C in 2026)

---
Learning Lessons from Languages, Trends, Fads, and Disasters:

Assembler/Assembly
Lisp ("the curse of lisp")
Fortran
c
cpp/c++
Java
HTML
CSS
PHP(?)
Adobe-Flash
LLVM
Java-Script
R
Python
Haskel
Kotlin
Lua
Go
Web-Assembly (wasm)
Rust
Zig
Odin
fil-c

---

Looking at c over time:

One way of looking at how in 2026 c is somehow simultaneously a completely abandoned unsupported language and also the primary language and dependency that nearly everything else is based on, built with, and relies upon, 
is that K&R C was not originally designed to be a Go-Rust type high level language (with mysterious hidden layers of compilation under an explicit primary layer of abstractions),

c did not have 'types' because in reality 'types' do not exist. The diagnosis of 'a lack of type strictness' might in some cases be a working-lie, but it is important to remember that 'types' are a high level concept that has no direct relationship with lower levels of concrete reality. The idea that 'the solution is always ever-more theologically strict enforcement of higher-level reified abstractions' should be a red flag, not a reasonable sounding policy. Case by case, this might fit a specific case very well, but this is not a good general approach to reality any more than mouth foaming coercive theological extremism is an acceptable proxy for participation in interconnected STEM projects (including trade and legal liberalism).

There are a number of conventions in hardware design in 2026 that did not exist in the 1960s and 70s (perhaps such as word-length, use of hex vs oct (base-32 was used at some points), endianism, etc.), giving c a flexibility that is arguably still in 2026 needed for real world uses (perhaps such as embedded devices, robotics, novel-hardware, GPU compute, etc.) that are not 'standard application development for a primary OS consumer products (where a 'high level first' language like swift or go might work).

C Preprocessor and Macros

---

What can be learned from Java?

 ---

Python may be a great example of a language that is extremely practical for a wide range of 'in the office' tasks (perhaps as bash was used in bell-labs) but trying to make a 'full stack python commercial product' is as insane as trying to make a fullstack bash-script commercial product. 

There is a case for a language for R&D, and language for a POC, being separate from a language for a big-team product, being separate from etc etc.

---

Memory-Management in terms of security-bugs and in terms of maintainability, 

---

Visicalc & Lotus 123

'developability'

It is a perhaps repeating tragedy that market-making world changing version-1 products that worked were followed by undevelopable, unmanageable, unmaintainable, unsustainable quagmire-projects or vaporware that either bankrupted the producer or were abandoned. 

On the one hand, high level features might not seem like the right discussion-scope here, but on the other hand, it might be appropriate.

Lots of software focuses on high-level user features and eye-candy which are not primary user-features. Arguably much of the internet is a 'pure art entertainment' bloat layer that is not needed for the nuts and bolts of more concrete functionality, and arguably is part of security issues and cost issues.

Version-1 Lotus 1-2-3 was written in assembly language, later versions tried to leap into feature-fantasy-expansion in the small-talk/abstraction world and turned into software development hell leading to extinction.

Another possible example is "windows-OS" vs. c-linux. 
c-linux is a working c tool chain (rejecting even C++ abstractions). 
"Windows" is a never ending nightmare of discontinuous insanity, 



---

Multics, Unix, Threads, GPUS, and Networks


---

Narrative/Thread:
What is 'bad' about programming in assembly-language (or, in machine-language)?

1. It is significantly cumbersome (not bad or wrong per se, but annoying, and the time it takes may be materially costly (at least in the short-term)). This issue may be nicknamed 'slow' overall, as encompassing learning curve, development time, planning time, communication time, etc.

2. It is error-prone without some kind of audit-tools. (This is the primary problem.) 

From the era of assembly language programming (slow, and error-prone) the world experimented with various languages and philosophies (e.g 'small talk' was arguably more a philosophy or set of philosophies rather than 'one formal language') until Perhaps 1990-2010, settling into a semi-equilibrium age of (roughly, usually) C++ style abstractions as a fundamental way of looking at what programming is:

That there are abstract control-flow concepts to be built-with like legos, with two schools of programmers:

- Math-Art Programmers
- Applied Engineer Programmers

While math-art programmers have certainly contributed to pure research and in other ways, their treatment here will be perhaps overly harsh:
Math-Art Programmers are schizophrenically separated from reality, they are fanaticists who seek to live in an entertainment-fantasy world of pure abstractions where they can spend infinite time and resources fetishizing and obsessing over abstract games and rules and purities and symmetries and clean-ness etc. 

Math-Art has had a disproportionate influence on applied programming, such that aesthetic debates in fun-time game-land have completely overwhelmed real world tasks and problems.

A mirror or perhaps symptom of this problem may be seen in Jeffrey Hinton's description of how sub-symbolic data-science was treated before Image-net-2012, 

https://www.youtube.com/watch?v=QWWgr2rN45o 
"Geoffrey Hinton in conversation with Fei-Fei Li — Responsible AI development," Arts & Science - University of Toronto
 
where there was an unbreachable fish-in-water invisible mindset (possibly from Minsky's hit-job book to terminate future research for neural-net research in 1969 "perceptron", until 2012) that happy magic 'symbol' abstraction land was the only possible primary reality. (Many people may not remember but in the 1980's we various branches of study were effectively abandoned and blacklisted, there was an overwhelming hubris that everything in the universe had been 100% 'finished' by a frat-boy version of simple symbolic science: done, solved, end of discussion, we-won, no more discussion. (And then after 2023 and Chat-GPT people started looking around for definitions of mind and intelligence and found that those departments were closed in the 70s and 80s.)

Proto-Type (or whatever the name ends up being, Awa) should be eternally vigilant against this kind of brain-distorting-addiction that will forever being trying to pull the human mind into vortices of complacent illusory insanity, walled in by potemkin villages of abstraction-candy.

Even with around 8 billion people alive in 2026, and ~most of them on the internet, the number of people (even within tech circles) who are aware of the GPU vs. CPU, memory-safety, async and multi-threading issues at a lower (assembly compiler) level are astonishingly low. A vast super-majority of people (even in tech circles) are like true-believe religious converts into a puppet-show world of attention-grabbing abstractions, with the vast vast majority of time and interest and concern spent obsessing over "cleanness" and IDE-configuration, and language-purity, and various aesthetic fixations.

As in the classic repeating cycle of people using a 'quick start' tool and then finding that the tool can not go 100% of the way in the project, the abstractions such as 'types' or 'lifetimes' or 'classes' or 'inheritances' eventually become barriers where there are disjunctions between the high-granularity empirical behavior and needs of the system and the cartoon-ified entertainment fictions that were created to babysit humans. 

3. Contexts:
As may be evident in a history-autopsy of the evolution and legacy of Small-Talk, context-specific use-cases are evolving and diversifying in a more Japanese-culture way rather than in an American 'One general absolute context to rule them all' way. Some areas of development and work may be completely fine for a given tool:
The COBOL world for making very specific programs on mainframes (such as Banking, the CS area my father worked in) was probably well defined by the inestimable Grace Hopper. Whereas the world of C for embedded systems even in 2006 as described by Holzmann was both more uniform (than 2026) but also less happy: he describes and tries to offer balm for a raging trainwreck among the top of the top of professionals. But skip ahead to the 2020's, and even for NASA the number of more or less distinct fields of software development needs has multiplied (e.g. Mars rovers running linux, not just micro-controllers, etc.)
From 'Systems programming' to 'frontend' to databases design to compiler design (LLVM appears likewise to be a raging dumpster fire that everyone equally "needs" and is horrified by, meanwhile there is more or less zero discussion about it as a high priority societal concern).

And as might be visible by looking into not only Hinton's work history but the evolution of compute-oriented and data-oriented Granmo-Automata-Machine applied machine learning: the landscape of compartmentalized disciplines has become an almost un-traversable expanse. Statistics, probability, Baysian, Frequentist, Sub-symbolic, Genetic-Algorithms, Quantum Information Theory, GPU-parallelism, CPU-ALU classic single threads, float-math-world, optimized graphics and high-performance compute (focused on narrow less-idealized maths and tricks), information-theory, game-theory, automaton-theory, "data-science", static-analysis, memory-safety, database-science, etc.  

Various approaches tend to emerge not only from within one village in the larger landscape, but within a conceptual and compatibility context of that village being exclusively all of reality, so we keep seeing events and kludges such as in 2011, the best of the best and the top of the top laughing at Jeffrey Hinton and telling him that sub-symbolic statistics can't possibly exist, because everyone of course knows that the world is made of fun symbolic abstraction legos. Duh!!! Silly Hinton! Then in the 2020's people in business and government are spending trillions of dollars investing in floating-point-math compute using 'textures and shaders' for... video-games, and are doubling down on a system so inefficient that a single math-task not only cost 15-20 million dollars but that even after that was a jumbled inexplicable 'solution.' Granted, this is an especially extreme example, but it shows how far the status-quo has drifted from the days of Jean Jennings Bartik & the ENIAC-6 or Grace Hopper pulling out a coil of wire to show engineers how unacceptable it was to waste a nano-second (and how unthinkable to waste a millisecond! (and getting the reward of wearing a 'millisecond-coil' around your neck (a possibly lethal proverbial punishment)) 

https://www.economist.com/science-and-technology/2026/09/11/top-mathematicians-are-outraged-by-openais-methods 

https://www.economist.com/international/2026/09/15/agreeing-to-make-ai-safer-may-be-impossible  



```
The company marshalled some 10,000 AI agents to work on the Navier-Stokes problem. The agents worked for 88 hours, using around 130 billion output tokens, or units of text and characters generated by the model. According to OpenAI's pricing for its most advanced publicly available model, the solution to the Navier-Stokes problem cost the company somewhere around $6-$10 million to compute. (Overall, the company says it used 300 billion tokens, closer to $15-20 million, looking for solutions.)
```
https://www.npr.org/2026/09/22/nx-s1-5968588/openai-navier-stokes-problem-mathematicians-learn-little 

As one more example, in the swirl of events around C, Rust, Zig, memory-safety and the 'Bun-rewrite' from zig-to-Rust, and the discussion of adding significant memory-safety to Zig, even for the extremely narrow-nerdy-expert discussion (including Filip Pizlo (the creator/maintainer of fil-c and andrew kelly the creator/maintainer of Zig themselves) there is no discussion (in those threads) of the nascent state of fil-c regarding compute-expense (e.g. people are talking about an unoptimized pre-alpha process as if it were a decades old optimized process). That might sound like a persnickety point, the topic of the conversation was literally the compute-expense of the approach. 

 
"introduce a fully memory safe (no escape hatches like in Rust) compilation mode inspired by Fil-C #36237
opened 2 months ago by andrewrk · 32 comments"
https://codeberg.org/ziglang/zig/issues/36237  

"Purely Technical Discussion: Memory-Safe Compilation Mode Inspired by Fil-C
Explain language"
https://ziggit.dev/t/purely-technical-discussion-memory-safe-compilation-mode-inspired-by-fil-c/16813  

Attention to compilers such as by matt godbolt https://godbolt.org/

CppCon 2018: Matt Godbolt “The Bits Between the Bits: How We Get to main()”
https://www.youtube.com/watch?v=dOfucXtyEsU 

It is admittedly a bit niche, but it is more than just a bit niche. It is completely off the radar even for projects like Rust, Zig and Odin that are fundamentally compiler projects and yet only after a decade in retrospect is that realized by the authors of the project. 

I am not trying to criticize Ginger Bill Hall, Andrew Kelly, Graydon Hoare, or Filip Pizlo, I am trying to illustrate the depth of the problem that these pioneers are trying to dig society out of. 

As one more example: 1991 is a fascinating time period. Not only is it the fiasco of Bell-Labs, Berkley, Unix, BSD, and Linux setting the stage for the future, but it was also the time period (give or take a year) that J. E. Tomayko (also NASA et al), help and published the proceedings of the SEI conference on software education, where the overwhelming theme was communication-confusion about project goals and trying to apply a sea of abstractions, and when P.J.Plauger (author of the original Prentice Hall book on The C Standard Library (and more or less a contributor to C from the early days)), published his updated essay and article collection as "Programming on Purpose" in which he flatly describes the mainstream philosophies of software practice and management, which he also constructed and taught, as "snake oil" (that he realized were utterly useless word-salad when he later tried to put them in practice). In other words, it has been in-writing, by the top authorities in the field since 1991 that the paradigms of software development are in terminal crisis of dysfunction. Fast forward to 2026, and the name of the game is still pushing Plauger's "Snake Oil."


I could go on and on, but the point is that in 2026 the international society is over its head in tech-debt and over-due homework reading.

To return to the start of this thought-thread:
1. Assembly language programming is (too often) too slow.
2. Assembly language programming is (too easily) unsafe.

But, 'Snake-Oil' ideology-abstraction based C-era programming is:
1. too unsafe
2. too unmaintainable
3. too inefficient


So our challenges are: 

A. Is it possible to design a 'programming-language-ish-tool-set' that can at least do a decent-enough job of connecting enough of these disparate areas and real-world concerns for at least one domain of software development for which the symbolic-reification-paradigm is not adequate? 

B. It is possible to cover more than one (sub sub) area of software development?

C. Is it possible to design a 'language-ish-tool-set' that is usable-enough by enough of the many diverse domains of [relevant] software development?

Such that teams can design and implement reasonably
- maintainable (not like a python-dependency-chain tech dept explosion)
- cost-economic (not using inefficient bloated computation) 
- memory-and-security-audit-able (not full of annoying glitches and unsafe vulnerabilities)
- concretely coherent (not trying to favor or kludge an ideology over an ill-fitting reality)
adequate software? 

---

Let's look both back to the days of the ENIAC-6, where they had different types of optimization options, to the ethos and lessons of Grace Hopper, and to the later lessons-not-entirely-learned from 1971-2020 about memory management, bloat, security issues, static analysis, async-needs, GPU vs CPU, etc.

Let's try to map out enough of the different programming problem spaces to be clear about what is and is not defined into this intended scope: what specific needs and functionalities are we aiming for here?



---


Types made of proto-type primitives oriented towards:
1. fil-c type memory compilation optimization and checking
2. memory-testable definition-primatives
3. per-hardaware-architecture optimization
4. gpu, async
5. defined down to bit level
6. q-bit compatible
7. Oriented around assembly language...
8. A skeleton-language around assembly
9. primarily stack oriented (probably eventually with heap support)
10. bitwise oriented...
11. error-correcting-code oriented

12. static analysis oriented
13. information-theory oriented


Q: could thread-id be defined into the test-properties of the data.
(focusing on stack)

...

managing registers

managing side-channel attack cpu-prediction
managing optimization-issues due to cpu-prediction 
(e.g. see https://github.com/lineality/tunnels/tree/main/udp_pingpong_6 

...

not abstract-it-all-away architecture-agnostic, it is architecture flexible, probably back to having specific clear compilers (whatever that means in this context) for a specific architecture (not: "throw it all at LLVM and who cares! Party time because now it's someone else's problem!!")

...

not 'garbage collection' no no no
as Martin Kleppmann clearly explains in "Designing Data-Intensive Applications", garbage collection is a primary cause of problems and errors in databases and other systems (this is a book that supposedly everyone has read, yet I have not met or heard single person who does not automatically assume databases have to be garbage collected: because "that's how we've always done things," so... that's the only possible option (See Grace Hopper's thoughts on that phrase.)

https://www.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/ 
...



1.
Rethinking (rejecting) some of the control-flow concepts that reification-fetsh-oriented people are addicted to, but that either lack evidence of effectiveness or show contraindicating evidence (term?)

e.g. not trying to solve concrete problems with reified abstractions that punt the problem or hide it

2. 
Introducing fundamental aspects that probably in the past were not considered 'primary' concerns:

- Information-Entropy 
Possibly: Transfer Entropy (TE)
Mutual Information (MI)
Conditional Mutual Information (CMI)
Directed Information


- Telecommunication signal-sending

- network concepts...

- async concepts?


---

Instead of 'after the fact' trying to 'unroll loops' for the 'loop-abstractions' that you were corralled into making,
of needing to replace control-flow branches with branchless bitwise operations (for security and for basic optimization-sanity) that are clearly not what the language was designed to corral ~data-structures into.

Or coming up with exotic 'workarounds' to replace the floating point operations (you were corralled into doing) with un-natural seeming operations.

etc.

These concerns should be the native, natural primary reality of computer science, not unspeakable mythic ghouls that most people never are aware of and that a brave few contort the 'snake oil' tools to be able to less-badly-manage. 

Can these concerns be made primary, with tooling design specifically to anticipate and handle these.

---

Another example may be the strange unix decision to make the otherwise brilliant unix-epoch a single reified signed 32-bit value (e.g. as opposed to be a modular-array of bytes (or nibbles)). (and then there's the utter insanity of windows-OS being stuck at a past year and adding ever-more days to December, with a patch-over to convert to reality-time (note: source: security-now Steve Gibson)).

The idea that time must be a signed integer without any thought about if that makes sense (in... time), may illustrate how people myopically embrace the nearby life-preservers of abstractions without any plan or strategy for the future.


---

The flexibility of K&R C, without strict types or defaults such as UTF-unicode handling (which did not exist in the 70s, 
https://en.wikipedia.org/wiki/UTF-8 utf-8 didn't come out until 1989 (where as c-89 is often considered to be ansi-c completed)) or conversion of word-size etc., is often described as a mistake or as unnecessary. But this might not be the right lesson to learn. The 'problem' with K&R c might not have been that they did not hard-code conformity to arbitrary future conventions.

Likewise, people in the 2020's talk about c not being 'type' strict, in a context of assuming that memory-safety requires abstracting specific theoretical 'types'  


---

Re-thinking how 'types' are defined, e.g. going away from the cpp/Rust direction of elaborate type-abstraction, staying closer to K&R-C, and defining the memory-safety of that workflow directly without the abstraction-overhead of architecting a fashionable type-land doll-house. 


- probably re-thinking the various abstract types of branches 
(whiles, loop, for, etc.)

- probably re-thinking the various abstract types of branches
if, switch, match,


- probably keep proc/fn
- probably keep input-library/package functionality (Odin might be a good model for directory-based packages)
- maybe enums are a good idea...

- arrays might still be primary...

...

Like with COBOL, C & C++ might have entirely made sense for UNIX-Bash (posix-shell) day to day operations for big institutions using mainframes and only a few STEM experts using them. 

But the software world more generally and broadly should be more clearly map-able in 2026, and that previous era of imperative and procedural language abstractions is no longer suitable. 


...

Information theory oriented perspective on 'control flow'



...

static-analysis (if interpreted more broadly to include even more types of similar analysis) may be one of the core insights of Holzmann (Gerard J. Holzmann 2006, NASA/JPL Laboratory for Reliable Software),


...

CHERI is likely seen as a counter-example (at least overall) in terms of requiring specific hardware (as I understand it).


...

"Ginger" Bill (Hall)'s comments on 'ergonomics' (e.g. in his comments about Rust's design and evolution putting too little time and effort into usability, and or in his design for Odin being oriented towards the '90' in 90/10 splits of what people will be doing, should be noted but not followed.

Perhaps like Rust this Proto-Type language is (as a very experimental experiment) oriented towards experimenting with what can be done, not on how easy it is to use.

But saying that ergonomics is not primary (as it arguably was for Odin) is not saying that it is an anti-priority. It is entirely possible that due to its strange and extra-low-level nature 

...

Note:
a focus on stack does not mean excluding heap,
but initial scope and priority is stack.


...


compiler-control oriented...

more of a modular-compiler-maker?


Trying to follow the idea of K&R-C in some ways (so maybe like Odin), but...

Favoring 'branchless' architectures


- not using normal control-flow
- not using normal types



it might be that "types" are strange and approximate


---
"meta-assembler" 
'programmable hardware description language' (Chisel, SpinalHDL)

CUDA vs. SASS (Streaming ASSembler (SASS) is the assembly format for programs running on NVIDIA GPUs)

---




Something to look at: 
c interoperability... in the sense of the larger c ecosystem
(ability to save projects as c-library?)


---

?"geometric bit-constraints"

allow a larger toolkit for managing 'types' in various kinds of more specific situations

- consumable data 
- single transform (consumable)
- immutable... array?
- 

---

policy on pointers...(pending) 
(probably takes some digging into c, odin, zig, and memory-mapping to see... how to be both flexible and auditable...)

(maybe)
1. flexible ways of using pointers is ok
2. ways to do 'static-analysis' and memory-behavior auditing of pointers is a key point.

---

Note:
Rust vs. Holzmann-c

Some of the restrictions and guidance of c, in a context of Rust, disappear in that memory-management tools may preclude a mass-trunction of the language in order to avoid potentially unsafe ranges of behavior. 

---

'Undefined behavior'

Based on what "Ginger" Bill Hall says, "undefined behavior" has many different contextually specific definitions. 

So it may be a number of different important topics.

"Deciding the fate of C Language" Wookash Podcast
https://www.youtube.com/watch?v=ES5_IWG8rcw 
- ~1:42min psychology of languages
- 1:45min undefined behavior (unobservable vs. undefined; undefinable vs. incidentally undefined; platform-specific behaviors; memory-model-violations ('illegal behavior'); memory-optimizations based on specific memory rules; )


---

From the description of Jane Street's language: OCaml
https://ocaml.org/about 

"Programming languages matter. They affect the reliability, security, and efficiency of the code you write, as well as how easy it is to read, refactor, and extend."

(I have not delved into Ocaml and I am not trying to criticize it here, I just thought this was a very nice sentence to echo.)

Ideally we can challenge some of the apparently misguided views and conventions about what makes a language and coding style "easy to read" and maintain.

Often 'easy to read' falls into an ideology that is does not try to refer to or include an understanding the memory-state-dynamics of the code:
- "Clean Code"(TM/CR)
- OOP
- Micro-Service Organization
- No-Comments
- Cryptic Terse Names
- Purely aesthetic syntax formatting
- One-liners wherever possible
- Arbitrarily as many 'as small as possible' micro-functions as possible
etc. 

And tautologically, if the 'nice to look at' attractors that people have following have led ever-further into tech-debt, then they are bad proxies for 'perception-understanding.'

Languages do matter, as the Jane Street line reads.
It may be too grand of a goal, but the ideal here is to create a "language" (compiler-assember tool-kit) that will facilitate an understanding and appreciation for what a given function/procedure is doing, for what a given 'value' is and is doing. Instead of hiding everything with eye-candy lipstick.

A possible example (maybe) of this is the Malcolm Gladwell, essay (can't recall which book) about the effect of different ~number-languages (my term, not his) on how people learn and use maths. Roman Numerals are romantic looking but horrible for maths. The English Indo-Arabic system is better, but there are a number of notable snags and kludges such as the teens and how fractions are described. Some Asian adoptions of the Indo-Arabic system are, like better programming languages, have 'less baggage that gets in the way' and help students to learn more quickly and perform better.




---


Another common anecdote I heard:
There are innumerable stories about people having bad experiences with a C course at uni (often that turned them away from coding and CS, sadly). One of these that I think is emblematic of many, if maybe unusually blunt, is the story of the person recounting telling their professor that they were having trouble getting the class assignment code to compile, and the teach dismissively instantly ended the discussion saying: "That's not a programming question, that's a compiler question. I don't care about compilers."

There are so many stories packed into this simple anecdote that probably many (perhaps most people in CS) can relate to from some experience. 

The idea that the compiler is unrelated to how the program works arguably was a goal of the 'programming through pure abstractions' paradigm (maybe 1980-2020) (though arguably K&R C for a PDP was more compiler aware in the early-early days). And that approach might have worked, but we now have enough evidence to say that 'programming through pure abstractions' does not work, is not effective, and leads to problems perhaps like economic abstractions when markets become divorced from accurate price signals (from bonds to goods to wages etc). People in the madness of crowds fall into cult obsessions with fictions and separation from reality ends badly.

A 'language' should help people to understand the memory-state-workflow of what is happening. People should understand what a 'value' or a 'lifetime' is in the context of what is happening and (as it may be different) what needs to happen. Language should not be invisible, but should help to understand both reality and the representation of reality. 



---
meaningful error messages:
I absolutely love cargo and the rust-compiler error messages. Having clear-accurate memory-informative messages is so valuable.



---


Ability to design modular systems, e.g.
multiple 'programs' in the same ecosystem operating independently (e.g. ant-swarm IOT network devices, e.g. swarm-database)

where various chunks of the modular system can be "statically analyzed" the way one "program" would be analyzed within Rust, fil-c, etc.

A tool maybe more oriented towards embedded systems than towards "scripting high level windows-OS apps" 

---

Idea/ideal:

The idea of having some kind of 'flow-chart' type tool in some way,
e.g. 

A. where a result of a static-analysis audit is a human-readable state-memory-map-flow-chart where functionality and disfunction can be examined.

B. As a design-guide tool, e.g. two flow charts
1. Goal Flow Chart
vs.
2. Current Flow Chart

Used to bring the current to be close enough to the goal.



---

trinary logic compatible?


---

qbit oriented?


---

System-State-Flow-Chart

---

Control-Flow-Functionalities

Common control flow abstractions such as while, if, for, etc.
in Awa-Compsembler may be more like functions/procedures (fn/proc) themselves:


as a possible illustrative semi-counter-example:

Imagine writing a function (or impl-method) for Rust using naked-assembler for some specific kind of bitwise "branchless" operation.

Rust is a positive example here in that it allows naked assembly language to be part of the code, 
but also a negative example in that an unsafe-block breaks the memory-audit. 

---

Errors, Modes, and Cases:
https://github.com/lineality/modes_and_case_handling/blob/main/mode_case_handling_framework_summary.md 

Mode and Case handling is a particular obsession of mine, and is largely based around a few key concepts (and notable terminology issues) in the 2006 Power of 10 ideas.

I want to explore whether mode and case handling cannot be more primary/primitive/fundamental in the language. 

For Rust, trying to create any systematic way for handling tautologically required modes and cases raises an important issue: to me it seems inexplicably perverse that it is so difficult to contort Rust into being able to do what, arguably, everyone MUST be doing. That seems fundamentally broken. 

Awa-Compsembler should have better native support for mode and error handling. 

This does not mean a one-size fits all system, there are various design decisions that are per-project. 




---

Types & Declaring/Setting a Variable

"type"
"datatype"
"value"
"variable"
data-memory-modes? / value-memory-mode? / variable-memory-mode?
(var-mmode?)

Q: operator, operand?


There may be 'default "data-types" '

Maybe having memory-modes rather than 'data-types'?

standard data-memory-modes / value-memory-mode

Is there a common set of properties for a value?

1 constant or not
2 value-mutable or not
3 memory-size-mutable or not
4 atomic or not?
5 thread-shared-or-not?
6 pre-compiled or not
7 lifetime-type:
- one function
- whole program
- 
8 Memory-clearing
9 encrypted-values


something about memory tracking?



---



packages... maybe more diverse?

packages vs. modules?

---

1. unique ID for package-crate ("crackages", that's a joke, I vote for: "modules" as descriptive)
1. Defining compiler (not standard)
2. package-imports? / modules?


---
"Data Structures"


---

'The Standard Library'

maybe more than one thing



---

arguably it is too ideological to have the language disallow any heap, but it should help the programmer-team to properly manage what is stack and what is heap. e.g. it might make sense to have 'done once' 'bootstrap/unstrap' processes make use of heap (maybe easier to clean too, as finite terminating processes) where as 'high frequency loop' type operations arguably should not use heap for a variety of reasons.

Rare edge-cases might also be a case for heap. If an event happens 1:1,000,000,000 times, and it makes sense to use heap for that case, then that should be fine (again, a finite single terminating event, not an unbounded process).

---

Designing processes to run either as an operating system or without and operating system (as is described in "Rust in Action" By Tim McNamara), is probably something that should have more use-cases (from dedicated servers or serverless endpoints, to network devices, etc.) but the engineering difficulty and the mis-match of tools for that makes what should be a primary use-case type into a mythic future mirage. 


---

...
Memory-clearing
memory-protection

encrypted-values

...

Logging:
- exit-codes
- error-codes

Another thing that should maybe be more native/primary is logging.
Even a micro-controller will often have some kind of malfunction-behavior (blink a light or something)


...
holzman:
- always on-loops

...

sub_routines

subrout/proc/fn 

property of functions:

retry_or_noretry



...

Try to avoid 'adding a feature' 
vs.
making proto-meta-tools so that people can make their own features...

---

possible approach:
focusing on memory-auditing tools for assembler,
rather than building 'stuff' on top of that just for the sake of doing so.




---



"Deciding the fate of C Language" Wookash Podcast
https://www.youtube.com/watch?v=ES5_IWG8rcw 
- ~1:42min psychology of languages
- 1:45min undefined behavior (unobservable vs. undefined; undefinable vs. incidentally undefined; platform-specific behaviors; memory-model-violations ('illegal behavior'); memory-optimizations based on specific memory rules; )


"Advice for Writing Small Programs in C" Sean Barrett
https://www.youtube.com/watch?v=eAhWIO1Ra6M 

https://www.youtube.com/watch?v=Au9LBqG5IHg 

..

maybe a side issue, or maybe more important,
I was curious about what FIlip Pizlo said about Rust panics being 'safe' 
E.g. memory based exploit attack vs. the satellite falling out of the sky because the software halted vs. can a panic/unwind ever be part of a chain of attacks? (no?)

...

# Not For:
- Rapid Prototyping
- High Level Scripting
- Recreational Math-Art
- Super High Speed 'move fast and break things' / Move Fast and Generate Tech-Debt Quickly
- Kludge & Hide It
- High Level Ideology
- Small-Mid Systems Programming niches where existing tools are already perfect.


# More For:
- Low-Level: fine control over low level, possibly micro-managing machine code.

- small-device-level: small-scale resource constrained single devices (micro-controllers)

- IoT-Network-Level: networks of small devices

- Unusual Projects with specific needs

- Advanced async, parallel features (maybe)

- 'Larger' scale systems programming where the standard tools create an obfuscating interface with the system: where memory-audit analysis and memory-safety matter and are infeasible in standard languages.

...

Idea:

Making threads primary, instead of making subroutine-procedure-functions primary.

There is no single 'main' that is both main-thread and main-function.

or...

be even more direct...

Are there hardware oriented aspects of processes more fundamental than 'threads'?

What determines this?

(note: I think concurrency isn't multi-core define... the whole parallel vs. concurrent vs. async topic seems ever obscure)

ALU... GPU... CPU...

Endian-ism... 


e.g. 
could 'protocol' and 'signal' maybe be a better 'model' e.g. in the sense of having a modular 'process' running on several devices and in each device over several cores, as a work-performing memory-state auditing whole?


Q:
While decentralization might make the 'overall process' non-linear in some ways, there should still be able to be a memory-protocol/memory-model (term?) that allows for restrictions against specific undesirable behaviors while perhaps not entirely defining the limits of what is permitted... maybe.

Possible analogy: billiard balls and ants can be bouncing around on a table in a non-linear decentralized way, but still following protocols that prevent the fabric of physics from being torn apart: the non-linearity is still 'fabric-coherent' however unpredictable in other ways. 

---

Possibly ideas a simple as assigning a unique identifier to various 'aspects or items' related to low-level-memory-state-over-time
to track items and properties more directly, rather than trying to cpp/Rust style define super-elaborate 'custom types' at a high level

note: this could extend down to the various ways that memory is stored, often in redundant patterns not as literal single on-off values,
which...might also open up flexibility for quantum/trinary compatibility.

(note: the strange optima between base-2 and base-3, 
where a fractional-base might either sound odd or... maybe just be a terrible idea.)

---


## Data & Computation:

The terms 'matrix' and 'tensor' are often used simplistically without reference to the domain and optimization specific implementations that are more of a diverse topic than a single 'thing' (as an integer 2d cartesian graph may be more singular).



maybe tangent, maybe not:

Granmo Automata-Machines & Compute-Memory-Language Echo:

'high performance compute'
standard methodologies:

- no-float tricks
- binary linear algebra
- no float linear algebra
- trick-suites
assorted math-tricks e.g. for game-graphics: e.g. trying various approximations and shortcuts first that often work: 
- control-flow and data-structure choices

---

Debuggers?
Role of tests?
Tiger-beatle style testing?



---

completely de-emphasizing 'reuse-ability' and 'dry' in and of itself.

Implementable-Performance first:


...

Imagine something kind of like K&R-c, with a memory-auditor (including informative messages) like rust-cargo/fil-c, but that instead of covering the assembly with quasi-types (again: type-abstraction was not the goal of K&R c) and a fixed-set of control-flow ~sub-function abstractions that were too far from how the hardware worked (e.g. branched[logic branches] vs. 'branchless'[logic branches]), that this new-imagined K&R-c (or odin-c) is a development framework that allows:

- management of packages/libraries/modules
- separation of modes: test, debug, production-release
- gives test, debug, and ~compilation-error/warning feedback
- and provides a 'standard library' tool-set of commonly used elements and patterns that are well-vetted

(The term 'compiler' may be unclear here, as we are not trying to abstract the compiler away, but make a kind of 'exposed write-compiler' framework that has no fully-abstracted-language above it. So maybe there "is no (separate) compiler," or maybe this is a compiler. (or maybe it doesn't matter... or maybe it does.)


---

for me, Rust is my go-to-language

I do not care at all about 'beauty' or 'fun-ness' as vague objections to rust: I only care about the sound-ness of the resulting code.

But:
A. maybe: Most features of it I don't use.
B. specific (no-heap) memory management is an area where Rust 'gets in the way' (hinders rather than supports what needs to be done)
C. Mode and case handling is an important area where Rust 'gets in the way' (hinders rather than supports what needs to be done)
D. That assembly breaks the memory-safety is a total failure (in this context)
E. inflexibility: There are too many 'brick wall' edge cases where Rust cannot be used for 1. embedded systems and 2. maybe projects that involve other libraries etc. (maybe example: for aws-lambda function Rust is native-supported, but for azure serverless functions there is only unofficial 50-page-length insane work-around rough-notes-docs on random websites to maybe-sort-of-sometimes allow to Rust to work-ish) 


There are no hard ideological requirements or taboos here; there isn't anything that a solution has to use or has to not use: Can anything, can something, be tested and tried in this space?

- A restricted but still usable set of operations that can be memory-inspected? Sure.
- using language definitions, or not? Sure.
- Only useful for specific cases? Fine
- Ugly? Fine.

---

For lack of better terms ('compile', 'run', 'safety',)
defining 1. 'compile time' memory safety and 2. run-time memory safety, may be a necessary or sufficient starting place.


Does something need to cover both? No.
But both should be explored.

There may be cases that are impossible to 'define' at/during compile-time, but that can be safely managed at/during run-time. 

---

identifying memory-boundaries and bounded-memory-identities?


---
Possible use-case:
~ribbon type calculation and large/unbounded value handing

e.g. E.g. astronomy with extremely large numbers that cannot be handled in a lossy-way

---

Is 'call-stack-recursion' an issue with a bad-implementation of recursion? (vs. a fixed-state-recursion)


---

AST or Graph structure for memory-structure?
DAG

or specifically not those directions?

...


# See:
- Marc Loy's 'Smaller C'
- 1978 'K&R C' TCPL
- 1990 Plauger "The C Standard Library"
- 1991 Plauger "Programming on Purpose"
- 1991 J.E.Tomayko SEI
- 2018, Granmo
- 2021, Rust in Action, McNamara
- 2026: Zilyinski (The Odin Programming Language)

- https://godbolt.org/
- https://en.wikipedia.org/wiki/Compiler 
- https://github.com/nicbarker - assembly structure-editor



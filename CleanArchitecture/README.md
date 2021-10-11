# Clean Architecture

This file summarizes my notes from the Clean Architecture book.

### Index
1. [PART I - Introduction](#part_1)
   1. [Chapter 1 – What is design and architecture?](#chapter_1)
   2. [Chapter 2 – A tale of two values](#chapter_2)
   
2. [PART II - Starting with the Bricks: Programming Paradigms Paradigm Overview](#part_2)
   1. [Chapter 3 – Paradigm Overview](#chapter_3)
   2. [Chapter 4 – Structural Programming](#chapter_4)
   3. [Chapter 5 - Object-Oriented Programming](#chapter_5) 
   4. [Chapter 6 - Functional Programming](#chapter_6) 

3. [PART III - Design Principles](#part_3)
   1. [Chapter 7 - SRP: The Single Responsibility Principle](#chapter_7)
   1. Chapter 8 - OCP: The Open-Closed Principle
   1. Chapter 9 - LSP: The Liskov Substitution Principle
   1. Chapter 10 - ISP: The Interface Segregation Principle
   1. Chapter 11 - DIP: The Dependency Inversion Principle
 
4. PART IV – Component Principles
   1. Chapter 12 - Components
   1. Chapter 13 – Component Cohesion
   1. Chapter 14 – Component Coupling

5. PART V – Architecture
   1. Chapter 15 – What is Architecture?
   1. Chapter 16 – Independence
   1. Chapter 17 – Boundaries: Drawing Lines
   1. Chapter 18 – Boundary Anatomy
   1. Chapter 19 – Policy and Level
   1. Chapter 20 – Business Rules
   1. Chapter 21 – Screaming Architecture
   1. Chapter 22 – The Clean Architecture
   1. Chapter 23 – Presenters and Humble Objects
   1. Chapter 24 – Partial Boundaries
   1. Chapter 25 – Layers and Boundaries
   1. Chapter 26 – The Main Component
   1. Chapter 27 – Services: Great and Small
   1. Chapter 28 – The Test Boundary
   1. Chapter 29 – Clean Embedded Architecture

6. Part VI - Details
   1. Chapter 30 – The Database is a Detail
   1. Chapter 31 – The Web Is a Detail
   1. Chapter 32 – Frameworks are Details
   1. Chapter 33 – Case Study: Video Sales
   1. Chapter 34 – The Missing Chapter
   
# <a name="part_1">Part 1 Introduction </a>
## <a name="chapter_1">Chapter 1 What is Design and Architecture?</a>

- Apparently, there is no difference between design and architecture
- 'Architecture' is used in high-level context, whereas 'design' is used in low-level context. But both are part of the whole software design
- The goal of software architecture is to minimize the human resources required to build and maintain the required system
- The best option is for the development organization to recognize and avoid its own overconfidence and to start taking the quality of its software architecture seriously.


## <a name="chapter_2">Chapter 1 What is Design and Architecture?</a>
-	Every software system provides two different values to the stakeholders: Behavior and Structure.
-	Behavior (a.k.a. Function): 
        *   To make machines behave the way stakeholders want, developed by programmers through functional specs and so on.
        *	Many programmers believe that this is the entirety of their job.
-	Structure (a.k.a. Architecture) – 
        *	This is software, invented to make things easier to change the behavior of the machines, hence “soft” (easy) + “ware” (product)
        *	Software must be easy to change, the difficulty should be proportional to the scope of the change and not to the shape of the change.
        *	Difference between the scope and the size of the change often drives the growth in s/w development costs.
        *	The more the architecture prefers one shape over the others, the more harder it is to fit the new features into the hardware.
-	Greater value
        *	For business manager, the functions (or the ability of the software to work) are of greater value.
        *	A program (that may not be working and yet) that has lower cost of changing to achieve the desired behavior is far more of a greater value than a program (that is working) that is far costlier to change to achieve the desired behavior.
-	Eisenhower’s matrix
        *	Software requirements typically falls in 4 
categories.
                *	Urgent and Important
                *	Not urgent and Important
                *	Urgent and Unimportant
                *	Not Urgent and Unimportant
        *	Behavior – Urgent but not always important
        *   architecture of the code – Important but never 
          particularly urgent
        *	Typical mistakes by business managers and developers is to elevate the items in Box 3 (Not so important, but urgent items) into Box 1 (Important, and urgent).
        *  	This failure leads to ignoring the important architecture of the system in favor of the unimportant features of the system.
        *	Dilemma for software developers is that business managers are not equipped to evaluate the importance of the architecture. This is what the software developers are hired to do.
        *	It is the responsibility of the software architecture to assert the importance of the architecture over the urgency of features.
-	Fight for the architecture
        *	Effective software development teams tackle the struggle for better architecture head on. 
        *	This responsibility doubles up for the software architects.
        *	If the architecture comes last, then the system will become ever more costly to develop, and eventually change will become practically impossible for part or all of the system. If that is allowed to happen, it means the software development team did not fight hard enough for what they knew was necessary.



# <a name="part_2">PART II - Starting with the Bricks: Programming Paradigms Paradigm Overview </a>
## <a name="chapter_3">Chapter 3 – Paradigm Overview </a>
-	Structured Programming
     *	1st paradigm to be adopted (not the 1st invented) was structured programming, discovered by Edsger Wybe Dijkstra in 1968.
     *	Structured Programming imposes discipline on direct transfer of control.
-	Object Oriented Programming
     *	Discovered in 1966, by Ole Johan Dahl and Kristen Nygaard.
     *	Object oriented programming imposes discipline on indirect transfer of control.
-	Functional Programming
     *	First to be invented among the three, it is a direct work of Alonzo Church, invented Lambda calculus in 1936, it is foundation for LISP language.
     *	Foundational notion of Lambda calculus is Immutability – that is, the notion that the values of symbols do not change. Functional language has no assignment statement.
     *	Functional Programming imposes discipline upon assignment.
-	Food for thought
     *	Each of the paradigm removes capabilities from the programmer.
     *	The three paradigms together removes the goto statements, function pointers and assignment.

## <a name="chapter_4">Chapter 4 – Structural Programming </a>
- Proof
    * Dijkstra proved that all programs can be constructed from just three structures: 1) *sequence* 2) *selection* 3) *iteration*.
    * The very control structures that made a module provable were the same minimum set of control structures from which all programs can be built. Thus structured programming was born.
    * How Dijkstra tackled the proofs for 3 structures?
        * Sequential statements - can be proved by simple enumeration by mathematically tracing the input of the sequence to the output of the sequence.
        * Selection statements - Reapplication of enumeration, Dijkstra enumerated each path of the selection.
        * Iteration - Dijkstra used induction here. He proved case for 1 by enumeration, then he proved case for N+1 by assuming that the case for N is correct. He also proved the starting and ending criteria of the iteration by enumeration.
- Functional Decomposition
    * Structural Programming allows modules to be recursively decomposed into provable units, which in turn means that the modules can be functionally decomposed.
    * Each decomposed function can be represented using the restricted control structures of the structured programming.
- Proofs
    - No programmer tried to prove functional decomposition through laborious mathematical process, instead all relied on scientific method.
    - Mathematics is the discipline of proving provable statements true. Science, in contrast, is the discipline of proving provable statements false.
- Tests
    - Digkstra: "Testing shows the presence (not the absence) of bugs."
    - A program can be proven incorrect by tests, but cannot be proven correct through the tests.
    - A program that is not provable, cannot be deemed correct no matter how many tests are applied to it.
    - After decomposing the program into smaller provable functions, we can use tests to try to prove those small provable functions incorrect.
        - If such tests fail to prove incorrectness, then we deem the functions to be correct enough for our purpose.
- Conclusion
    - It is this ability to create falsifiable units of programming that makes structured programming valuable today.
    - This notion of functional decomposition is of very importance when defining the software architecture.
    - At every level, software architects strive to define the modules, components, services that are easily falsifiable (testable).
    - To do so, they employ restrictive disciplines similar to structured programming albeit at much higher level.
 
         

## <a name="chapter_5">Chapter 5 - Object-Oriented Programming </a> 
- The basis of a good architecture is the understanding and application of the principles of object oriented design.
- OO is the proper admixture of *encapsulation*, *inheritance*, and *polymorphism*.
- Encapsulation
    - OO languages provide easy and effective encapsulation of the data and function.
    - C language provides high level of encapsulation by dividing the data members and functional methods between *.h* and *.c* files.
    - Modern languages sort of broke that notion of perfect encapsulation
- Inheritance
    - It is simply redeclaration of a group variables and functions within an enclosing scope.
    - This was easily but manually achievable in C language.
    - OO languages made it more formal about inheritance.
- Polymorphism
    - Polymorphism is the application of pointers to the functions.
    - Programmers have been using the pointers to functions to achieve polymorphic behavior.
    - However, such pointers to functions behavior is quite dangerous as it just hits at having a good intent but not a strong mechanism to ensure the correctness.
    - OO languages have made it much safer and easier to use the polymorphism.
    - The power of polymorphism
        - Before OO languages, the polymorphism helped in achieving the device independence via plugin architecture.
            - i.e. device drivers (which implements conventional contract) can be plugged into the main source code, and the source code would work with the device seamlessly.
        - OO allows the plugin architecture to be used anywhere, for anything.
    - Dependency Inversion
        - In typical top-down approach of functional decomposition, every caller is forced to mention the name of the module that contained the callee.
        - However, due to polymorphism, these dependencies can be inverted very easily.
            - for example, a high level module could be pointing to the interface and another module could be implementing that interface. Thus, the module depends on the interface and it inverts the dependency relation.
        - With OO, any source code dependency, no matter where it is, can be inverted.
        - With this approach, the software architects gets the absolute control over the direction of all source code dependencies in the system.
        - This essentially gives the power to the software architects to make the dependency point in any desired direction.
        - With such a power provided by OO languages, the components can be developed and deployed independently.
    - Conclusion
        - For software architects, the OO is the ability (through polymorphism) to gain absolute control over every source code dependency in the system.
        - Polymorphism allows the software architects to create a plugin architecture, in which the modules that contains the high level policies are independent of the lower level modules.
            

## <a name="chapter_6">Chapter 6 - Functional Programming </a> 
- An important aspect of the functional programming languages
    - Variables in functional programming languages do not vary.
- Immutability and Architecture
    - All race conditions, deadlock conditions, and concurrent update problems are due to mutable variables.
    - As an architect, we should look out for robustness in the system that has multiple threads and processors.
    - Immutability can be achieved through compromises.
- Segregation of Mutability
    - Segregate the application in immutable and mutable components.
    - Architects must then push for as much work as possible in the immutable components of the application.
- Event Sourcing
    - It is a strategy wherein we store the transactions instead of the state.
    - When the state is required, we simply apply all the transactions from the beginning of the time.
- Given we have enough storage and processing power, we can make our applications entirely functional.
- Functional programming is a discipline imposed upon variable assignment.
- Software is composed of sequence, selection, iteration and indirection.

# <a name="part_3">PART III - Design Principles </a>
- SRP - Single responsibility Principle
    - Software modules has one, and only one reason to change.
- OCP - Open-Closed Principle
    - Software systems must be designed to allow the behavior of the system to be changed by adding new code, rather than changing the existing code.
- LSP - Liskov Substitution Principle
    - To build software systems from interchangeable parts, those parts must adhere to a contract that allows those parts to be substituted for another.
- ISP - Interface Segregation Principle
    - Software designers should avoid depending on things that they don't use.
- DIP - Dependency Inversion Principle
    - The code that implements high level policy should not depend on the code that implements low-level details. Rather, details should depend on those policies. 

## <a name="chapter_7">Chapter 7 - The Single Responsibility Principle</a>
- A module should be responsible to one , and only one, actor.
- Module - simplest definition could be a source file or it is a cohesive set of functions and data structures.
- Cohesion binds together the code responsible to a single actor.
- Symptom 1 - Accidental duplication
    - Many problems occur because we put code that different actors depend on into close proximity.
    - The SRP says to separate the code that different actors depend on.
- Sympton 2 - Merges
    - Problems occur when different developers from different teams try to change the same source code they depend on.
    - This is easily reflected by the code merges and they get riskier if multiple actors depends on same files.
- At component level, the SRP becomes the Common Closure Principle.
- At architectural level, the SRP becomes the Axis of change responsible for the creation of Architectural boundaries.
  
  


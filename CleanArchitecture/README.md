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

3. PART III - Design Principles
   1. Chapter 7 - SRP: The Single Responsibility Principle
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

## <a name="chapter_5">Chapter 5 - Object-Oriented Programming </a> 

## <a name="chapter_6">Chapter 6 - Functional Programming </a> 


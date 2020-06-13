# A Primer on (JavaScript) Programming

## Overview

A brief history of computing and programming, and a general introduction to JavaScript programming

## A. TL; DR

* **Key Point #1**: *The paradigm of transistor-based general-purpose computers, implemented with the von Neumann architecture and running programs written by human programmers in a (more-natural) general-purpose programming language, remains the predominant form of computer programming today.*
* **Key Point #2**: *JavaScript/ECMAScript has come to dominate the Web-application software development arena, and has become a full-fledged, robust general-purpose programming language in its own right since its humble origins as a simple scripting language, all the way through to the present day.*
* **Key Point #3**: *The role of the programmer is to translate user specifications (e.g., business requirements) into instructions that can be understood by the computer. This is generally done with the assistance of a high-level general-purpose programming language and corresponding development tools (e.g., Integrated Development Environments/IDEs).*

**!TO-DO**

## B. Contents

* C. A Brief History of Modern Computing and Programming
  * C-1. Early Era (1800s to 1940s)
  * C-2. Middle Era (1940s to 1970s)
  * C-3. Modern Era (1970s to Present)
* D. The Perfect Language Doesn't Exist :(
* E. What Is a Program?
* F. JavaScript Programming: Fundamental Concepts
  * F-1. Values, Literals, and Data Types
  * F-2. Expressions and Statements
  * F-3. Control Structures
    * Conditionals
    * Loops
    * Function Calls
  * F-4. Values vs. References
  * F-5. Objects and Methods
* G. JavaScript Programming: A Guided Example
* H. Program Errors
* I. Key Takeaways
* J. References

## C. A Brief History of Modern Computing and Programming

### C-1. Early Era (1800s to 1940s)

Computation has a long, rich history, but its modern form originated approximately in the mid-1800s, with Charles Babbage’s conception of the **Analytic Engine**, a mechanical device which (in principle) would behave similarly to what would now be recognized as a general-purpose computer.

Through the turn of the 20th century, several other important developments had been independently discovered, including the formalization of key mathematical logic constructs by George Boole (a body of work now known eponymously as Boolean algebra). This continued progression of events up through the 1920s and 1930s culminated in the work of Alan Turing and his contemporaries. Turing’s canonical paper “*On Computable Numbers, with An Application to the Entscheidungsproblem*” (1936) formalized the modern notion of “**computation**”; a corollary of this monumental paper was the ability to precisely specify what is now known as a **general-purpose computer**.

Building on Turing’s work, and as part of the War effort, the first predecessors of the modern-day computer were conceived and built in the 1940s. The **ENIAC** is generally regarded as the first stored-program, general-purpose computer to have been built using electronic components (outcompeting its electro-mechanical, electro-magnetic, and other contemporaries); the ENIAC was effectively the first physical manifestation of Babbage’s Analytic Engine, conceived almost a whole century prior to that point.

These early machines were multi-ton in weight—occupying entire rooms—and had very limited memory and comparatively slow computational speed by modern standards. Furthermore, the binary (i.e., 1/0, or on/off) “language” understood by these machines was programmed using bulky components such as mechanical relays and vacuum tubes, which had performance issues and were susceptible to malfunction.

These implementation difficulties notwithstanding, another important emergent property of these early computers was their fundamental design: the **von Neumann architecture**. This design (conceived by the mathematical prodigy John von Neumann and his colleagues) formed the basis of all modern computational devices—including the computers, smartphones, etc. in widespread use today.

The von Neumann architecture has the following general structure:

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/01-C1-vNA.JPG" alt="von Neumann Architecture")
 </p>

The structure is comprised of three key components:
* ***Memory*** - the storage area of the computer, which stores data and instructions of the computer program
* ***Central Processing Unit (CPU), or Processor*** - the “brain” of the computer, which performs computations and reads/writes data and program instructions to/from memory
* ***Inputs/Outputs*** - provides a user the ability to interact with the computer
  * ***Inputs*** include keyboard, mouse, audio/video peripherals (e.g., microphones and video cameras), network connectors (inbound), touch devices, etc.
  * ***Outputs*** include monitors, printers, audio/video peripherals (e.g., speakers), network connectors (outbound), etc.

### C-2. Middle Era (1940s to 1970s)

With the groundwork set by these early machines, several problems arose.

There was an obvious impracticality of such large, unwieldy devices which precluded any large-scale manufacture and adoption. A final critical piece was introduced to these nascent “proto-computers” with the invention of the **transistor** in the 1950s. The transistor is an electronic device which can behave as an “on/off” switch, and is a solid-state device having no moving/mechanical parts. As the manufacturing process of transistors improved over time, the transistor was subsequently incorporated into computational devices to represent the fundamental **binary digit** (or **bit**), which underlies all computer hardware. The bit constitutes the simplest possible representation of data in computation: either on, or off. From this fundamental operation, larger, more complex structures such as digital logic gates (based on Boolean algebra) could be built, which ultimately hierarchically form into the full general-purpose computer.

Further innovation in integrated-circuit manufacturing technology over the subsequent decades propelled the transistor into a role of great prominence, as well as sparking the “second westward gold rush” of what eventually would become known today as *Silicon Valley*. The transistor was critically important in increasing the density of computational power and memory into increasingly smaller physical space (ultimately allowing for the mass production of consumer electronic devices), and it is widely regarded as one of—if not ***the***—most important inventions of the 20th century accordingly.

There was still, however, another problem: the process of “programming” these early computational devices required great skill and was highly tedious and error-prone, inasmuch as these machines were directly programmed in the “native” binary language understood by the machines. These early program were typically printed on punch cards or on tape read by the machine, which required intense labor and skill to write even trivial programs.

An [example](http://www.cs.uni.edu/~fienup/cs1410f11/lectures/Supplement_MARE_AL.pdf) "simple" binary program is as follows:
```
1010000000000000
0010000000010000
0001000000010010
0011000000010000
0010000000010001
1101000000010001
1000010000000000
1001000000001001
1001000000001110
0110000000000000
0001000000010000
0011000000001111
0010000000010000
1001000000000010
0111000000000000
0000000000000001
0000000000000000
0000000000000000
0000000000010011
0000000001001000
0000000001000101
0000000001001100
0000000001001100
0000000001001111
0000000000001101
0000000001010111
0000000001001111
0000000001010010
0000000001001100
0000000001000100
0000000000000000
```

A key innovation to address this issue was the development of **assembly languages**, starting in the late 1940s and into the subsequent decades. Assembly languages use mnemonic terms to represent the binary machine instructions and memory addresses of the computer, alleviating the need to explicitly program the computer in its native binary format.

The above binary program example can be represented in [MARIE](http://computerscience.jbpub.com/ecoa/4e/Login.aspx?ref=/ecoa/4e/default.aspx) (a fictitious/academic assembly language for a hypothetical computer architecture, used for pedagogical purposes) as follows:
```
		CLEAR
		STORE INDEX
WHILE,		LOAD STR_BASE
		ADD INDEX
		STORE ADDR
		LOADI ADDR
		SKIPCOND 400
		JUMP DO
		JUMP END_WHILE
DO,		OUTPUT
		LOAD INDEX
		ADD ONE
		STORE INDEX
		JUMP WHILE
END_WHILE,	HALT
ONE,		DEC 1
INDEX,		DEC 0
ADDR,		HEX 0
STR_BASE,	HEX 13
STR,		DEC 72	/H
		DEC 69	/E
		DEC 76	/L
		DEC 76	/L
		DEC 79	/O
		DEC 13	/carriage return
		DEC 87	/W
		DEC 79	/O
		DEC 82	/R
		DEC 76	/L
		DEC 68	/D
NULL,		DEC 0	/NULL CHAR

```

### C-3. Modern Era (1970s to Present)

While a vast improvement over explicit binary programming, assembly languages did not address several issues which were inherent in writing programs at the time, two of which are of particular note.
* Firstly, assembly languages lack **portability**. A given program written in a given machine’s **instruction set** (the binary instructions understood by that particular machine) were not directly portable/transferable to another machine—the program would have to be entirely rewritten all over in the new machine’s instruction set in order to execute the same program on the latter machine.
* Secondly, writing programs in assembly languages still subjected the programmer to solve problems within the constraints of the machine’s own instructions, rather than solving problems within the constraints of the problem domain itself and in a more natural, human-comprehensible manner.

Both of these issues (among others) were ultimately solved with the development of high-level, general-purpose programming languages and their associated compilers in the late 1950s through the 1970s (and to the present day).

A **general-purpose programming language** allows the programmer to specify instructions in a manner that is more reminiscent of natural language (e.g., English), using descriptive terms to perform **operations** (e.g., arithmetic, repetitive loops, etc.) and to denote **data** (e.g., variable declarations), rather than specifying binary machine instructions and binary memory addresses.

The previous example program can now be (truly) simply written in the general-purpose programming language JavaScript (discussed later) as follows:
```js
console.log("HELLO\rWORLD");
```

However, because the computer only understands binary instructions, the **compiler** (itself a specialized program) servers the role of “translator” from the human’s programming language to the computer’s native binary instructions. Compiler implementations are very complicated and even today are still an active area of research in the computer science arena, however, with decades of innovation preceding them, modern compilers can generate machine code that is approximately just as efficient as that created by a skilled human assembly programmer.

> **Key Point #1**: *The paradigm of transistor-based general-purpose computers, implemented with the von Neumann architecture and running programs written by human programmers in a (more-natural) general-purpose programming language, remains the predominant form of computer programming today.*

Another key innovation was the development of computer **networking** (i.e., connecting computers into larger, integrated systems), ultimately resulting in the formation of the **Internet** in the 1980s and the **World Wide Web** in the early 1990s. (The profound impact of these technologies is readily self-apparent.)

The 1990s and 2000s marked a rapid transformation of globalized society and technology, including the proliferation of many wide-ranging computational devices and consumer appliances. Accordingly, one of the emerging challenges during this time was cross-compatibility of programs and software across these devices (a challenge that still remains today!).

In the mid-1990s, the general-purpose programming language **Java** was developed by Sun Microsystems to address this issue of cross-compatibility. One of Java’s core tenets was the notion of “*write once, run anywhere*.” To accomplish this, Java was implemented using a runtime environment (the **Java Runtime Environment**, including the **Java Virtual Machine**), which sits on top of each corresponding device’s operating system as a “*virtual computer*” that provides the ability to translate compiled Java source code (called Java **bytecode** in its compiled form) into the machine instructions specific to that particular target computer system. (Bytecode is essentially the “assembly program” run by the “virtual computer,” analogously to an assembly program running on the physical computer’s native binary instruction set.)

A simplified schematic of the Java programming language's implementation is as follows:

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/02-C3-Java.JPG" alt="The Java Runtime Ecosystem")
 </p>

Here, the source code written by the programmer in Java (`HelloWorld.java`) is first compiled to bytecode (`HelloWorld.class`) by the Java Runtime Environment (JRE), and then deployed to the corresponding target machine/operating system by the Java Virtual Machine (JVM), thereby constituting a cross-platform implementation system. 

Java’s popularity grew quickly during this time, and it has since become deeply rooted in the enterprise software development space. Microsoft released the programming language **C#** (analogously running on top of  the **.NET Framework** runtime environment) in 2000 as a direct competitor to Java, and many other runtime-environment-based programming languages have also emerged since then.

By the mid-to-late 1990s, as the Web became more prevalent and computers continued to become more powerful, the early form of modern **Web applications** began emerging. Up to this point, most programmed applications were developed to run in a native format (e.g., desktop applications) targeted to a specific operating system (e.g., Windows, Mac, Unix, etc.). However, with the interconnectivity provided by the Web, it was apparent that applications could similarly be useful in this growing cross-platform, cross-device landscape.

In 1995, Brendan Eich of Netscape developed the **JavaScript** programming language for use in its Netscape Navigator Web browser application, originally intended as a scripting language based on the Scheme programming language and implemented using an **interpreter** (analogous to a compiler, i.e., translator from the high-level programming language to machine code). Originally slated to be named “*LiveScript*” in its initial implementation and release, the Netscape team led by Eich elected to name the language “*JavaScript*” instead, capitalizing on the buzz surrounding its (otherwise unrelated) contemporary at the time, the aforementioned Java programming language.

The ensuing implementation challenges and “browser wars” subsequently to JavaScript’s initial launch and widespread adoption is beyond the scope of the present discussion, however, the key outcome of these events was the standardization of JavaScript’s programming language specification, under the oversight of the **European Computer Manufacturers Association** (**ECMA**), which correspondingly named its specification of the language as “**ECMAScript**” (partly due to trademark infringement concerns with respect to the name “JavaScript”). This is often abbreviated “**ES**” in reference to modern versions of the language (e.g., “**ES6**,” the 2015 release of the updated ECMAScript language specification, which marked a watershed moment in its maturity as a modern programming language).

Modern implementations (e.g., Google Chrome’s V8 and Mozilla Firefox’s SpiderMonkey engines) of the ECMAScript language specification (i.e., JavaScript) integrate its various features into a single “**JavaScript runtime environment**,” which provides the ability to program Web applications using the JavaScript programming language targeting the Web browser (e.g., Chrome, Firefox, etc.) as the medium of deployment of the fully functional, standalone Web application. This allows for great portability of Web applications, independently of the user’s operating system (the cross-platform issue is solved by vitue of the browser applications themselves, which are generally developed by the corresponding browser vendors for most major operating systems, e.g., Mac, Windows, and Linux).

A simplified schematic of the JavaScript runtime environment is as follows:

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/03-C3-JavaScriptRE.JPG" alt="The JavaScript Runtime Environment")
 </p>

(*N.B. [This informative article](https://medium.com/@olinations/the-javascript-runtime-environment-d58fa2e60dd0) provides a more comprehensive review of the various components of the open-source V8 JavaScript engine (Google Chrome’s implementation of the ECMAScript language and runtime environment), as well as the corresponding Web API (not formally part of the ECMAScript language specification) used for DOM manipulation of the Web browser page. V8 was also later adapted by Ryan Dahl to create **Node.js**, which provides a standalone JavaScript runtime environment allowing to deploy JavaScript applications outside/independently of the Web browser.*)

The proliferation of Web applications from the mid-2000s through the 2010s (and beyond) has largely displaced the use of native desktop applications, and consequently Web applications have become the predominant form of software applications used in practice today.

> **Key Point #2**: *JavaScript/ECMAScript has come to dominate the Web-application software development arena, and has become a full-fledged, robust general-purpose programming language in its own right since its humble origins as a simple scripting language, all the way through to the present day.*

[:arrow_up_small: Return to top](#overview)

## D. The Perfect Language Doesn't Exist :(

With all of the innovations that have occurred in the past century of computation and programming, there are still performance limits of modern computational devices, both in practical and in theoretical terms.

Referring back to the von Neumann architecture model, both processor speeds (i.e., machine operations per unit time) and memory capacity (i.e., total bits of stored information) are ***finite***. Modern computers have processor speeds measured in GHz (billions of operations per second) and memory capacities measured in Gigabytes/GB (billions of bytes of addressable memory, where a “**byte**” is a conventional grouping of bits into a set of eight). With rapid technological advancements, processor speeds and memory capacities have increased at an exponential rate in the decades spanning from the mid-20th century through the present day. However, while modern applications are far more robust than even as recently as a decade ago, with the explosive growth of devices and data, there are still many applications and problem domains that even the most advanced computers must contend with.

Furthermore, general-purpose programming languages ultimately become machine-code instructions, and therefore are subject to the constraints of the machine. For this reason, computers in their modern form do not possess “intelligence” and “insight” in the same (nondeterministic) way that a human does, and are incapable of interpreting ambiguous or unspecific requirements accordingly.

Therefore, an “*ideal*” computer would be one with infinite processor speed and infinite memory, with the ability to translate ambiguous natural-language specifications directly into a set of precise instructions. This would also obviate the need for computer programmers in the first place (fortunately for programmers, this is not a credible threat!). Interestingly, even if such an “ideal” (*read*: impossible) machine were available, there are still many mathematical and non-trivial computational problems that are beyond its capabilities!

With these considerations, when a general-purpose programming language is designed and implemented, there are inherent **trade-offs** that are made accordingly. These typically involve a compromise between high performance (which requires programming “closer to the machine”) vs. readability and expressiveness (which is more similar to natural language, but at the price of more “overhead” to generate the machine instructions from the programmer’s source code resulting in slower performance).

Below is a brief survey of a few representative modern, popular general-purpose programming languages in common use today.

| Programming Language | Creator | Current Specification Developer(s) | Language Specification | Implementation | Representative Application Domain(s) | Comments |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| C | Dennis Ritchie (1970s) | ISO/IEC JTC 1 | ISO/IEC 9899 | compiled (e.g., gcc, Clang) | <ul><li>operating system kernels</li><li>embedded hardware systems</li><li>compilers</li></ul> | Used in high-performance applications, and has more explicit constructs reminiscent of assembly & machine code |
| C++ | Bjarne Stroustrup (1980s) | ISO/IEC JTC 1 | ISO/IEC 14882 | compiled (e.g., gcc, Clang, MS Visual C++) | <ul><li>high-performance applications (e.g., game engines, real-time audio/video signal processing, etc.)</li><li>embedded hardware systems</li></ul> | Originally developed as an "improvement" (++) to C with the addition of classes, it has since become widespread in hardware systems and influenced later languages such as Java |
| Java | James Gosling (1990s) | Oracle | The Java® Language Specification | compiled and interpreted via the Java Runtime Environment & Java Virtual Machine |  <ul><li>cross-platform desktop applications</li><li>Web applications</li></ul> | Popularized the runtime environment paradigm of application development and deployment, and is still in wide use today |
| C# | Anders Hejlsberg (2000s) | <ul><li>Microsoft</li><li>ISO/IEC</li><li>Ecma International</li></ul> | ISO/IEC 23270, ECMA-334 | compiled and interpreted via the .NET Framework & Common Language Runtime (CLR) | <ul><li>cross-platform desktop applications</li><li>Web applications</li></ul> | Developed by Microsoft as a direct competitor to Java, these languages generally compete in similar markets (e.g., enterprise software development) |
| Python | Guido von Rossum (1990s) | The Python Software Foundation (PSF) | The Python Language Reference (based on Python Enhancement Proposals, or PEPs) | interpreted (standard CPython implementation) | <ul><li>Data science and analytics</li><li>Machine learning and artificial intelligence</li><li>Education (computer science & programming)</li><li>Web applications</li></ul> | Having gained popularity into the 2010s and beyond, Python is widely used in academia and in data application domains. Python is less performant than the other languages indicated above, a design trade-off made in favor of its expressiveness (i.e., more reminiscent of natural human language). |
| JavaScript | Brendan Eich (1990s) | Ecma International | ECMA-262 | interpreted by JavaScript runtime environment (e.g., Google Chrome V8, Mozilla FireFox SpiderMonkey, Node.js, etc.) | <ul><li>Web applications</li><li>Native applications (desktop & mobile)</li></ul> | JavaScript has come to dominate the Web application developed landscape through the 2010s (and beyond), often touted by its enthusiasts as the "most used programming language" due to the ubiquity of the modern Web |

[:arrow_up_small: Return to top](#overview)

## E. What Is a Program?

With the preceding discussion regarding the historical context of computation and programming now concluded, it is worthwhile to ask a fundamental question: what *is* a **program**, anyways? 

A program is simply a set of instructions, i.e., ultimately the machine instructions performed by the computer’s constituent transistor-implemented bits.

The famously titled textbook “Algorithms + Data Structures = Programs” (1976) by computer scientist Niklaus Wirth provides an insightful description of the fundamental essence of a “*program*.”
* An **algorithm** is a precisely specified sequence of instructions (e.g., a step-by-step recipe to prepare a dish).
* A **data structure** (e.g., an array) is a organized grouping of information, which is typically manipulated by algorithms to achieve a certain desired result or outcome.

A program, then, is simply a collection of data structures and algorithms, which vary in scale and complexity correspondingly to the underlying problem that the program is intended to solve.

Therefore, while the computer hardware is only “aware” of its constituent bits (transistors), it is the programmer-specified data structures stored in its memory and corresponding programmer-specified algorithms performed (computed) by its processor on those data structures which confer “meaning” on those bits—be it bank account information, moving pictures on a screen, text messages, spreadsheets, etc. Indeed, the information stored in and represented by the underlying physical circuitry of any given computational device is only “meaningful” to the human user of that device, by virtue of the programmer’s implementation of the user’s software applications per their (potentially ambiguous) specification.

> **Key Point #3**: *The role of the programmer is to translate user specifications (e.g., business requirements) into instructions that can be understood by the computer. This is generally done with the assistance of a high-level general-purpose programming language and corresponding development tools (e.g., Integrated Development Environments/IDEs).*

[:arrow_up_small: Return to top](#overview)

## F. JavaScript Programming: Fundamental Concepts

This section will review fundamental programming principles, using JavaScript as a representative case study of a modern general-purpose programming language.

### F-1. Values, Literals, and Data Types

The atomic unit of any computer program is the **value**, which is represented as binary digits (bits) by the constituent hardware (i.e., transistors) of the computer system on which the program is ultimately run.

The most fundamental level of human semantics provided by the programming language to the computer is the notion of a **data type**. While the computer itself only understands bits (sequences of 1s and 0s), the problem-domain and programmer have a more intuitive notion of useful “*values*.” Accordingly, JavaScript provides several **primitive data types** to represent these values. These primitive data types are as follows:

| Primitive Data Type | Representative Literal(s) | Description |
| :---: | :---: | :---: |
| Number | `5`, `3.14` , `NaN` | Represents numbers and used in arithmetic operations |
| String | `'Hello World'` | Represents text information |
| Boolean | `true`, `false` | Represents true/false values and used in control structures (discussed later) |
| Null | `null` | Semantically represents the *deliberate absence* of a value |
| Undefined | `undefined` | Semantically represents an *unknown/indeterminate* value |

*(N.B. Symbol and BigInt are primitive data types also provided by JavaScript as of ES2019, however, these will not be considered further for purposes of discussion. See [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures) for further discussion of primitive values.)*

A common term when referring to a value from a primitive data type is a **literal**. As this terminology suggests, primitive values are “hard-coded” in the programming languages and are unchanging/immutable (e.g., the value 5 is understood to be a numeric integer—it would not make sense to “change” what 5 fundamentally represents in the programming language).

Additionally, JavaScript provides many additional *non*-primitive data types (e.g., objects, arrays, and functions). These provide a more robust feature set for the corresponding values (i.e., to represent more complicated values and data structures for a particular problem), however, this also comes at the expense of implementation and performance overhead. These non-primitive data types will be revisited again later in this section.

### F-2. Expressions and Statements

**!TO-DO**

### F-3. Control Structures

**!TO-DO**

#### Conditionals

**!TO-DO**

#### Loops

**!TO-DO**

#### Function Calls

**!TO-DO**

### F-4. Values vs. References

**!TO-DO**

### F-5. Objects and Methods

**!TO-DO**

[:arrow_up_small: Return to top](#overview)

## G. JavaScript Programming: A Guided Example

**!TO-DO**

[:arrow_up_small: Return to top](#overview)

## H. Program Errors

**!TO-DO**

[:arrow_up_small: Return to top](#overview)

## I. Key Takeaways

**!TO-DO**

[:arrow_up_small: Return to top](#overview)

## J. References

**!TO-DO**

[:arrow_up_small: Return to top](#overview)

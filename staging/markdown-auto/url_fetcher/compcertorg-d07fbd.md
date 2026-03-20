# compcert.org

**Link:** [https://compcert.org/](https://compcert.org/)

## Conteúdo Extraído

```text
CompCert - Main page
home
partners
motivations
research
compiler
downloads
publications
CompCert
compilers you can
formally
trust
Menu
Home
Partners
Motivations
Research
The Compcert C compiler
Downloads
Publications
The CompCert project investigates the formal verification of realistic
compilers usable for critical embedded software.  Such verified
compilers come with a mathematical, machine-checked proof that the
generated executable code behaves exactly as prescribed by the
semantics of the source program.  By ruling out the possibility of
compiler-introduced bugs, verified compilers strengthen the guarantees
that can be obtained by applying formal methods to source programs.
The main result of the project is the CompCert C verified compiler, a high-assurance compiler for almost all of the C language (ISO C 2011), generating efficient code for the ARM, PowerPC, RISC-V and x86 processors.
Download CompCert C
Read the manual
News
[02/2026] Release of CompCert version 3.17.  This release fixes a few minor bugs, uses extraction of Rocq strings to OCaml native strings, and adds compatibility with Rocq version 9.1 and with the latest versions of Menhir..
[09/2025] Release of CompCert version 3.16.  This version adds support for position-independent code (PIC) and position-independent executables (PIE) on x86-64, AArch64 and RISC-V.  It also improves the static analysis and the optimizations of 64-bit integer arithmetic (esp. on 32-bit platforms) and of calls to built-in functions.  Finally, it is compatible with the Rocq prover version 9.0.
[12/2024] Release of CompCert version 3.15.  This release makes value analysis more precise, thus improving the effectiveness of constant propagation and redundant cast elimination.  Other missed opportunities for optimization were also addressed, notably for redundant load elimination on ARM and RISC-V.  This release also fixes incompatibilities with header files in the latest version of macOS, and improves support for Coq 8.20.
[05/2024] Release of CompCert version 3.14.  It provides minor performance improvements, notably for ARM 32 bits, better debugger support for ARM 64 bits and RISC-V, and supports Coq up to version 8.19.
[07/2023] Release of CompCert version 3.13.  This is a minor release that fixes minor issues in the unverified C front-end, and improves code compactness for ARM Thumb.
[01/2023] For the development of CompCert, the
2022 ACM SIGPLAN Programming Languages Software Award
is awarded to
Xavier Leroy
,
Sandrine Blazy
,
Zaynah Dargaye
,
Jacques-Henri Jourdan
,
Michael Schmidt
,
Bernhard Schommer
,
and
Jean-Baptiste Tristan
.
This award recognizes "a software system that has had a significant impact on programming language research, implementations, and tools. The impact may be reflected in the widespread adoption of the system or its underlying concepts by the wider programming language community either in research projects, in the open-source community, or commercially".
[11/2022] CompCert version 3.12 is released, featuring full support for unstructured
switch
statements (the infamous Duff's device) and C2011 Unicode string literals and character constants.
[06/2022] Release of CompCert version 3.11.  This release adds support for
_Generic
expressions from C11 and fixes minor deviations from ISO C and minor issues with the RISC-V back-end.  It uses version 4.1 of the Flocq library for floating-point arithmetic and is compatible with Coq 8.15.
[05/2022] For the development of CompCert, the
2021 ACM Software System Award
is awarded to
Xavier Leroy
,
Sandrine Blazy
,
Zaynah Dargaye
,
Jacques-Henri Jourdan
,
Michael Schmidt
,
Bernhard Schommer
,
and
Jean-Baptiste Tristan
.
This award recognizes "a software system that has had a lasting influence, reflected in contributions to concepts, in commercial acceptance, or both" and is considered the highest award for software originating from computer science research.
[11/2021] Release of CompCert version 3.10.  Bit fields in structs and unions are no longer emulated, but are given formal semantics and are compiled to bit-level manipulations in the formally-verified part of CompCert.  Relatedly, the layout of bit fields is now compatible with the ELF ABI.  Other novelties include a new implementation of the PTree data structure that enjoys extensionality and runs faster, and an option to the
clightgen
to produce CompCert C AST instead of Clight AST.
[05/2021] CompCert version 3.9 is released.  It adds support for macOS running on "Apple silicon", i.e. ARM 64-bit architectures, preliminary support for
__builtin_expect
and
__builtin_unreachable
, and compatibility with Coq 8.13 and Menhir >= 20210419.  Also, the open-source parts of CompCert are now licensed under the LGPL (instead of the GPL as before).
[11/2020] Release of CompCert C version 3.8.  Novelties include support for x86 64 bits under Windows using the Cygwin64 environment, support for
_Static_assert
from ISO C11, several new built-in function, and compatibility with Coq 8.12.
[03/2020] Release of CompCert C version 3.7.  This is a minor release that improves conformance with ISO C and with ABIs, fixes a few bugs, and adds support for Coq 8.11 and OCaml 4.10.
[09/2019] CompCert C version 3.6 is released.  Novelties include support for the AArch64 (ARMv8 in 64-bit mode) target architecture, and better support for generating branchless code, including a new if-conversion pass that turns conditional statements and expressions into conditional move instructions when possible.
[02/2019] Release of CompCert C version 3.5.  This release improves compatibility with GCC and Clang with respect to the handling of C attributes.  It fixes a few bugs and adds support for Coq 8.9.0.  Last but not least, the Coq development can now be rechecked in full using
coqchk
.
[09/2018] Release of CompCert C version 3.4.  It adds more error and warning messages, tightens compatibility with ISO C11,  fixes a few bugs, and improves compatibility with newer Coq, Menhir, and OCaml versions.
[05/2018] Release of CompCert C version 3.3.  It features a source annotation mechanism to transmit information to
AbsInt's a
3
analyzers
, improved error and warning messages, and compatibility with Coq 8.8.
[01/2018] Publication:
CompCert: Practical experience on integrating and qualifying a formally verified optimizing compiler
, by Daniel Kästner, Ulrich Wünsche, Jörg Barrho, Marc Schlickling, Bernhard Schommer, Michael Schmidt, Christian Ferdinand, Xavier Leroy, and Sandrine Blazy.  ERTS 2018: Embedded Real Time Software and Systems.
[01/2018] CompCert C version 3.2 is released.  Novelties include an improved inlining heuristic, resurrected support for Cygwin x86 32-bit as a target architecture, and compatibility with Coq 8.7 and 8.7.1.
[08/2017] CompCert C version 3.1 is released, featuring a new code generator for the RISC-V architecture (in 32 and 64 bit modes) and improved support for PowerPC 64 and E5500 processors (in 32/64 bit hybrid mode).
[02/2017] Publication:
Closing the gap — the formally verified optimizing compiler CompCert
, by
Daniel Kästner, Xavier Leroy, Sandrine Blazy, Bernhard Schommer, Michael Schmidt, and Christian Ferdinand. SSS'17: Developments in System Safety Engineering: Proceedings of the Twenty-fifth Safety-critical Systems Symposium.
[02/2017] Release of CompCert C version 3.0.  This is the first version of CompCert that fully supports 64-bit architectures, with pointers and memory addresses that can be either 32 or 64-bit wide.  The existing x86 32-bit port was extended to generate x86 64-bit code as well.  A version 3.0.1 for Coq 8.6 is also available.
[06/2016] Release of CompCert C version 2.7.  It features a formal account of separate compilation and linking, and generation of full DWARF debugging information for the ARM and IA32 targets.  A version 2.7.1 adds support for Coq 8.5pl2.
[01/2016] The paper
CompCert — a formally verified optimizing compiler
, by Xavier Leroy, Sandrine Blazy, Daniel Kästner, Bernhard Schommer, Markus Pister, and Christian Ferdinand, was presented at ERTS 2016 (Embedded Real Time Software and Systems conference) and received the "President's favorite" award.
[12/2015] CompCert C version 2.6 is released, with complete generation of DWARF debugging information for the PowerPC target, detailed explanations of syntax errors, and support for PowerPC 64 bits and E5500 processors.
[06/2015] Release of CompCert C version 2.5. Novelties include a formally-verified type checker for CompCert C, a more careful modeling of pointer comparisons against the null pointer, algorithmic improvements in the handling of deeply nested struct and union types, much better ABI compatibility for passing composite values, support for GCC-style extended inline asm, and more complete generation of DWARF debugging information (contributed by AbsInt).
[09/2014] The working sources for CompCert are now hosted on
Github
.
[09/2014] CompCert C version 2.4 is released, with a revised handling of single-precision floating-point arithmetic and support for C99 compound literals and
switch
statements over 64-bit integers.
[06/2014] As part of a licensing agreement with Inria,
AbsInt Angewandte Informatik GmbH
will market and provide support for the CompCert verified C compiler.
[05/2014] CompCert C version 2.3 is released.  Novelties includes a formally-verified parser, and support for C99 designated initializers.
[02/2014] Release of CompCert C version 2.2, featuring more aggressive optimizations, support for more features of ISO C99 (especially variable-argument functions), and improved conformance with the target ABIs.
[10/2013] Minor release of CompCert C version 2.1.  The main novelty is support for the
_Alignas
attribute from ISO C2011, for finer control of alignment.
[06/2013] CompCert C version 2.0 is now available, featuring two major improvements: 1- support for 64-bit integer arithmetic (type
long long
) and 2- a new register allocator based on a posteriori validation.
[03/2013] Release of version 1.13 of the CompCert C compiler.  The semantics of pointers "one past the end of an array" is now properly defined as in the ISO C standard.
[01/2013] CompCert C versions 1.12 and 1.12.1 are released.  The two versions are functionally identical, but 1.12 is for Coq 8.3 and 1.12.1 for Coq 8.4.
[12/2012] The
Microsoft Research Verified Software Milestone Award
was awarded to Xavier Leroy for his work on the CompCert verified compiler.
[07/2012] CompCert C version 1.11 is released.  Novelties include a full formalization and proof of floating-point arithmetic, and performance improvements: function inlining, more aggressive constant propagation and CSE.
[06/2012] A
technical report
describing the memory model used in CompCert versions 1.7 and up.
[03/2012] Release of version 1.10 of the CompCert C compiler.  Now with a provably-correct implementation of volatile accesses and by-value structure passing and assignment, plus various small performance improvements, and a
user's manual
.
[02/2012] Publication:
Formally verified optimizing compilation in ACG-based flight control software
, with Ricardo Bedin França, Sandrine Blazy, Denis Favre-Felix, Marc Pantel and Jean Souyris, symposium ERTS2 2012.
[11/2011] Release of version 1.9.1 of the Compcert C compiler.
[10/2011] The
2011
La Recherche
prize in Information Sciences
was awarded to Xavier Leroy, Sandrine Blazy, Zaynah Dargaye and Jean-Baptiste Tristan for their work on the CompCert verified C compiler.
[08/2011] Release of version 1.9 of the Compcert C compiler.  Novelties include a reference C interpreter and stronger semantic preservation results.
[05/2011] Release of version 1.8.2 of the Compcert C compiler.
[03/2011] Release of version 1.8.1 of the Compcert C compiler.  Now compatible with Coq 8.3pl1, and including algorithmic improvements (lower compilation times) and better handling of initialized global variables.
[09/2010] Version 1.8 of the Compcert C compiler is available.  It includes a larger subset of C (including side-effects within expressions) as its source language; a new port generating x86-32 bits code; and more precise semantics for volatile accesses.
[03/2010] Release of version 1.7 of the Compcert C compiler, featuring a new C type-checker/elaborator/simplifier and a refined memory model.
[01/2010] Release of version 1.6 of the Compcert C compiler.
[11/2009] Publication:
A formally verified compiler back-end
.
An extensive (80 pages!) description of the back-end part of Compcert, published in
Journal of Automated Reasoning
43(4).
[08/2009] Release of version 1.5 of the Compcert C compiler.
Now with full support for
goto
statements!
[07/2009] Publication:
Formal verification of a realistic compiler
.  A short overview of the CompCert verified compiler, published in
Communications of the ACM
, July 2009, along with a
perspective
written by Greg Morrisett.
[06/2009] Release of version 1.4.1 of the Compcert C compiler.
(This version is functionally identical to version 1.4, but compatible
with Coq 8.2-1.)
[04/2009] Release of version 1.4 of the Compcert C compiler.
[01/2009] Publication:
Mechanized semantics for the Clight
subset of the C language
.  A description of the Clight source language,
published in
Journal of Automated Reasoning
43(3).
[08/2008] Release of version 1.3 of the Compcert C compiler.
[03/2008] First public release (version 1.2) of the Compcert C compiler.
[02/2008] Creation of this Web site.
Last modified:
2026-02-13
      
Contents copyright © 
2007-2026
Xavier Leroy
      
Design by
6ix Shooter Media
modified by Pos3idon
Mentions légales
```

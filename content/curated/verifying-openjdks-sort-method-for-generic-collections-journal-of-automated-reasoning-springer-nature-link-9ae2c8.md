# Verifying OpenJDK’s Sort Method for Generic Collections | Journal of Automated Reasoning | Springer Nature Link

**Link:** [https://link.springer.com/article/10.1007/s10817-017-9426-4](https://link.springer.com/article/10.1007/s10817-017-9426-4)

## Conteúdo Extraído

```text
Verifying OpenJDK’s Sort Method for Generic Collections | Journal of Automated Reasoning | Springer Nature Link
Skip to main content
Log in
Menu
Find a journal
Publish with us
Track your research
Search
Saved research
Cart
Home
Journal of Automated Reasoning
Article
Verifying OpenJDK’s Sort Method for Generic Collections
Open access
Published:
31 August 2017
Volume 62
, pages 93–126, (
2019
)
Cite this article
You have full access to this
open access
article
Download PDF
Save article
View saved research
Journal of Automated Reasoning
Aims and scope
Submit manuscript
Verifying OpenJDK’s Sort Method for Generic Collections
Download PDF
Stijn de Gouw
2
,
Frank S. de Boer
1
,
3
,
Richard Bubel
5
,
Reiner Hähnle
5
,
Jurriaan Rot
4
&
…
Dominic Steinhöfel
5
Show authors
5741
Accesses
37
Citations
Explore all metrics
Abstract
TimSort is the main sorting algorithm provided by the Java standard library and many other programming frameworks. Our original goal was functional verification of TimSort with mechanical proofs. However, during our verification attempt we discovered a bug which causes the implementation to crash by an uncaught exception. In this paper, we identify conditions under which the bug occurs, and from this we derive a bug-free version that does not compromise performance. We formally specify the new version and verify termination and the absence of exceptions including the bug. This verification is carried out mechanically with KeY, a state-of-the-art interactive verification tool for Java. We provide a detailed description and analysis of the proofs. The complexity of the proofs required extensions and new capabilities in KeY, including symbolic state merging.
Similar content being viewed by others
Proving JDK’s Dual Pivot Quicksort Correct
Chapter
© 2017
Formally Verifying an Efficient Sorter
Chapter
© 2024
Modular Transformation of Java Exceptions Modulo Errors
Chapter
© 2021
Explore related subjects
Discover the latest articles, books and news in related subjects, suggested using machine learning.
Algorithms
Computability and Recursion Theory
Data Structures
Logical Analysis
Java
Open Source
Parallel Sorting Algorithm Optimization
1
Introduction
Among the arguments that are routinely invoked against the usage of formal software verification one can find the following: it is expensive, it is not worthwhile (compared to its cost), it is less effective than bug finding (e.g., by testing, static analysis, or model checking), it does not work for “real” software. In this article we present a case study in formal verification demonstrating that none of these arguments holds up in general and, on the contrary, formal specification and verification of real software is possible and can very well pay off.
We perform functional verification with mechanical proofs of TimSort, the sorting algorithm for generic collections in the Java standard library. Because of the complexity of the code under verification, it is essential to break down the problem into sub-tasks of manageable size. This is achieved with
contract-based deductive verification
[
4
], where the functionality and the side effects of each method are precisely specified with expressive first-order contracts. In addition, each class is equipped with an invariant that has to be re-established by each method upon termination. These formal specifications are expressed in the Java Modeling Language (JML) [
14
].
We use the state-of-art Java verification tool KeY [
1
], a semi-automatic, interactive theorem prover, which covers nearly full sequential Java. KeY typically finds more than 99% of the proof steps automatically (see Sect.
5
), while the remaining ones are performed interactively by a human expert. This is facilitated by the use in KeY of symbolic execution plus first-order reasoning as its proof paradigm. It results in a close correspondence between proof nodes and symbolic program states which brings the experience of program verification somewhat close to the activity of debugging.
The work presented here was motivated by our recent success to verify executable Java versions of counting sort and radix sort in KeY with manageable effort [
12
]. As a further challenge, we planned to verify a complicated sorting algorithm taken from the widely used OpenJDK core library. It turns out that
the default implementation
of Java’s
java.util.Arrays.sort()
and
java.util.Collection.sort()
methods is an ideal candidate: it is based on a complex combination of merge sort and insertion sort [
15
,
19
]. It had a bug history (see
www.bugs.java.com/view_bug.do?bug_id=8011944
), but was reported as fixed as of Java 8. We decided to verify the actual implementation with only two minor modifications: we stripped the code of generics and we modified one execution path that is irrelevant to the sorting result (see Sect.
7
for details). Otherwise, the verified Java code is identical to the library code and fully executable. The implementation is described in detail in Sect.
2
.
During our verification attempt we discovered that the fix to the bug mentioned above is in fact not working [
13
] and that the “fixed” version crashes with an uncaught top-level exception on certain inputs. We succeeded to identify conditions under which the bug occurs (Sect.
3
). From our analysis we could derive a bug-free version that does not compromise performance. The bug as reported in [
13
] led to different kinds of fixes in different languages, including Java, Android and Python. We review the reactions in Sect.
4.1
, and then provide a detailed description of the proof that the fixed Java code terminates properly and does not raise any exception in Sect.
4.3
. This includes two auxiliary methods that could not be proven correct in [
13
]. The Android community provided an alternative fix, which we proved to be correct as well, as reported in Sect.
4.4
.
We provide a detailed account of the proof statistics in Sect.
5
. They show that the symbolic state merging technique recently implemented in KeY [
22
] can successfully mitigate state explosion during symbolic execution. In addition, we analyze the nature of user interactions, thereby providing indicators where prospects for automation lie and how the individual style of proof engineers can influence efficiency of the proof effort.
In Sect.
6
we draw lessons from our experience of proving TimSort. These concern the development of formal specifications, the choice of integer semantics and how to deal with state explosion. While our case study shows that formal specification and verification of real Java library code is possible and pays off, it also highlighted a number of limitations to current verification technology. These are discussed in Sect.
7
.
In addition to fixing the bug, our verification effort exhibited further potential issues with TimSort. We point out some recommendations to the maintainers of TimSort in Sect.
8
. Related work is discussed in Sect.
9
and in Sect.
10
we draw conclusions.
This paper is a revised and extended version of [
13
]. The extension includes a more detailed description and (statistical) analysis of the proofs, including a comparison between the old proof and several new proofs based on branch merging techniques; a (mechanic) proof for all methods, including
mergeLo
and
mergeHi
, which only became possible after several new techniques (branch merging, a new
do-while
rule) were added to KeY; and a mechanic proof of the Android version.
2
Implementation of TimSort
The default implementation of
java.util.Arrays.sort
for non-primitive types is TimSort, a hybrid sorting algorithm based on merge sort and insertion sort. The algorithm sorts a specified segment of the input array incrementally from left to right based on consecutive (disjoint)
runs
: segments of the array that are already sorted. If these runs are not large enough, they are extended using binary insertion sort. The starting positions and the lengths of the generated runs are stored on a stack. During execution some of these runs are merged, triggered by a condition on the top elements of the stack. In the end, all runs are merged, yielding a sorted array.
Now we explain the algorithm in detail, focusing on the central parts of the Java implementation. The interface of TimSort is given by the two static methods on lines 1 and 29 of Listing 1. The main method of TimSort is shown in Listing 1 (with original comments), where
a
is the input array. The parameters
lo
and
hi
are the lower bound (inclusive) and upper bound (exclusive) of the part of
a
that must be sorted. To sort the entire array, they can be omitted, see lines 29–31.
The stack of runs is encapsulated by the object variable
ts
which is constructed in line 5. It is represented by two instance variables
runBase
and
runLen
of the object
ts
, that refer to arrays of integers. These arrays
runBase
and
runLen
contain respectively the starting positions and the lengths of the runs on the stack.
Footnote
1
The (variable) size of the stack is kept in the instance variable
stackSize
. The allocated length of these arrays
runBase.length
and
runLen.length
is determined in the constructor of
ts
based on the length of the input array.
In each loop iteration, the next run is constructed. In line 9 a maximal run from the current position
lo
is constructed by identifying a maximal descending or ascending segment, reversing the order in case of a descending one. If the resulting run is too short (that is, less than
minRun
) then it is extended to a run of length
minRun
using binary insertion sort (“binary” refers to the fact that it uses binary search). The variable
nRemaining
denotes the number of elements yet to be processed. In line 17 the starting position and the length of the run is pushed onto the stack of the object variable
ts
by method
pushRun
in Listing 2.
In line 18, the method
mergeCollapse
is called, which repeatedly merges runs until the top three elements of the stack satisfy the conditions given in lines 4 and 5 of Listing 4, for
i
=
stackSize
. Actual merging is done by a call to
mergeAt(n)
, which merges the two runs whose lengths are represented respectively by
runLen[n]
and
runLen[n+1]
. Without going into detail, we note that
mergeAt
(see Listing 3) features an optimisation that identifies parts of the two runs that do not need to be considered for merging, and then merges either from left to right or from right to left (by a call to
mergeLo
or
mergeHi
respectively), using a temporary array holding a copy of the smaller of the two.
We describe the merging pattern of
mergeCollapse
. To simplify the notation, let
\(\texttt {runLen[n-1]}=C\)
,
\(\texttt {runLen[n]}=D\)
, and
\(\texttt {runLen[n+1]}=E\)
, representing the lengths of the top three runs on the stack (observe that
n = stackSize-2
at the beginning of each iteration). The condition to be established is that
\(C > D + E\)
and
\(D > E\)
. The loop achieves this by distinguishing the following cases:
1.
If
\(C\le D+E\)
and
\(C<E\)
then the runs at
n-1
and
n
are merged.
2.
If
\(C\le D+E\)
and
\(C\ge E\)
then the runs at
n
and
n+1
are merged.
3.
If
\(C> D+E\)
and
\(D\le E\)
then the runs at
n
and
n+1
are merged.
4.
If
\(C>D+E\)
and
\(D>E\)
then the loop exits.
After exiting the main loop in Listing 1, the entire input array has been processed, but there may still be pending runs on the stack. These runs are finally merged by the call to mergeForceCollapse (Line 25 of Listing 1), which repeatedly merges runs on the stack (either the top two or the two below it) until only a single run remains, representing the sorted array.
3
Breaking the Invariant
As explained in the previous section, the method
mergeCollapse
establishes the following postcondition:
1.
\(\texttt {runLen[i - 3] > runLen[i - 2] + runLen[i - 1]/}\)
2.
\(\texttt {runLen[i - 2] > runLen[i - 1]}\)
for
\(\texttt {i = stackSize}\)
. However, as the comments in lines 1–9 of Listing 4 suggest, the intention is that the above conditions are “re-established” by
mergeCollapse
for
all
\(\texttt {i <= stackSize}\)
. More precisely, the above conditions for
\(\texttt {i <= stackSize}\)
should be a
loop invariant
of the main loop of the
sort
method (Listing 1). After the call to
pushRun
in the
sort
method (line 17) the loop invariant is temporarily broken (for the case
i = stackSize
), and the intention is that it is restored by the call to
mergeCollapse
(line 18).
The above loop invariant is fundamental to TimSort, hence we sometimes refer to it simply as
the invariant
. We shall also refer to specific elements of
runLen
satisfying the
(element) invariant
, meaning that such an element is greater than the next one and greater than the sum of the next two.
The invariant is used to compute the length of
runLen
, as explained in more detail in Sect.
3.1
. However, the method
mergeCollapse
does not re-establish the invariant in general, contrary to what is suggested in the comments. To see this, consider the situation where
runLen
consists of
$$\begin{aligned} 120,\, 80,\, 25,\, 20,\, 30 \end{aligned}$$
on entry of
mergeCollapse
, directly after the entry 30 was added by
pushRun
. In the first iteration of the
mergeCollapse
loop there will be a merge at entry 25, since
\(25 \le 20 + 30\)
and
\(25 < 30\)
, resulting in (Listing 4, conditions in lines 13 and 14 are evaluated to true causing lines 15 and 16 to be executed):
$$\begin{aligned} 120^\times ,\, 80,\, 45,\, 30. \end{aligned}$$
We annotate an entry with the superscript
\(\times \)
if it does not satisfy the element invariant. In the second iteration the element invariant is satisfied at entries 80 and 45 (i.e., conditions at lines 13 and 17 are evaluated to false and line 20 is executed), because
\(80 > 45 + 30\)
and
\(45 > 30\)
, so
mergeCollapse
terminates. The element invariant does not hold at entry 120, however, since
\(120 \le 80 + 45\)
. Thus,
mergeCollapse
has not fully restored the loop invariant of
sort
.
More generally, an error (a violation of the invariant) can only be introduced by merging the third-to-last and second-to-last element and requires precisely four elements after the position of the error, i.e., at
runLen[stackSize-5]
. Indeed, suppose
runLen
consists of four elements
A
,
B
,
C
,
D
satisfying the invariant. We add a fifth element
E
to
runLen
using
pushRun
, after which
mergeCollapse
is called. The only possible situation in which an error can be introduced, is when
\(C \le D + E\)
and
\(C <E\)
. In this case,
C
and
D
will be merged, yielding the stack
$$\begin{aligned} A,\,B,\,C+D,\,E. \end{aligned}$$
Then
mergeCollapse
checks whether the invariant is satisfied by the new three top elements. But
A
is not among those, so it is not checked whether
\(A > B + C + D\)
. As shown by the above example, this latter inequality need not hold in general.
3.1
The Length of
runLen
The invariant affects the maximal size of the stack of run lengths during execution; recall that this stack is implemented 
... (conteúdo truncado)

```

![Image](C:\Users\Humberto\Desktop\MetodosFormaisClaude\metodos_formais\staging\markdown-auto\docling\wing90a\wing90a_artifacts\image_000000_b3fd033f855329fb8cac3aeb650b5b2567dd6a011481aa83f64fc7232d069bb1.png)

## A Specifier's Introduction to Formal Methods

Jeannette M. Wing, Carnegie Mellon University ormalmethods used in developing computer systems are mathematically based techniques for describing system properties. Such formal methods provideframeworks within which peoplecanspecify,develop,andverifysystems in a systematic,rather than ad hoc, manner.

ber of pragmatic considerations: who uses A formal method also addresses a numit,what it is used for,when it is used,and how it is used. Most commonly, system designers use formal methods to specify a system's desiredbehavioral and structural properties.

Applied to computer systems development, formal methods provide mathematically based techniques that describe system properties. As such, they present a framework for systematically specifying, developing, and verifying systems.

A method is formal if it has a sound mathematical basis, typically given by a formal specification language.This basis provides the means of precisely defining notions like consistency and completeness and,morerelevantly,specification,mplementation,and correctness.It provides the means of proving that a specification is realizable,proving that a system has been implemented correctly,and proving properties of a system without necessarily running it to determine its behavior.

However,anyone involved in any stage of system development canmakeuse of formal methods. They can be used in the initial statement of acustomer'srequirements,through system design,implementation, testing,debugging, maintenance, verification,and evaluation.

Formal methods are usedtoreveal ambiguity, incompleteness, and inconsistency in a system.When usedearlyin the system development process, they can reveal de- sign flaws that otherwise might be discovered only during costly testing and debugging phases. When used later, they can help determine the correctness of a system implementationandtheequivalence of differentimplementations.

not address any pragmatic considerations, but lacking such considerations would render it useless.Hence,a formal method should possess a set of guidelines or a "style sheet"that tells the user the circumstancesunder which themethodcan and should be applied as well as how it can be appliedmost effectively.

One tangible product of applying a formal method is a formal specification.A specification serves as a contract, a valuable piece of documentation,and a means of communication among a client, a specifier,and animplementer.Because of their mathematical basis, formal specifications aremorepreciseandusuallymoreconcise than informal ones.

Since a formal method is a method and not just a computer program or language,it may or may not have tool support. If the syntax of a formal method's specification language is made explicit,providing standard syntax analysis toolsforformal specifications would be appropriate.If the language's semantics are sufficiently restricted,varying degrees of semantic analysis can be performed with machine aids as well.Thus,formal specifications have the additionaladvantage overinformal onesof being amenable to machine analysis and manipulation.

For more on the benefits of formal specification, see Meyer.For more on the distinction between a method and a language, and what specifying a computer system means, see Lamport.2

Continued on p.10

COMPUTER

For a method tobe formal,it must have a well-defined mathematical basis.It need

## What is a specification language?

A formal specification language provides a formal method's mathematical basis.I borrowed the terms and definitions thatfollowfromGuttaget al.3Burstall and Goguenhaveused theterm"language"and morerecently the term"institution"forthe notion of a formal specification language.

Definition: A formal specification language isatriple,&lt;Syn,Sem,Sat&gt;,whereSynandSem are sets and Sat SynxSem is arelation between them. Syn is called the language's syntactic domain; Sem,its semantic domain; and Sat,its satisfies relation.

Definition:Given a specification language, &lt;Syn,Sem,Sat&gt;,if Sat(syn,sem)then syn is aspecificationof sem,andsemisaspecificand of syn.

Definition: Given a specification language, &lt;Syn，Sem，Sat&gt;，the specificand set of a specification syn in Syn is the set of all specificands sem in Sem such that Sat(syn, sem).

Less formally, a formal specification language provides a notation (its syntactic domain), a universe of objects (its semantic domain), and a precise rule defining whichobjects satisfyeach specification.A specification is a sentencewritten in terms of theelements of thesyntacticdomain.It denotes a specificand set,a subset of the semantic domain.A specificand is an object satisfying a specification. The satisfies relation provides the meaning, or interpretation,forthesyntacticelements.

Backus-Naur form is an example of a simple formal specification language,with a set of grammars as its syntactic domain and a set of strings as its semantic domain. Every string is a specificand of each grammar that generates it.Every specificand set is a formal language.

In principle,a formal method isbasedon some well-definedformal specification language. In practice,however,this language may not have been explicitly given. Themore explicit the specification language's definition, the more well-defined the formal method.

Formal methods differ because their specification languages have different syntactic and/or semantic domains.Evenif theyhaveidenticalsyntactic and semantic domains,they may have different satisfies relations.

When a specification language's semantic domain is over programs or systems of programs,the term implements is used for the satisfies relation,and the term implementationis used fora specificandinSem. An implementation prog is correct with respect to a given specification spec if prog satisfies spec. More formally, tives) and a set of grammatical rules for combiningthesesymbolsintowell-formed sentences.For example,using standard notationforuniversalquantification()and logical implication (=),let x be a logical variableandPandQbepredicatesymbols. Then this sentence,Vx.P(x)=Q(x),would be well-formed in predicate logic, but this one,Vx.= P(x) → Q(x),would not because =is a binary logical connective.

A syntactic domain need not be restricted to text;graphical elements such as boxes,circles,lines,arrows,and icons can be given a formal semantics just as precisely as textual ones.A well-formedness condition on such a visual specification might be that all arrows start and stop at boxes.

Definition: Given a specification language, &lt;Syn,Sem,Sat&gt;,an implementation prog in Semis correct withrespect toagiven specification specinSynif andonlyifSat(spec, prog).

Semantic domains. Specification languages differ most in their choice of semantic domain.The following are some examples:

- ·Abstract-data-type specification languages are used to specify algebras, theories,and programs.Though specifications written in these languages range over different semantic domains,they often look syntactically similar.
- ·Concurrent and distributed systems specification languages are used to specify statesequences,eventsequences,stateand transition sequences,streams, synchronization trees,partial orders,and state machines.
- ·Programming languages are used to specify functions from input to output, computations,predicate transformers,relations, and machine instructions.

Each programming language (with a welldefined formal semantics) is a specification language, but the reverse is not true, because specifications in general do not have to be executable on some machine whereas programs do. By using a more abstract specification language, we gain the advantage of notbeingrestricted to expressing only computable functions.It is perfectlyreasonablein a specification to express notions like"Forall xin setA,there existsayin set Bsuchthat propertyPholds of.xandy,"where Aand Bmight beinfinite sets.

Programs,however,areformalobjects. susceptible to formal manipulation (for example,compilationandexecution).Thus, programmers cannot escape fromformal methods.Thequestion is whetherthey work with informal requirements and formal programs, or whether they use additional formalism to assist them during requirements specification.

Syntactic domains.We usually define a specification language's syntactic domain in terms of a set of symbols (for example, constants, variables, and logical connec-

Satisfies relation.Weoftenwould like to specify different aspects of a single specificand,perhaps using different specification languages.Forexample,you might want tospecify thefunctional behavior of a collection of program modules as the composition of thefunctional behaviors of the individual modules. You might additionally want to specify a structural relationshipbetween the modules such as what set ofmoduleseachmoduledirectlyinvokes.

Toaccommodatethesedifferentviews ofa specificand,wefirstassociatewith each specification language a semantic abstraction function,which partitions specificands into equivalence classes.

Definition: Given a semantic domain,Sem,a semanticabstractionfunctionisa homomorphism,A: Sem → 2sem, that maps elementsofthesemanticdomaininto equivalence classes.

For a given specification language, we choose a semantic abstraction function to induceanabstractsatisfiesrelationbetween specifications and equivalence classes of specificands. This relation defines a view on specificands.

Definition:Given a specification language, &lt;Syn, Sem, Sat&gt;,and a semantic abstraction function,A,defined on Sem,an abstract satisfies relation, ASar:Syn →2sew, is the inducedrelation such that spec E Syn,prog ∈Sem· [Sat(spec,prog)=ASat(spec,A(prog)]

Different semantic abstractionfunctions make it possible to describe multiple views of the same equivalence class of systems, orsimilarly,impose different kinds of constraints on these systems.Having several specification languages with different semantic abstraction functions for a single semantic domain can be useful. This encourages and supports complementary specifications of different aspects of a system.

COMPUTER

For example, in Figure 1,a single semantic domain,Sem,is on the right. One semantic abstractionfunction partitions specificands in Sem into a set of equivalence classes,three of which are drawn as blobs in solid lines. Another partitions specificands into a different set of equivalence classes, two of which are drawn as blobs in dashed lines.Via the abstract satisfies relation ASatl, specification A of syntactic domain Syn1 maps to one equivalence class of specificands(denoted by a solid-linedblob),andviaASat2,specificationBof syntactic domainSyn2maps toa different equivalence class of specificands (denoted by a dashed-line blob).Note the overlapbetweenthesolid-linedanddashedlined blobs.

To be concrete, suppose Sem is a library of Ada program modules. Imagine that A specifies (perhaps through a predicate in first-order logic) allprocedures that sort arrays, and B specifies (perhaps through a call graph) all procedures that call functions on a user-defined enumeration type E. Then, a procedure that sorts arrays of E's might bein the intersectionof ASat1(A) and ASat2(B).

Two broad classes of semantic abstraction functions are those that abstract preserving each system's behavior and those that abstract preserving each system's structure.Intheexampleabove,A specifies a behavioral aspect of the Ada program modules,but B describes a structural aspect.

Behavioralspecifications.Behavioral specifications describe only constraints on the observablebehavior of specificands. The behavioral constraint that most formal methods address is a system's required functionality (that is,mapping from inputs to outputs).Current research in formal methods addresses other behavioral aspects, such as fault tolerance, safety，security, response time, and space efficiency.

Often,some of thesebehavioral aspects, such as security, are included as part of, rather than separatefrom,a system'sfunctionality.If the overall correctness of a system is defined so that it must satisfy more than onebehavioral constraint,asystem that satisfiesonebut not anotherwould be incorrect.For example,if functionality and response time were the constraints of past deadlines would be just as unacceptinterest,asystemproducingcorrectanswers able as a system producing incorrect answers on time.

Structural specifications.Structural specifications describe constraints on the

September1990

![Image](C:\Users\Humberto\Desktop\MetodosFormaisClaude\metodos_formais\staging\markdown-auto\docling\wing90a\wing90a_artifacts\image_000001_81e2019c85b5aed6c38817c4d9729e1c23c2a58dc350b5b8a2bad5ac70b015ed.png)

internal composition of specificands. Example structural specification languages aremodule interconnectionlanguages. Structuralspecificationscapturevarious kinds of hierarchical and uses relations such as those represented by procedurecall graphs, data-dependency diagrams,and definition-use chains.Systems that satisfy thesamestructuralconstraintsdonot necessarily satisfy the same behavioral constraints.Moreover,the structure of a specification need not bear any direct relationshiptothe structure ofitsspecificands.

Properties of specifications.Each specification language should be defined so each well-formed specification is unambiguous.

Definition:Given a specification language, &lt;Syn,Sem,Sat&gt;,a specification syn inSynis unambiguous if and only if Sat maps syn to exactly one specificand set.

Informally,aspecificationis unambiguous if and only if it has exactly one meaning.This key property of formal specifications means that any specification language based on or incorporating a natural language (like English) is not formal since natural languages are inherently ambiguous. It also means that a visual specificationlanguage that permits multiple interpretations of a box and/or arrow is ill-defined, and hence not formal.

Another desirable property of specifications is consistency.

Definition:Given a specification language, &lt;Syn,Sem,Sat&gt;,a specification synin Syn is consistent (or satisfiable) if and only if Sat maps syn to a non-empty specificand set.

Informally,a specificationis consistent if and only if its specificand set is nonempty. In terms of programs, consistency isimportant becauseit meansthereissome implementation that will satisfy the specification.If you view a specification as a set offacts,consistencyimplies thatyoucannot derive anything contradictory from the specification.

Were you to pose a question based on a consistent specificationyou would notget mutually exclusive answers.Obviously, we want consistent specifications.An inconsistent specification,which negates on one occasion what it asserts on another, means you have no knowledge at all.

Specifications need not be complete in the sense used in mathematical logic,though certain relative-completeness properties might be desirable(forexample,sufficient completeness of an algebraic specification*).

In practice, you must usually deal with incomplete specifications. Why? Specifiers may intentionallyleave some things unspecified,giving theimplementer some freedom to choose among different data structures and algorithms.Also,specifiers cannot realistically anticipate all possible scenarios in whichasystem will be run and thus,perhaps unwittingly,have left some things unspecified.Finally, specifiers develop specifications gradually and iteratively, perhaps in response to changing customer requirements,and hence work with unfinished products more often than finished ones.

Figure 2. Specification users.

![Image](C:\Users\Humberto\Desktop\MetodosFormaisClaude\metodos_formais\staging\markdown-auto\docling\wing90a\wing90a_artifacts\image_000002_d4e1ab0d4740025aa1b0670b3ef08811da1f6574eb3f71b0ea3f3f0f1ddae7b9.png)

A delicatebalance exists betweensaying just enough and saying too much in a specification.Specifierswanttosayenough so thatimplementers donotchooseunacceptable implementations.Specifiers are responsible for not making oversights; any incompletenessinthespecificationshould be an intentional incompleteness. On the other hand,saying too much may leave little designfreedomfortheimplementer. Aspecification that overspecifiesisguilty ofimplementation bias.

Informally,a specification has implementation bias if it specifies externally unobservable properties of its specificands; it places unnecessary constraints on its specificands.For example,a set specification that keeps track of the insertion order of its elements has implementation bias toward an ordered-list representation and against a hash tablerepresentation.

Proving properties of specificands. Mostformal methods aredefinedinterms of a specification language that has a welldefined logicalinference system.A logical inference system defines a consequence relation,typically givenin terms of asetof inference rules, mapping a set of wellformed sentences in the specification lan- guage to a set of well-formed sentences.

When you prove a statement inferable from these facts, you prove a property that a specificand satisfying the specification will have, a property not explicitly stated in the specification.An inference system gives users of formal methods a way to predict a system's behavior without having to execute or even build it. It gives users a way to state questions,in the form of conjectures,aboutasystemcastinterms of just the specification itself. Users can then answer these questions in terms of a formalproof constructed throughaformal derivation process.

provers and proof checkers are example toolsthatassistuserswith thetedium of deriving and managing formal proofs.

## Pragmatics

Certain pragmatic concerns exist about formal methods,theirusers,theiruses,and their characteristics.

Users. Some users of formal methods are actually going to produce something tangible: formal specifications. However, most people need only read specifications, not develop their own from scratch.Besides specification writers,there are several kinds of specification readers.

In Figure 2,each stick figure represents a differentroleinthesystem development process.A person playing any of these roles isa potential specification user.In practice, one person may play multiple roles, and some role may not be played at all.

Specifiers write, evaluate, analyze, and refine specifications.They prove that their refinements preserve certain properties and prove properties of specificands through specifications.Specification readers,besides specifiers,are customers,those people who may have hired the specifiers; implementers,those peoplewhorealize a specification;clients,those peoplewho use aspecifiedsystem,usuallywithoutknowledgeofhowitisimplemented;andverifiers,those people whoprove the correctness of implementations.All these people can benefitfrom the assistance of machine tools(anotherkindofspecification reader), some ofwhich might blindly manipulate specifications without regard totheir meaning.

One point of tension in many formal methods is that their languages may be more suitable to one type of specification user than to others. Most language designers will target their language for at least two types of users(forexample,clients and specifiers orspecifiersandimplementers). Some specification languages contain a lot morereadablebycustomers.Some contain aminimalamountbecausetheintentofthe method is to do formal proofs by machines or because the meaning of a rich set of cryptic mathematical notation is assumed.

A formal method with an explicitly defined inference system usually has the further advantage that this systemcan be completelymechanized(forexample,ifit has a finite set of finite rules).Theorem

An advocate ofaparticularformal methodshouldtellpotentialusersthemethod's domain of applicability.For example,a formal method might be applicable for describing sequential programs but not parallel ones, or for describing message-

We use this inference system to prove properties from the specificationabout specificands.Again taking a specification asasetoffacts,wederivenewfactsthrough the application of the inference rules.

The inference system increases user confidence in the specification's validity. If users are able to prove a surprising result from the specification,then perhaps the specification is wrong.

passing distributed systems but not transaction-based distributed databases. Without knowing the proper domain of applicability,a user may inappropriately apply a formalmethod to aninapplicable domain.

A formal method's set of guidelines should identify different types of users the method is targetedfor and the capabilities each should have. To apply some methods properly, users might need to know modern algebra,set theory,and/or predicate logic.To apply some domain-specific methods,users might need to know additional mathematical theories —for example, digital logic, if specifying hardware, or probability and statistics,if specifying system reliability.

Uses. You can apply formal methods in all phases of system development. Such applications shouldn't be considered a separate activity,but rather an integral one. The greatest benefit in applying a formal method often comes from the process of formalizing rather thanfrom the end result. Gaining a deeper understanding of the specificand byforcing yourself tobe abstractyetprecise about desired system properties canbemore rewarding than having the specification document alone.

Consider,foreachsystemdevelopment phase, some uses of formal specifications and the formal methods that support them. (See"Further reading"for specific citations.)

Requirements analysis.Applying a formal method helps clarify a customer's set of informally stated requirements.Aspecification helps crystallize the customer's vague ideas and reveals contradictions, ambiguities, and incompleteness in the requirements.A specifier has a better chance of asking pertinent questions and evaluating customer responses through the use of a formal,rather than informal, specification.Both the customer and specifier can pose and answer questions based on the specification to see whether it reflects the customer's intuition and whether the specificand set has the desired set of properties. Systems such as Kate and the Requirements Apprentice address the problem of transforming informal requirements into formal specifications; the Gistexplaineraddressestheconverse problem of translating a formal specification into a restricted subset of English.

opment Method (VDM), Z, Larch, and fy an entire system, you can certainly verLamport's transition axiommethod areify smaller,critical pieces.The trickiest for system design.

Decomposition is the process of partitioning a system into smaller modules. Specifiers can write specifications to captureprecisely theinterfaces between these modules.Eachinterfacespecificationprovides the module's client theinformation needed to use the module without knowledge of its implementation.At the same time, it provides the module's implementertheinformationneededtoimplementthe module without knowledge of its clients. Thus,as long as the interface remains the same,the implementation of the module can be replaced,perhaps by a more efficient one,at some later time without affecting its clients.

formalmethodsthatareespeciallysuitablepartisinexplicitlystatingtheassumptions about the environment inwhich each critical piece is placed. (I elaborate on this point in the "Bounds of formal methods" section.) Systems such as Gypsy, the Hierarchical Development Method (HDM),the Formal Development Method (FDM),and m-EVES (Environment for Verifying and Evaluating Software)evolved as aresult of a primary focus on program verification. Higher Order Logic(HOL)was originally developed for hardwareverification.

System validation.Formal methods can aid in system testing and debugging.Specifications alone can be usedto generate test cases for black-box testing.Specifications that explicitly state assumptions on a module's use identify test cases for boundary conditions.

The interface provides a place for recording design decisions; moreover, any intentionalincompleteness can be captured succinctly as a parameter in the interface.

Refinement involves working at different levelsofabstraction,perhapsrefininga single module at one level to be a collection of modules at a lower level,or choosing a representation type for an abstract data type. Each refinement step requires showing that a specification(or program) at one level satisfies a higher level specification.

Proving satisfaction often generates additional assumptions, called proof obligations,that must be discharged forthe proof tobe valid.Aformal method provides the language to state these proof obligations precisely and the framework to carry out the proof.

Program refinement dates back toDijkstra's work on stepwise refinement and predicate transformers and Hoare's work on data representation and abstraction functions.Related work on program transformation, program synthesis, and inferential programminghave spawned the design of languages like Refine and Extended ML,and programming environments like CIP-S and the Ergo Support System.These refinement approaches are based on classicalmathematicallogic.Analternative approach to program development based on constructive logic gave rise to proof development environments like Nuprl in which programs are proofs and vice versa.

Specifications along with implementations can be used for other kinds of testing analysis such as path testing, unit testing, andintegrationtesting.Testingbasedsolely on an analysis of the implementation is not sufficient; the specification must be taken into account.For example,a test set may be complete for doing a path analysis but may not reveal missing paths that the specification would otherwise suggest.The success of unit and integration testing depends on the precision of the specifications of theindividual modules.

Only a few formalmethodshavebeen developed explicitly for testing.Three examples are the Data Abstraction, Implementation,Specification,andTestingSystem,usedtotestimplementationsofabstract datatypes;Kemmerer'ssymbolicexecution tool,used to generate and execute test cases from Ina Jo specifications; and the Task Sequencing Language Runtime System,used to automatically check the execution of Ada tasking statements against TSL specifications.

Systemdocumentation.Aspecification is a description alternative to system implementation.It serves as a communication medium between a client and a specifier,between a specifier and an implementer, andamongmembers ofanimplementation team.In reply to the question"What does it do?"no answer is more exasperating than "Run it and see." One of the primary intended uses of formal methods is to capture the"what"in a formal specification rather than the"how."A client can then impossible without a formal specification.simplyread the specification rather than

Systemverification.Verificationis the process of showing that a system satisfies System design.Two of the most imporits specification. Formal verification is tant activities during design are decomposition and refinement. The Vienna Devel-Although you may never completely veri-read the implementation or worse,execute

Figure 3. State chart specification of a one-slot buffer.

![Image](C:\Users\Humberto\Desktop\MetodosFormaisClaude\metodos_formais\staging\markdown-auto\docling\wing90a\wing90a_artifacts\image_000003_8892fb85e10e43f25a2bedc048e2b3ccf45585236f10484d73d1f4232ead2079.png)

the system, to find out the system's behavior.

Systemanalysisandevaluation.Tolearn from the experience of building asystem, developers should do a critical analysis of itsfunctionalityandperformanceonceit has been built and tested.Does the system do what the customer wants? Does it do it fast enough?If formal methods were used initsdevelopment,theycanhelpsystem developers formulate andanswer these questions.The specification serves as a reference point.If the customer is unhappy but the system meets the specification, the specification can be changed and the system changedaccordingly

Indeed,much recent work in the applicationof formal methodsto nontrivialexamples has been in specifying a system already built,running,and used. Some of these exercises revealed bugs in published algorithms and circuit designs,serious bugs thathad gone undiscoveredfor years.As expected, most revealed unstated assumptions,inconsistencies，and unintentional incompleteness in the system.

Medium-sized systems thathave been specified formally include VLSI circuits, microprocessors, oscilloscopes, operating systems kernels, distributed databases, and securesystems.Mostformal methodshave not yet been applied to specifying largescale software or hardware systems;most are still inadequatetospecifymanyimportantbehavioral constraints beyond functionality,forexample,fault-tolerance and real-time performance.

This problem of scale exists in two, often confused dimensions: size of the specification andcomplexity of the specificands. Tools can help address specification size,since managing large specifications is just like managing otherlarge documents (such as programs, proofs, and test suites)and their structural interrelationships.

The problem of dealing with a specificand's inherent complexity remains.System complexityresultsfrominternalcomplexityand/or interface complexity.For example,an optimizing compiler is internallymorecomplext than a nonoptimizing one for the same language, yet, in principle, they both provide the same simple interface to their clients (for example, "compile program\_name").Byproviding a systematic wayto think and reason about specificands.formal methods can help people grapple with both kinds of system complexity.

Characteristics.Aformalmethod's characteristics,such as whether its language is graphical or whether its underlying logic isfirst-order,influence the style in which a user applies it.This article is not intended togiveacompletetaxonomyof allpossible characteristics of a method nor to classify exhaustively all methods according to these characteristics.Instead,1 givea partial listingofcharacteristics,noting that a method typically reflects a combination of many different ones. (See "Further reading"for citations of the methods mentioned.)

Model-versus property-oriented.Two broadclassesofformalmethods arecalled model-oriented and property-oriented. Using a model-oriented method, a specifier defines a system's behavior directly by constructing a modelofthe systemin terms ofmathematicalstructuressuch astuples, relations,functions,sets,and sequences. Using a property-oriented method, a specifier defines the system's behavior indirectlyby stating asetof properties,usually in the form of a set of axioms, that the system must satisfy.

A specifier following a property-oriented method tries to state no more than the necessary minimal constraints on the system's behavior.The fewer the properties specified,the more the possible implementations that will satisfy the specification.

Model-oriented methodsfor specifying the behavior of sequential programs and abstract data types include Parnas'statemachines, Robinson and Roubine's extensions to them with V-, O-, and OV-functions,VDM,andZ.Methods forspecifying thebehavior of concurrent and distributed systems include Petri nets,Milner's Calculus of Communicating Systems,Hoare's Communicating Sequential Processes, Unity, I/O automata, and TSL.The Raise Project represents more recent work on combining VDM and CSP.

Property-oriented methods can be brokenintotwocategories,sometimesreferred to as axiomatic and algebraic.Axiomatic methodsstemfromHoare'swork on proofs of correctness ofimplementations of abstract data types,where first-order predicatelogicpreconditions andpostconditions are used for the specification of each operation of the type. Iota, OBJ, Anna, and Larch are example specification languages that support an axiomatic method.

In an algebraic method, data types and processes are defined to be heterogeneous algebras. This approach uses axioms to specifyproperties of systems,but the axioms are restricted to equations. Much work has been done on the algebraic specification of abstract data types, including the handlingoferrorvalues,nondeterminism, and parameterization.The more widely known specification languages that have evolved from this work are Clear and Act One(Algebraic Specification Techniques for Correct and TrustySoftware Systems).

Property-oriented methods for specifying thebehavior of concurrent and distributed systems include extensions to the Hoare-axiommethod,temporal logic,and Lamport's transition axiom method. The Language of Temporal Ordering of Speci-

fications(LOTOS)specification language represents more recent work on the combination of Act One and CCS (with some CSP influence).

Visual languages. Visual methods include any whose language contains graphical elements in their syntactic domains. The most prominent visual method is Petri nets and its many variations, used most typically to specify the behavior of concurrent systems.

The example shows one of the more notable features of state charts that distinguish them from"flat" state-transition diagrams: A roundtangle can represent a hierarchy of states(and,in general,an arrow can represent a set of state transitions), thereby letting users zoom in and out of a system and its subsystems.

More recent visual language work includes Harel's state charts based on higraphs, used to specify state transitions in reactive systems.Figure 3 gives a simple example of a state chart that describes the behaviorofaone-slotbuffer.Rounded rectangles("roundtangles")represent states in a state machine and arrows represent state transitions.Initially,the one-slotbuffer is empty. If a message arrives and is put in the buffer, the buffer becomes full; when the message has been serviced and removed from the buffer, its state changes back to being empty.

Harel's higraph notation inspired the design of the Miro visual languages, which specify security constraints. Like state charts,theMirolanguageshaveaformally defined semantics and tool support.

Manyinformal methods usevisual notations.These methods allow the construction of ambiguous specifications,perhaps because English text is attached to the graphical elements or because multiple interpretationsofagraphicalelement (usually different meanings for an arrow) are possible. Many popular software and system design methods such as Jackson's method,Hierarchy-Input-Processing-Output (HIPO), Structured Design, and SoftwareRequirementsEngineeringMethodology are examplesof semiformal methods that use pictures.

resentations. As long as users realize that the specification may suffer from implementationbias,executablespecifications can play an important role in the system development process. Specifiers can use themtogainimmediatefeedback about the specification itself,todorapid prototyping (the specification serves as a prototype of thesystem),and totesta specificandthrough symbolic execution of the specification. For example,the Statemate toollets users run simulations throughthe state transition diagram represented by a state chart.

Besides state charts,executable specification languages include OBJ; Prolog, a logic programming language that when used in a property-oriented style lets specifiers state logical relations on objects;and Paisley,a model-oriented language,based on a model of event sequences and used to specify functional and timing behavioral constraints for asynchronous parallel processes.

Tool-supported. Some formal methods evolved from the semantic-analysis tools that were built to manipulate specifications and programs.Model-checking tools let users construct a finite-state model of the system and then show a property holds of each state or state transition of the system.Tools such as Extended Model Checker (EMC) are especially useful for specifying and verifying properties of VLSI circuits.

attributable tothe nature or simplicity of the specificand and sometimes tothe methods themselves.

The choice ofamethodislikelytoaffect what a specification says and how it is said. A method'sguidelines may encourage the specifier to be explicit about some system behaviors(forexample,statechanges)and not others (for example,error handling). Syntacticconventions(such asindentation style), special notation(vertical and horizontal lines), and keywords affect a specification's physical appearance and its readability.

Most proponents of methods used primarily to specify behavioral properties of concurrent and distributed systems have carefully defined the satisfies relation for a given semantic domain.Many of their methods lack the niceties—the syntactic sugar and software support tools —— that formalmethods for sequential systems provide. For some theories or models of concurrent and distributed systems,more user-friendlyspecificationlanguages (LOTOS and Raise)are beginning to appear.

## Abstract data types: Z,VDM, Larch.

The table contains four operations: INIT, INSERT, LOOKUP, and DELETE. INIT initializes the symbol table st to be empty. INSERT modifies the table by adding a new binding to st, in the case the key k is not already in the domain of st.LOOKUP requires that the key k be in the domain of the mapping,returns the value to which kis mapped, and does not change the state of the symbol table (sr'= st).DELETE also requires that the key k be in the domain of the mapping and modifies the table by deletingthebindingassociatedwithkfrom st ( is a domain subtraction operator). The proof checkerB has been used toprove

Z,a formal method based on set theory,can be used inboth model-oriented and property-oriented styles. Figure 4 gives a modeloriented specification of a symbol table, following the Z notation of Spivey.6 The Proof-checking tools that let users treat state of the table is modeled by a partial algebraic specifications as rewrite rules mapping from keys to values (X +&gt; Y include Affirm,Reve,the Rewrite Rule denotes a set of partial mappings from set Laboratory,and the Larch Prover. Tools X to set Y; a partial mapping relates each (and their associated specification lanmember of X to at most one member of Y). guages) that handle subsets of first-order By convention,unprimed variables in Z logic include the Boyer-Moore Theorem stand for the state before an operation is Prover (and the Gypsy specification lanperformed and primed variables for the guage),FDM (Ina Jo), HDM (Special),and state afterwards. I will use the same conm-EVES (m-Verdi). Finally,tools that vention in the VDM and Larch specihandle subsets ofhigher orderlogicsinfications. clude HOL,LCF,and OBJ.

## Some examples

This section illustrates six well-known or commonly used formal methods,half applied to one simple example and the other half applied to another example.All six methods have been used to specify much more complex systems.

Sometimes,when specifying the same problem using different methods, the resulting specifications look remarkably similar(asin the first three examples),and sometimes they don't(as in the last three).theorems based on Z specifications. The similarity or differenceis sometimes VDM supports a model-oriented speci-

Executable.Some formal methods support executable specifications, specifications that can run on a computer. An executable specification language is by definition more restrictedinexpressive power than a nonexecutable language because its functions must be computable and defined over domains with finite rep-

Figure 4. Z specification of a symbol table.

![Image](C:\Users\Humberto\Desktop\MetodosFormaisClaude\metodos_formais\staging\markdown-auto\docling\wing90a\wing90a_artifacts\image_000004_ccd6e962c61f9bc7232e379ec58c56767b74e0c17dd781fdf07d6f324aa889e3.png)

fication style and defines a set of built-in data types (such as sets, lists, and mappings), which specifiers use to define other types.

```
ST = map Key to Val INITO ext wr st : ST postst' ={} INSERT( k: Key,v : Val) ext wr st:ST pre ke dom st postst'=stU {k → v} LOOKUP( k:Key)v:Val ext rd st : ST pre k∈ dom st post v = st(k) DELETE( k:Key) ext wr st : ST pre k∈ dom st post st'= {k}  st
```

Figure 5. VDM specification of a symbol table.

the preconditions,specified in pre clauses are made explicit and separate from the postconditions, specified in post clauses.

A preconditiononanoperationisapred icate that must hold in the state on each invocation of the operation;if it does not hold, the operation's behavior is unspecified.A postcondition is a predicate that holds in the state upon return. An operation''s clients are responsible forsatisfying preconditions,and its implementer is responsible for guaranteeing the postcondition.

Thefact that LOOKUPdoes not modify the symbol table (hence st' = st) but INSERT and DELETE do is specified by using rd (for read-only access) instead of wr(for write-and-read access)in the declarationoftheexternalstatevariablesaccessed by each operation.

The VDM specification in Figure 5 defines a symbol table also in terms of a mapping from keys to values. I follow the VDM notation given in Jones.7 The behavior of the INIT, INSERT, LOOKUP, and DELETE operations are the same as specified in the Z specification. However,

Larch is a property-oriented method that combines both axiomatic and algebraic specifications into a two-tiered specification.*The axiomatic component specifies state-dependentbehavior(forexample,side effects and exceptional termination)of programs. The algebraic component specifies state-independentproperties of data accessed by programs. Figure 6 shows a Larch specification of the symbol table example.I follow the Larch notation given in Guttag et al.

The first piece of the Larch specification,calledaninterfacespecification,looks similar to the Z and VDM specifications. For each operation, the requires and ensures clauses specify its pre- and postconditions.The modifies clause lists those objects whosevaluemay possibly change asaresultofexecutingtheoperation.Hence, LOOKUPisnotallowedtochange the state of its symbol table argument,but INSERT and DELETE are.

One difference(not shown in the example)between Larch and VDM (and Larch and Z) is that, if the target programming language supports exception handling, the interfaces would specify whether and under what conditions an operation signals exceptions.Forexample,wecould remove INSERT's requires clause and instead use a specialsignals clause inits postcondition to specify that a signal should beraised in thecasethat thekeykisalreadyinthe symbol table.

The second piece of the Larch specification,called a trait, looks like an algebraic specification. It contains a set of function symbol declarations and a set of equations that define the meaning of the function symbols.The equations determine an equivalence relation on sorted terms.Objects of the symbol\_table data type specified in the interface specification range over values denoted by the terms of sort S.

The generated by clause states that all symbol table values can be represented by terms composed solely of thetwofunction symbols, emp and add. This clause defines an inductiverule ofinference andis useful for proving properties about all symbol table values.

The partitioned by clause adds more equivalences between terms.Intuitively,it states that two terms are equalif they cannot be distinguished by any of thefunctions listed in the clause.In the example,we could use this property to show that order of insertion of distinctkey-value pairs in the symbol table does not matter, that is, insertioniscommutative.

The exempting clause documents the absence of right sides of equations for rem(emp) and find(emp); the requires and signals clauses in the interface specification deal with these "error values." The converts and exemptingclauses together provide a wayto state that this algebraic specificationis sufficiently complete.

Syntax analyzers exist forLarch traits and interfaces. The Larch Prover has been usedtoperform semantic analysis on Larch traits.

The user-defined function symbols in a Larch trait are exactly those used in the pre- and postconditions of the interface

COMPUTER

specification; they serve the same role as the built-in symbols like U and  used in the Z and VDM specifications.

Unlike Z and VDM,Larchdoes not comewith anyspecialbuilt-innotation nor with any built-in types. The advantage is that the user does not have to learn any special vocabulary for those concepts and isfreetointroducewhateversymbolsheor she desires,giving them theexact meaning suitable for the specificand set.Exactly those properties of a data type being specifiedneedbestatedexplicitly andsatisfied by an implementation.

The disadvantage is that the user may often need to provide a large set of userdefined symbols,as well as the equations that define their meaning.Since I modeled symbol tables in Z and VDM in terms of finite mappings, I did not need to state explicitly that insertion is commutative. This is a property of mappings — the commutative property came for free.The Larch handbookserves as a compromise between the two extremes in that it provides a library of traits that define many general and commonly used concepts (for example, properties of finite mappings, partial orders, sets, and sequences).

Concurrency: Temporal logic, CSP, transition axioms. As mentioned before, many formal methods for specifying the behaviorofconcurrentanddistributedsystems differ because of their choice in semantic domain. Some focus on just the states,someonjusttheevents,andsome on both.To be more concrete here,I will modelasystem'sbehavior as asetof linear sequences of states and associated events. An alternative approach, used by CCS and EMC,is to model a system's behavior as a set of trees of states and associatedevents. When a specification is interpreted with respect to sets of sequences, separating properties of concurrent and distributed systems into two general categories,safety and liveness,is common.Safety properties ("nothing bad ever happens") include functional correctness, and liveness properties ("something good eventually happens") include termination.

```
symbol_table is data type based onSfrom SymTab init = proc () returns (s: symbol_table) ensures s'=emp^ new(s) insert = proc (s: symbol_table,k: key,v: val) requires ~ isin(s,k) modifies (s) ensures s' = add(s,k,v) lookup = proc (s: symbol_table,k : key) returns (v: val) requires isin(s, k) ensures v'= find(s,k) delete = proc (s: symbol_table, k : key) requires isin(s,k) modifies (s) ensures s' = rem(s,k) end symbol_table SymTab: trait introduces emp:-→ S add: S,K,V -→ S rem: S,K -→ S find: S,K -→ V isin: S,K -→ Bool asserts S generated by (emp, add) S partitioned by (find, isin) for all (s: S,k,k1 : K,v : V) rem(add(s,k,v),k1) == if k = k1 then s else add(rem(s,k1),k,v) find(add(s,k,v),k1) == if k = k1 then v else find(s,k1) isin(emp,k) == false isin(add(s,k,v),k1) == (k = k1) v isin(s,k1) implies converts (rem,find,isin) exempting (rem(emp),find(emp)) end SymTab
```

Figure 6. Larch specification of a symbol table.

Temporal logic is a property-oriented method for specifying properties of concurrent and distributed systems. For a given temporal logic inference system, specialmodal operators conciselystate assertions about systembehavior.Specifiers use these operators torefertopast,current, and future states (or events).

There is no one standard temporal logic inference system nor one standard set oft operators.Modaloperators commonly used are ,, and O. Informally, when interpreted with respect to a sequence of states, P says that in all future states,the state predicate P holds; P says that in some future state,Pwill hold;and OPsays that in the next statePwill hold.For example, P=→Q says that if Pholds in the current state,Q will eventually hold.Temporal logic notation tends to be terse,and a temporal logic specification is simply an unstructured set of predicates,all of which must be satisfied by a given implementation.

Figure 7 presents a temporal logic specification of thebehavior of anunbounded buffer in an asynchronous environment. The exampleis adapted fromKoymans et al.,using the temporal logic system in Pnueli,0 which has 12 modal operators. Theformulas areinterpretedwithrespect to sequences of events.A buffer has a left input channel and a right output channel. The expression&lt;c!m&gt; denotes the event of placing message m on channel c. The first predicate,

(right!m)=(left!m)

```
<right!m)=(left!m) (1) (right!m)^(right!m))=(left!m)^(left!m) (2) (left!m)^<left!m)=(m ≠m) (E) (left!m) →(right!m) (4)
```

Figure 7. Temporal logic specification of an unbounded buffer.

states that any message transmitted to the right channel(&lt;right!m&gt;)must have been previously placed on the left channel (&lt;left!m&gt;). The second predicate,

<!-- formula-not-decoded -->

states that messages are transmitted first in,first out. If message m placed on the output channel is preceded by some other message m'alsoon the outputchannel( &lt;right!m'&gt;), there must have been a preceding(thesecond)eventofplacingm on the input channel (&lt;left!m&gt;） and, moreover,anevenearlierevent that placed m' on the input channel ahead of m( &lt;left!m'&gt;). The third predicate,

(left!m)^(left!m))→(m≠m)

states that all messages are unique. For each message m currently placed on the inputchannelandforeachpreviouslyplaced message m'(  &lt;left!m'&gt;),m and m' are not equal. This property is not a property of the buffer,but an assumption of the environment. This assumption is essential to thevalidityofthespecification.Withoutit, a bufferthat outputs duplicatecopiesof its input would be considered correct.

Whereas thefirst three predicates state safety properties of the system (and its environment),thefourthpredicate,

(left!m))=(right!m))

states a liveness property: Each incoming message will eventuallybe transmitted.

CSPuses a model-oriented method for specifying concurrent processes and a property-oriented method for stating and proving properties about the model.CSPis based on model of traces,or event sequences, and assumes that processes communicate by sending messages across channels.Processes synchronize onevents so the event of sending output message m on named channel cis synchronized with theeventofsimultaneouslyreceivingan input message on c. Figure 8 gives a CSP specification of an unbounded buffer (adapted from Hoare"'). BUFFER itself is specified to be a process P that acts as an unbounded buffer. The recursive definitionofPisdividedintotwoclausesto handle the empty and non-empty cases. The first clause,

<!-- formula-not-decoded -->

says that if the bufferis empty,in the event that there is a message m on the left channel (left?m), it will input it. In CSP, if x is an event and P is a process, the notation x → P denotes a process that first engages in the event xand thenbehaves exactly as described by P. The second clause,

```
BUFFER =P<> where P. <>= left?m -→ P<m> and P<m>s = (left?n -→P <m>p<n> right!m →> Ps) BUFFER sat (right ≤ left)^ (if right = left then left  ref else right E ref)
```

Figure 8. CSP program and specification of an unbounded buffer.

<!-- formula-not-decoded -->

says that if the buffer is non-empty,then either the buffer will input another message n from the left channel, appending it to the end of the buffer,or output the first message in the buffer to the right channel. CSPusess^ttodenote theconcatenation of sequence s to sequence t.It usesIto denote choice: If x and y are distinct events, x -→ Ply → Q describes a process that initially engagesineither xory.After this first event,subsequentbehaviorisdescribedby P,if the first event was x,and by Q,if the first event was y.

In CSP's formalism, BUFFER is a CSP program; you can state and prove properties about the tracesit denotes.Using algebraic laws on traces,you can formally verify that agivenCSPprogram satisfiesa specification on traces. The last line in Figure 8 states that BUFFER describes a set of traces,each of which satisfies the predicate given on the right side of sat.The predicate's first conjunct says that the sequence of (output) messages on the right channel is a prefix of the sequence of (input) messages on the left channel. CSP uses the notation s ≤ t to denote that the sequence s is a prefix of sequence t. The prefixpropertyofsequencesguarantees that only messages sent from the left will be delivered to the right,only once,and in the same order.The second conjunct says thatthe process neverstops:it cannot refuse tocommunicate oneither theright or left channel. This implies that input messages willeventuallybe delivered,which is the same property as stated in the temporal logic specification's fourth predicate.

B,previously mentioned for proving theorems from Z specifications,has also been used to prove properties of CSP specifications. Occam is a programming language derivative of CSP that has been implemented and used on Transputers.

Lamport's transition axiom method combines an axiomaticmethod for describing thebehavior ofindividual operations with temporallogic assertions for specifying safety and liveness properties. In thebuffer example of Figure 9(adapted from Lamport'2), I use his original notation,although Lamport introduced twoother notations in a more recent description of his method.2

In the example, the functions, buffer, parg,and gval define the state of the buffer, which has two operations, PUT and GET, and an initial size of O.For this example, we assume thatinvocations of different

COMPUTER

operations can be active concurrently,but at most oneinvocation ofa givenoperation can be active at once.

The predicates at(OP),in(OP), and after(OP)state whether control is at the pointof calling the operationOP,within the execution of OP,or at the point of return from OP.

The first pair of safety properties states that thevalueof thestatefunctionparg is equal to theinputparameter toPUT at the timeofcallandequaltoNULLuponreturn.

The second pairstatessimilarproperties for GET. The third pair of properties indicates how the state functions change as a result of executing PUT and GET: If control is in PUT, buffer gets updated by appending the non-NULL message to its end; if control is in GET and the buffer is non-empty,buffer gets updated by removing its first message,which is GET'sreturn value gval. (The * denotes appending an element to a sequence.)

Unlike the temporal logic and CSP examples—but like the Z,VDM,and Larch examples ——— the last example uses keywords and distinct clauses forhighlighting a model of state (state functions), state initialization(initialconditions),andstate changes (allowed changes to).Again,unitusessimilarnotationalconveniencesto highlight synchronization conditions(the enablingpredicatestotheleft-handsideof -→)and safety and liveness constraints on the processes'behaviors. Hence, this last example shows a combination of linguistic featuresborrowedfromformal methods used to specify sequential programs and othersusedtospecifyconcurrentones.

## Bounds of formal methods

Between the ideal and real worlds. Formal methods are based on mathematics but are notentirely mathematical.Formal-

The fourth and fifth properties areliveness properties requiring that PUT return whenever therearefewer thanminmessages in the buffer and that GET return whenever the buffer is non-empty. (The temporal logic operator ~&gt; stands for "leadsto.")These requirements ensure that progress is made,that once control is within the PUT (or GET)operation,control will reach its corresponding return point. The fifth implies that messages received (throughPUT)areeventually transmitted (through GET) since, if control is in GET, it must eventually return.

```
module BUFFER with subroutines PUT,GET state functions: buffer : sequence of message parg : message or NULL gval: message or NULL initial conditions: Ibufferl = 0 safety properties 1.(a) at(PUT) = parg = PUT.PAR (b) after(PUT) = parg = NULL 2.(a) at(GET) = gval = NULL (b) after(GET) = GET.PAR = gval 3.allowed changes to buffer parg when in(PUT) gval when in(GET) (a)α[BUFFER]:in(PUT) ^ parg ≠ NULL → parg'=NULL ^buffer'= buffer *parg (b) α[BUFFER]:in(GET)^ gval =NULL^ Ibufferl> O → gval' ≠ NULL ^ buffer = gval' * buffer liveness properties 4.in(PUT)^Ibufferl<min~>after(PUT) 5.in(GET)^Ibufferl>0~>after(GET)
```

Figure 9.Transition axiom specification of an unbounded buffer.

methodsusersmustacknowledgethetwo important boundaries between the mathematical world and the real world.

Users cross thefirst boundary in codifying the customer'sinformally stated requirements.Figure 10 illustrates this maplike the temporal logic and CSPexamples,ping,where the cloud symbolizes the customer'sinformalrequirements and the oval symbolizes aformal specification of them.

This mapping from informalto formal is typically achieved through an iterative process not subject to proof. A specifier mightwriteaninitialspecification,discuss its implications with the customer, and revise it as aresult of the customer'sfeedback.

andformally characterizethemisinterpretation.For these reasons, it is important that specifiers and customers interact.

Specifiers can help customers clarify their fuzzy,perhaps contradictory,notions; customers can help specifiers debug their specifications. The existence of this boundary should not besurprising because people use formal methods.

The second boundary is crossed in the mapping from the real world to some abstract representation of it. Figure 11 illustrates thismapping,where thecloud symbolizestherealworldandtheoval symbolizes an abstract model of it.

The formal specification language encodes this abstraction.For example,a formal specification might describe properties of real arithmetic,abstracting away from the fact that not all real numbers can be represented in a computer. The formal specification is only a mathematical approximation of the real world. This bound-

At all times, the formal specification is only a mathematical representation of the customer's requirements. On one hand, any inconsistencies in the requirements wouldbefaithfullypreserved in the specifier's mapping.On the other,the specifier mightincorrectlyinterprettherequirements ary is not unique to formal methods or

Figure 10.Mapping informal requirementsfor a formal specification.

![Image](C:\Users\Humberto\Desktop\MetodosFormaisClaude\metodos_formais\staging\markdown-auto\docling\wing90a\wing90a_artifacts\image_000005_8e97cbeb121ed0a45868287a243765f7203173dea77346958cdce378d8ff08ea.png)

computer science in general; it is ubiquitous in all fields of engineering and applied mathematics.

## Assumptions about the environment.

Anotherkindofboundaryisoftenneglected,even byexperienced specifiers.It's the boundarybetweenarealsystemandits environment.Asystemdoesnotrunin isolation;its behavioris affected by input from the external world,which in turn consumes the system's output.

Given that you can formally model the system (in terms of a specification language's semantic domain), then, if you can formally model the environment, you can formallycharacterizetheinterfacebetween a system and its environment. Most formal methodsleave the environment's specification (formal or otherwise)outside the system's specification.An exception is the Gist language used to specify closed systems.In theory,a complete Gist specificationincludesnotonlyadescriptionof the system's behavior, but also of its clients and otherenvironmentalfactorslikehardware.

A system's behavior as captured in its specification is conditional on the environment's behavior:

Environment=System

Thisimplicationsaysthatif the environment satisfies some precondition, Environment, then the system will behave as specified in System. If the environment fails to satisfy the precondition,then the system is free to behave in any way.

Environmentisasetofassumptions.

Figure 11. Mapping the real world to an abstract model.

![Image](C:\Users\Humberto\Desktop\MetodosFormaisClaude\metodos_formais\staging\markdown-auto\docling\wing90a\wing90a_artifacts\image_000006_9932e5275ef43bfe44dc3761ba6c9bfb601012f7cd677bc53ad844ff42dd8b90.png)

Whereas a system specifier places constraints on the system's behavior, the specifier cannot place constraints on the environmentbut canonlymakeassumptions about its behavior.For example,in the temporal logic specification of the unbounded buffer,the assumption thatmessages are uniqueis an obligation the environmentisexpected to satisfy,not a property the buffer is expected to satisfy nor a constraintthesystemspecifiercanplaceonthe environment.

A specifier often makes implicit assumptions about a system's environment when specifying somethinglike a procedure in a programming language because theenvironmentisusuallyfixedoratleast well-defined.

A procedure'senvironmentis definedin terms of the programming language's invocation protocol.A procedure's specificationwilltypicallyomitexplicitmention of thelanguage'sparameterpassingmechanism,or,foracompile-timetype-checked language,that the argument types are correct. The specifier presumablyknows the details of the programminglanguage's parameter-passing mechanism and assumes the programmer will compile the procedure,thereby doing the appropriate type checking.

However, when specifying a large, complex software or hardware system,the specifier should take special care to make explicit as many assumptions about the environment as possible.Unfortunately, whenspecifying alargesystem,specifiers toooftenforgettoexplicitlystatethecircumstances under which the system is expected to behave properly.

In reality, it is impossible to formally model many environmental aspects such as unpredictable or unanticipated events, human error,and natural catastrophes (lightning,hurricanes,earthquakes).Hazard analysis, as a complementary technique to formal methods, can identify a system's safety-critical components. Formalmethods can thenbeused to describe and reason about these components,where reasoningholds onlyfor those system input parameters that are made explicit.

n a strict mathematical sense,formal methods differ greatly from one another. Not only does notation vary, but the choice of the semantic domain and definitionofthesatisfiesrelationbothmake a tremendous difference between what a specifiercan easily and concisely express inonemethodversusanother.Anidiom in one language might translate into a long list of unstructured statements inanother or might not even have a counterpart.

But, in a more practical sense, formal methods do not differ radically from one another.Within some well-defined mathematical framework,they let system developers couch theirideas precisely.The more rigor applied in system development,the morelikely developers are to state requirements correctly and to get the design right and,of course,the more precisely they can argue the correctness of the implementation.

In conclusion,existingformal methods can be used to

- identify many, though not all, deficiencies in a set of informally stated requirements,detect discrepancies betweenaspecificationand animplementation, and find errors in existing programs and systems;
- specify medium-sized and nontrivial problems,especially the functional behavior of sequential programs,abstract data types,and hardware; and
- provide a deeper understanding of the behavior of large,complex systems.

Many challenges remain. In an effort to push against some of the current pragmatic bounds (in contrast to the two theoretical bounds covered in the previous section), theformal methodscommunityis actively pursuing the following goals:

- ·specifying nonfunctional behaviorsuch asreliability,safety,realtime,performance, and human factors;
- combining different methods, such as

COMPUTER

a domain-specific one with a more general one, or an informal one with a formal one;

- ·buildingmore usable and more robust tools,in particular tools to manage large specifications and tools to perform more complicated semantic analysis of specifications more efficiently,perhaps by exploiting parallel architectures and parallel algorithms;
- building specification libraries so systems and their components can be reused based on information captured in their specification (general libraries, like the Larch handbook and the Z mathematical toolkit,and domain-specific ones like that for oscilloscopes, are recent examples);
- ·integrating formal methods with the entire system developmenteffort,forexample,to provide a formal way to record design rationale in the system development process;
- ·demonstratingthatexistingtechniques scale uptohandlereal-world problems and to scale up the techniques themselves;and
- ·educating and training more people in the use of formal methods.

## Acknowledgments

IthankseveralpeopleincludingJohnGuttag and JimHorning,whointroduced me to formal specifications.They have been instrumental in shaping my opinions about the role formal methods canand should playinsystem development. I am grateful toSusan Gerhart for affording me this opportunity to expressmy thoughts about formal methods.I especially credit Jim Horningforsuggesting this article's title,a subject of much controversy,and Joseph Goguen who has suggested that formal methods can be given a formal characterization in terms of institutionswhere semantic abstractionfunctions are institutionmorphisms.Ialso thank all those Nova Scotia,Canada,for helpful feedback and whoattendedFormalMethods89inHalifax, discussion.Finally,I thank Mark Ardis, Dan Craigen, Susan Gerhart,Joseph Goguen,Bob Harper,Jm Horning,LeslieLamport,andDavid Parnasfor their criticalcomments on an earlier draft of this article.

## References

- 1.B.Meyer,"On Formalism in Specification," IEEE Software,Jan.1985,pp.6-26.
2. L. Lamport, "A Simple Approach to Specifying Concurent Systems,，Comm.ACM, Vol. 32, No.1, Jan. 1989, pp. 32-45.
- 3.J.V. Guttag, J.J. Horning, and J.M.Wing, cations to Productive Use,"Science of "Some Remarks onPutting Formal SpecifiComputerProgramming,North-Holland, Vol. 2, No.1, Oct. 1982, pp.53-68.
4. J.V. Guttag, J.J. Horning, and J.M. Wing, "Larch in Five Easy Pieces,"Tech.Report 5,DECSystems ResearchCenter,July1985.
- 5.C.B.Jones,Software Development:A Rigorous Approach,Prentice Hall Int'l, 1980.
- 6.J.M.Spivey,IntroducingZ:ASpecification Language anditsFormalSemantics,Cambridge Univ.Press,1988.
- 7.C.B.Jones,Systematic Software Development Using VDM,Prentice Hall Int'1, 1986.
8. J.V. Guttag, J.J. Horning, and J.M. Wing, "TheLarchFamilyofSpecificationLanguages,"IEEESoftware,Vol.2,No.5,Sept. 1985,pp. 24-36.
- 9.R.Koymans, J Vytopil, and W.P. de Roever, "Real-Time Programming and Asynchronous Message Passing,""Proc.Second ACM Symp.Principles Distributed Programming,1983,pp.187-197.
- 10.A.Pnueli,"Applications of Temporal Logic to theSpecificationandVerification of Reactive Systems:ASurveyofCurrentTrends," in Current Trends in Concurrency:Overviews and Tutorials,W.-P. de Roever and G.Rozenberg,eds.,Lecture Notes in Computer Science 224,Springer-Verlag,N.Y., 1986,pp.510-584.
- 11.C.A.R.Hoare,CommunicatingSequential Processes, Prentice Hall Int'l, 1985.
12. L.Lamport,"Specifying Concurrent Program Modules,"ACMTrans.Programming Languages and Systems,Vol.5, No.2,Apr. 1983,pp.190-222.

## Further reading

Specifying sequential programs and data abstractions.Twokey ideas to good program design are modularity and abstraction.In addition toVDM,Z,andLarch, themethods presented infive of thepapers below (Futatsugi et al.; Luckham and von Henke;Nakajima et al.;Robinson and Roubine; and Wing)focus on specifying modules (for example, functions, procedures, and packages, of sequential programs).Besides proceduralabstraction, data abstraction can greatly enhance a program's design.The use of data abstraction for structuring programs motivated much work in thelate 70s and early 80s on algebraic specification techniques, the focus of the remaining papers in this section.

Burstall, R.M.,and J.A. Goguen,"The Semantics of Clear,A Specification Language," in Proc.1979CopenhagenWinterSchoolAbstract SoftwareSpecification,LectureNotes inComputer Science 86, Springer-Verlag, 1980, pp. 292-332.

Ehrich,H.-D.,"Extensions and Implementations of Abstract Data Type Specifications,"in Math.Foundations ComputerScience1978 Proc.,Lecture Notes in Computer Science 64, Springer-Verlag,Poland, 1978,pp. 155-164.

Ehrig,H.,and B.Mahr,Fundamentals ofAlgebraic Specification 1,Springer-Verlag,Berlin, 1985.

Futatsugi, K., et al.,"Principles of OBJ2," in guages,1985,pp.52-66. Proc.ACMPrinciples ofProgrammingLan-

Goguen, J.A., et al.,"Abstract Data Types as InitialAlgebras and Correctnessof DataRepresentations,"inProc.Conf.ComputerGraphics, PatternRecognition,andDataStructures,ACM, May 1975, pp. 89-93.

Guttag,J.V.,Specification and Application Programming Abstract DataTypes,PhD thesis, Univ.of Toronto,Toronto,Canada,Sept.1975.

Kamin,S.,"Final Data Types and Their Speci fication,"ACMTrans.ProgrammingLanguages and Systems,Vol.5,No.1,Jan.1983,pp.97121.

Luckham,D.C.,and F.W.von Henke,""An for Ada,"IEEE Software,Vol. 2,No. 2,Mar. Overview of Anna,A Specification Language 1985, Pp. 9-23.

Nakajima,R.,M. Honda, and H. Nakahara, "Hierarchical Program Specification and VeriActa Informatica,Vol.14,1980,pp.135-155. fication -- A Many-Sorted Logical Approach,"

Robinson, L., and O.Roubine,"Special ——A Specification and Assertion Language,"Tech. Report CSL-46,Stanford Research Inst.,Menlo Park, Calif., Jan. 1977.

Wand, M., "Final Algebra Semantics and Data TypeExtensions,"J.Computerand System Sciences, Vol. 19, No.1,Aug. 1979,pp. 27-44.

Wing,J.M.,Writing LarchInterfaceLanguage Specifications，"ACM Trans.Programming Languages and Systems, Jan.1987,pp.1-24.

Zilles,S.N.,"Abstract Specifications for Data Types," IBM Research Lab, San Jose, Calif., 1975.

Programrefinement,transformation, andverification.Two complementary techniques for developing provably correctprograms arerefinement andverification.Refinement is a process of adding more andmoreimplementationdetails(for example, choosing a particular algorithm or data representation) until an acceptably efficient implementation is achieved. Of-

ten these refinement steps are a result of little consensus exists today on general applying transformations that are guaran-models of concurrent and distributed systeed topreserve the program's correctnesstemsorlogicsfor reasoning about their from onelevel to the next.Verification is properties. The references below present a the process of proving thata given program widerange of approaches to supplement satisfies a given specification. the CSP, temporal logic,and Lamport's state transition approaches used in this AnExample"IEEE Trans.Sofrware Eng.,Vol. Balzer,R.,"Transformational Implementation: article.Not surprisingly,the particular choice of model or logic can greatly affect 7, No. 1, Jan. 1981, pp. 3-14. theeaseinexpressing and/or proving some property of a given system.

Apt, K.R., N.Francez, and W.P. de Roever,"A ProofSystemforCommunicatingSequential Processes,"ACM Trans.Programming LanBurstall, R.M., and J. Darlington,"A Transfor-guages and Systems, Vol. 2, No. 3, July 1980,

Bauer,F.L.,et al.,TheMunich Project CIP,Vol. 1:TheWideSpectrumLanguageCIP-L,Lecture Notes in Computer Science183,Springer-Verlag,1985.

mation System for Developing Recursive Pro-pp.359-385. grams," J. ACM, Vol. 24, No. 1, Jan. 1977, pp. 44-67.

Constable,R.,et al.,Implementing Math.with theNuprl ProofDevelopmentEnvironment, Prentice Hall, 1986.

Broy,M.,"A Fixed Point to Applicative Multiprogramming,"inTheoreticalFoundations Programming Methodology,M.Broy and G. Schmidt,eds.,ReidelPublishing,1982,pp.565623.

Dijkstra, E.W.,A Discipline of Programming, Prentice Hall, 1976.

Zave,P.,"AnOperational ApproachtoRequirements Specification for Embedded Systems, IEEE Trans.Software Eng.,Vol.8,No.3,May 1972, pp. 250-269.

Specification, verification, and testing tools. Many formal methods provide semantic analysis tools because the underlying semantics of their languages is sufficientlyrestrictedsothatreasoning interms of specifications becomes tractable.As specifications grow in length and complexity,such tools become invaluable to the specifier.Many of the theorem-proving or proof-checking tools described in the papers below dealwith some subset or small extension of first-order logic.The model checking,simulation,and testing tools typically dealwith afinite orbounded state space,and hence can also be used

Chandy,K.M.,and J.Misra,Parallel Programas effective semantic analyzers. Design,Addison-Wesley,1988.

Goldberg,A.T.,"Knowledge-Based Program-Feather,M.,Language Support for the Specifiming:A Survey of Program Design and Con-cationand Developmentof CompositeSystems."" struction Techniques,"IEEE Trans.Software ACM Trans.Programming Languages,Vol.9, Eng., Vol. 12, No.7, 1986,pp. 752-768. No. 2, Apr. 1987, pp. 198-234.

Hoare,C.A.R.,Notes on Data Structuring,Academic Press, 1972,pp.83-174.

Harel,D.,"OnVisual Formalisms,"Comm.ACM, Vol. 31, No.5,1988,pp. 514-530.

Hoare, C.A.R.,"Proof of Correctness of Data "Information Systems Processing  Open SysRepresentations,"Acta Informatica,Vol.1,No. tems Interconnection—LOTOS,"Tech.report, 1, 1972, pp. 271-281. Int'1 Standards Organization, 1987.

Lee,P.,et al.,"The Ergo Support System: An Lynch, N., and M. Tuttle, "Hierarchical CorIntegratedSetofToolsforPrototyping Integratrectness Proofs for Distributed Algorithms," ed Environments,"in Proc.ThirdACM SIGSoft Tech.report, MIT Laboratory for Computer Symp.Software Development Environments, Science, Cambridge, Mass., Apr.1987. Boston, Nov.1988,pp.25-34.

Manna, Z., and A.Pnueli, "Verification of ConManna,Z., and R.Waldinger,"A Deductive current Programs,Part I:The Temporal Frame- gramming Languages and Systems,Vol. 2,No.ofComputerScience,Stanford Univ.,June1981. 1, Jan.1980, pp. 90-121.

Martin-Lof,P.,"Constructive Mathematics and Computer Programming,"in Sixth Int'l Congress Logic,Methodology,andPhilosophy of Science,North-Holland,Amsterdam,1973,pp. 153-175.

Sannella D.,and A.Tarlecki,Program Specification and Development in Standard ML,"in Proc.Symp.PrinciplesProgrammingLanguages,1985, pp. 67-77.

Scherlis,W.L., and D. Scott,"First Steps Toward InferentialProgramming,"inProc.IFIPS 83,Paris, 1983,pp.199-212.

Abrial, J.-R., "B User Manual," Tech. report, Programming Research Group, Oxford Univ., 1988.

Boyer, R.S., and J S.Moore,A Computational Logic,ACMmonographseries,Academic Press, New York, 1979.

Clarke, E.M., E.A.Emerson, and A.P. Sistla, "AutomaticVerification of Finite-State Concurrent Systems UsingTemporal Logic Specifications,"ACMTrans.ProgrammingLanguages and Systems, Vol.8,No. 2,1986,pp. 244-263.

Craigen,D.et al.,"m-EVES:AToolforVerifying Software,"in Proc. 1Oth Int'l Conf. SoftwareEng.,Singapore,Apr.1988,CSPress,Ls Alamitos, Calif.,Order No.849, pp. 324-333.

Garland,S.J.,and J.V.Guttag,"An Overview of LP,TheLarch Prover,"inProc.Third Int'I Conf. RewritingTechniquesandApplications,Chapel Hill, N.C., 1989, pp. 137-151.

Goguen, J.A., "OBJ as a Theorem Prover with Applications to Hardware Verification,"Tech. Report SRI-CSL-88-4R2, Stanford Research Inst., Menlo Park, Calif., Aug. 1988.

Good, D.1.,R.L. London, and W.W. Bledsoe, "An Interactive ProgramVerification System,， IEEE Trans. Software Eng., Vol.1, No.1, 1979, Pp. 59-67.

Gordon,M.,"HOL:AProof-GeneratingSystem for Higher-Order Logic,"inVLSISpecification, Verification,and Synthesis,Kluwer,1987.

Gordon,M.J.,A.J.Milner,and C.P.Wadsworth, Edinburgh LCF,Lecture Notes in Computer Science 78,Springer-Verlag,1979.

Milner,A.J.R.G.,ACalculusofCommunicating Systems,Lecture Notes inComputerScience92, Springer-Verlag,1980.

Nielsen,M.,et al.,"TheRaiseLanguage,Meth od,and Tools,"Formal Aspects Computing, Vol. 1, 1989, pp. 85-114.

Owicki,S.,and D.Gries,"Verifying Properties of ParallelPrograms:AnAxiomaticApproach，" Comm. ACM, Vol. 19, No.5, May 1976,Pp. 279-285.

Owicki,S.,and L.Lamport,"Proving Liveness Properties ofConcurrent Programs,"ACMTrans. ProgrammingLanguages andSystems,Vol.4, No. 3, July 1982, pp. 455-495.

Models and logics for specifying conPeterson, J.L.,"Petri Nets," Computing Surveys, Vol. 9, No. 3, Sept. 1977. Harel, D. et al., "Statemate: A Working Envicurrentand distributed systems.Unlike ronmentfortheDevelopmentof ComplexReacthe situation for sequential programs and Pratt,V.,"Modeling Concurrency withPartialtive Systems,"in Proc.1Oth IEEEInt'l Conf. data abstractions for which there is someOrders,Int'lJParalllrogramming,Vol15,Sofware Eng.,Apr.1988,CS PressLos lam consensus on underlying formal models,No.1,Feb. 1986,pp. 33-71. itos,Calif., Order No. 849.

COMPUTER

T

ule Specification with Examples,"Comm.ACM, Vol. 15, No.5, May 1972,pp. 330-336.

Kapur,D.,andD.Musser,"Proof by Consisten-WorkshopSoftwareSpecification andDesign, cy,"Artificial Intelligence,Vol. 31, 1987, pp.Pittsburgh, 1989,pp.242-248. 125-157.

Kemmerer,R.A., and S.T.Eckmann,"A User's"Verification of VLSI Circuits Using LP" in"Toward a Requirements Apprentice,"in Proc. Manual for theUnisex System，"Tech.report,Proc.IFIPWG10.2,Fusion HardwareDesignFourth Int' Workshop Softrware Specification

Dept.of Computer Science,Univ.Calif.,Santa andVerification,North-Holland,1988. Barbara,Calif.,Dec.1983.

Lescanne,P.,"Computer Experiments with the REVE TermRewriting SystemVenerator,，"in Proc.1OthSymp.PrinciplesProgrammingLanguages,Austin,Texas,Jan.1983,pp.99-108.

Garland, S.J., J.V. Guttag, and J. Staunstrup, Rich, C., R.C. Waters, and H.B. Reubenstein, and Design, Apr.1987,pp.79-86.

Heydon,A.,et al.,"Constraining Pictures withSwartout,W.,"The Gist Behavior Explainer," Pictures,"inProc.IFIPS89,SanFrancisco,Aug.inProc.Am.Assoc.ArtificialIntelligence Conf., 1989. Aug.1983,pp. 402-407.

Levitt,K.N.,L.Robinson, and B.A.Silverberg, "The HDM Handbook,"Tech.Report Vols.1-3, SRI Int'l, Menlo Park, Calif., 1979.

Hunt,W.A.,The Mechanical Verification of a MicroprocessorDesign,"Tech.Report 6,Computational Logic, Inc., 1987.

Moore,A.P.,"Investigating Formal Specification andVerificationTechniques for Comsec SoftwareSecurity,"inProc.1988Nat'l Computer Security Conf.,Oct.1988.

Narendran,P.,and J. Stillman,"Formal Verification of the Sobel Image Processing Chip,"in McMullin,P.R.,and J.D.Gannon,"CombiningCurrent Trends HardwareVerification andAuTestingwith FormalSpecifications:A CasetomatedTheorem Proving,G.BirtwistleandP.A. Study,"IEEE Trans.Sofrware Eng.,Vol.9,No.Subrahmanyam,eds.,Springer-Verlag,1989, 3, May 1983. Pp. 92-127.

Locasso, R., et al.,"The Ina Jo Reference Manual,"Tech.Report TM-(L)-6021/001/000,System Development Corp.,Santa Monica,Calif., 1980.

Rosenblum, D.S., and D.C. Luckham,"Testing Woodcock, J.C.P.,"Transaction Processing the Correctness ofTasking Supervisors withPrimitives and CSP,IBMJ.Research and DeTSL Specifications,"in Proc.ACM SIGSoft 89velopment,Vol.31,No.5,1987,pp.535-45. (Third Symp.SoftwareTesting,Analysis,and Verification),No.TAV-3,1989,pp.187-196.

## Informal and semiformal methods.

Examples. All the work referenced be-  role in software development, too. Some of Lessformal methodscan play animportant of this article.Manydrawupon thehardmethods that are gaining popularity in inware domain. See Clarke and Grumberg's dustry today. Some describe ways to deal examples. cal structuring techniques.Some borrow ideas from the area of artificial intelliBevier,W.R.,"A Verified Operating System gence. In addition, I include a reference to Kernel," Tech. Report 11, Computational Logic,Inc., Mar. 1987. Leveson's work on hazard analysis.

Browne,M.C.,E.M.Clarke,and D.Dill,Alford,M.,"SREM at the Age of Eight: The "Checking the Correctness of Sequential Cir-Distributed Computing Design System," Com- cuits," in Proc. IEEE Int'l Conf. Computer De-puter,Apr.1985,pp.36-46. sign,1985,pp.545-548.

Burrows, M., M. Abadi, and R. Needham, ""A Logic of Authentication,"in Proc.Symp. Operating Systems,1989.

DeRemer,F., and H.H. Kron,"ProgrammingSmall,"IEEE Trans.on Software Eng,June 1976.

AutomaticVerificationofFinite-StateConcur-AnExample,"inProc.FourthInt'IWorkshop rentSystems,"Ann.ReviewComputing Science,SoftwareSpecification andDesign,Apr.1987， Vol. 2, 1987,pp. 269-290. Pp. 79-86.

Wing received SB,SM, and PhD degrees in computer science from theMassachusetts InstiClarke, E.M., and O. Grumberg, "Research on Fickas, S.,"Automating the Analysis Process:tute of Technology. She is a member of the IEEE,the IEEE Computer Society,and ACM.

Jackson, M.A.,Principles Program Design, Academic Press, London, 1975.

Katzan,H.,Systems Design and Documentation:AnIntroductiontotheHIPOMethod,Van Nostrand Reinhold, New York, 1976.

Collins,B.P.,J.E.Nicholls,and I.H. Sorensen, "IntroducingFormal Methods:The CICSExperience with Z,"Tech.Report TR 12.260, IBM, United Kingdom Labs, Hursley, 1987.

Cullyer,W.J.,"Implementing Safety-Critical Systems:The Viper Microprocessor,"in VLSI Specification,Verification,andSynthesis,lu wer,1987.

Delisle, N., and D. Garlan,"Formally Specifying Electronic Instruments,""in Proc.Fifth Int'lParnas, D.L.,"A Technique for Software Mod-

Leveson, N.G., "Software Safety: What, Why, and How,"ACM Computing Surveys,Vol. 18, No. 2, June 1986, pp. 125-163.

The author can be contacted at the School of Computer Science,Carnegie Mellon Universi-ty,Pittsburgh,PA 15213-3890.

COMPUTER

Yourdon,E.,and L.L.Constantine,Structured Design:FundamentalsDisciplineofComputer Programs and Systems Design,YourdonPress, New York, 1978.

![Image](C:\Users\Humberto\Desktop\MetodosFormaisClaude\metodos_formais\staging\markdown-auto\docling\wing90a\wing90a_artifacts\image_000007_54eb732f1e875e8afdb51186b423ed12a9240cd3949c72e61dab4e18c4747129.png)

JeannetteM.Wing is an associate professor of computer science at CarnegieMellonUniversity.Her research interests include formal specifications,programming languages,concurrent and distributed systems,visuallanguages,and, most recently，objectmanagement.Her current research project at CMU involves the application of language semantics to the search and retrieval of objects.She directs the Avalon Project,which focuses on language support for reliable distributed systems,and codirects the Mir6Project,whichfocuses on specifying security constraints ina visual language.ShecontinLarchfamilyof specificationlanguages.
# How to integrate formal proofs into software development - Amazon Science

**Link:** [https://www.amazon.science/blog/how-to-integrate-formal-proofs-into-software-development](https://www.amazon.science/blog/how-to-integrate-formal-proofs-into-software-development)

## Conteúdo Extraído

```text
How to integrate formal proofs into software development - Amazon Science
Close
Close
Research
Research
Research areas
Automated reasoning
Cloud and systems
Computer vision
Conversational AI
Economics
Information and knowledge management
Machine learning
Operations research and optimization
Quantum technologies
Robotics
Search and information retrieval
Security, privacy, and abuse prevention
Sustainability
Our scientific contributions
Publications
Research from our scientists and collaborators.
Conferences
Our experts present and discuss cutting-edge research at scientific meetings globally.
Research areas
Automated reasoning
Cloud and systems
Computer vision
Conversational AI
Economics
Information and knowledge management
Machine learning
Operations research and optimization
Quantum technologies
Robotics
Search and information retrieval
Security, privacy, and abuse prevention
Sustainability
Our scientific contributions
Publications
Research from our scientists and collaborators.
Conferences
Our experts present and discuss cutting-edge research at scientific meetings globally.
News & blog
News & blog
The latest from Amazon researchers
Amazon Science Blog
Technical deep-dives and perspectives from our scientists.
News
Research milestones and recent achievements.
The latest from Amazon researchers
Amazon Science Blog
Technical deep-dives and perspectives from our scientists.
News
Research milestones and recent achievements.
Collaborations
Collaborations
Amazon Research Awards
Overview
Call for proposals
Latest news
Research stories
Recipients
Amazon Nova AI Challenge
Overview
Rules
FAQs
Teams
Research collaborations
Overview
Carnegie Mellon University
Columbia University
Hampton University
Howard University
IIT Bombay
Johns Hopkins University
Max Planck Society
MIT
Tennessee State University
University of California, Los Angeles
University of Illinois Urbana-Champaign
University of Southern California
University of Texas at Austin
Virginia Tech
University of Washington
Amazon Research Awards
Overview
Call for proposals
Latest news
Research stories
Recipients
Amazon Nova AI Challenge
Overview
Rules
FAQs
Teams
Research collaborations
Overview
Carnegie Mellon University
Columbia University
Hampton University
Howard University
IIT Bombay
Johns Hopkins University
Max Planck Society
MIT
Tennessee State University
University of California, Los Angeles
University of Illinois Urbana-Champaign
University of Southern California
University of Texas at Austin
Virginia Tech
University of Washington
Resources
Resources
Code and datasets
AGI Labs
Meet the team building useful AI agents.
Amazon Nova
Try Amazon’s frontier foundation models.
Code and datasets
AGI Labs
Meet the team building useful AI agents.
Amazon Nova
Try Amazon’s frontier foundation models.
Careers
Careers
Careers
Explore our open roles.
Amazon Scholars
Faculty research opportunities on industry-scale technical challenges.
Postdoctoral Science Program
Early-career research opportunities alongside experienced industry scientists.
Careers
Explore our open roles.
Amazon Scholars
Faculty research opportunities on industry-scale technical challenges.
Postdoctoral Science Program
Early-career research opportunities alongside experienced industry scientists.
Social
twitter
instagram
youtube
facebook
linkedin
github
rss
Menu
Research
Research areas
Automated reasoning
Cloud and systems
Computer vision
Conversational AI
Economics
Information and knowledge management
Machine learning
Operations research and optimization
Quantum technologies
Robotics
Search and information retrieval
Security, privacy, and abuse prevention
Sustainability
Our scientific contributions
Publications
Research from our scientists and collaborators.
Conferences
Our experts present and discuss cutting-edge research at scientific meetings globally.
Research areas
Automated reasoning
Cloud and systems
Computer vision
Conversational AI
Economics
Information and knowledge management
Machine learning
Operations research and optimization
Quantum technologies
Robotics
Search and information retrieval
Security, privacy, and abuse prevention
Sustainability
Our scientific contributions
Publications
Research from our scientists and collaborators.
Conferences
Our experts present and discuss cutting-edge research at scientific meetings globally.
News & blog
The latest from Amazon researchers
Amazon Science Blog
Technical deep-dives and perspectives from our scientists.
News
Research milestones and recent achievements.
The latest from Amazon researchers
Amazon Science Blog
Technical deep-dives and perspectives from our scientists.
News
Research milestones and recent achievements.
Collaborations
Amazon Research Awards
Overview
Call for proposals
Latest news
Research stories
Recipients
Amazon Nova AI Challenge
Overview
Rules
FAQs
Teams
Research collaborations
Overview
Carnegie Mellon University
Columbia University
Hampton University
Howard University
IIT Bombay
Johns Hopkins University
Max Planck Society
MIT
Tennessee State University
University of California, Los Angeles
University of Illinois Urbana-Champaign
University of Southern California
University of Texas at Austin
Virginia Tech
University of Washington
Amazon Research Awards
Overview
Call for proposals
Latest news
Research stories
Recipients
Amazon Nova AI Challenge
Overview
Rules
FAQs
Teams
Research collaborations
Overview
Carnegie Mellon University
Columbia University
Hampton University
Howard University
IIT Bombay
Johns Hopkins University
Max Planck Society
MIT
Tennessee State University
University of California, Los Angeles
University of Illinois Urbana-Champaign
University of Southern California
University of Texas at Austin
Virginia Tech
University of Washington
Resources
Code and datasets
AGI Labs
Meet the team building useful AI agents.
Amazon Nova
Try Amazon’s frontier foundation models.
Code and datasets
AGI Labs
Meet the team building useful AI agents.
Amazon Nova
Try Amazon’s frontier foundation models.
Careers
Careers
Explore our open roles.
Amazon Scholars
Faculty research opportunities on industry-scale technical challenges.
Postdoctoral Science Program
Early-career research opportunities alongside experienced industry scientists.
Careers
Explore our open roles.
Amazon Scholars
Faculty research opportunities on industry-scale technical challenges.
Postdoctoral Science Program
Early-career research opportunities alongside experienced industry scientists.
Search
Submit Search
Cloud and systems
How to integrate formal proofs into software development
ICSE paper presents techniques piloted by Amazon Web Services’ Automated Reasoning team.
By
Daniel Schwartz-Narbonne
May 27, 2020
4 min read
Share
Share
Copy link
Email
X
LinkedIn
Facebook
Line
Reddit
QZone
Sina Weibo
WeChat
WhatsApp
分享到微信
x
Conference
ICSE 2020
Related publications
Code-level model checking in the software development workflow
Formal verification is the process of using automatic proof procedures to establish that a computer program will do what it’s supposed to. Given a mathematical specification of how a function is supposed to behave, and some assumptions about the environment where the code executes (e.g., how the operating system behaves and which inputs are reasonable), formal verification determines whether the code as written will ever, with any input that meets the assumptions, violate the specification.
Formal verification is known to produce more secure and less buggy code, but it’s rarely used on large commercial software projects. Developers working on deadline lack time to write careful function specifications — if they’re even familiar with the formal languages typically used for them. Verification teams, conversely, lack familiarity with the software under development; learning how every function in a commercial-scale program is supposed to behave can be prohibitively time consuming.
An example of how developers might embed function specifications in their code.
On the Amazon Web Services’
Automated Reasoning
team, we’ve piloted several projects on integrating formal verification into the software development process. Some involve verification at the protocol level; some involve generating code directly from a verified specification; and some involve verification at the code level itself.
In a
paper
we’ll present at the International Conference on Software Engineering — which was to be held this week but has been postponed until July — we describe lessons learned from one of the code-level verification projects, which involved a large development initiative in 2019.
In the paper, we report that, thanks to our methodology, the number of verified lines of code, bugs found and fixed, verification “contracts” introduced by developers, and working code (i.e., non-proof code) contributed by the verification team all increased precipitously in the first eight months of the project.
Thousands of lines of code verified over the first eight months of a large AWS development project. The graph flatline indicates that we hit our target for this experiment.
Our method has six key components:
1. Function specification in a familiar programming language.
Writing function specifications typically requires a special-purpose formal language that can capture all of the logical relationships that might govern a function’s execution. With our method, both the verification team and the developer team instead specify functions in the language in which the code is being written — in this case, C. This approach sacrifices some expressive power: there are some logical relationships that C cannot capture. But we have found that ease of adoption more than makes up for the loss of expressivity.
2. Declarative function specification.
Most familiar programming languages — such as C — are
imperative
, meaning they describe functions as sequences of operations. For function specification, however,
declarative
syntax is more intuitive. For instance, the developer should be able to say (in slightly more formal terms), “This function doubles each value in an array”, rather than having to write out the procedure for stepping through the array and doubling values individually. With our method, the verification team provides a library of functions that enables developers to write such declarative specifications in a familiar imperative language.
3. Code-embedded specifications.
Most program functions are written as self-contained blocks of code. With our method, we allow the developer to write a function specification as a set of preconditions that precede each such block — which function inputs are invalid, for instance — and a set of postconditions after each such block — that an array has adequate memory allocated to it, for instance
(see sample code, above)
. Usually, a developer writing a function is thinking through such operational parameters, anyway, so adding the specification is not a huge burden.
4. A proof model that uses a familiar “unit test” syntax.
Many developers are already familiar with writing “unit tests” for their code. Inserted into the code for a specific program function, the unit test cycles through a sequence of inputs to determine whether any cause errors. Our proof method uses a very similar syntax, except that, rather than a sequence of concrete inputs, it specifies a range of possible inputs. Such test code can automatically be converted into the type of mathematical expression that automated provers are designed to evaluate.
Number of bugs found over the first eight months of the project.
5. Bug repair.
The great advantage of formal verification is that it not only identifies bugs but indicates how to fix them, by pinpointing exactly which lines of code lead to violation of the function specification. We have found that one of the most effective means of selling developers on the utility of formal verification is for the verification team to not only identify bugs but provide code patches for them.
6. Continuous integration.
On large software projects, code is constantly being revised. As part of our method, we provide a back-end system that automatically re-runs the prover on new code as soon as it’s checked in to a repository, providing immediate feedback on whether the revision does or does not violate function specifications.
The interface for our continuous-integration engine, indicating newly checked-in code that does
(x’s)
or does not
(check marks)
violate existing function specifications.
In the paper, we report the application of our methodology during development work on the AWS C Common Library, an open-source repository of functions used by several other AWS libraries, including widely used AWS software development kits.
Using our methodology, one full-time verification engineer and two interns, working together with the development team, were able to specify and verify (with some assumptions) 171 entry points (points in the program where the user can input data) over nine key modules of the library.
In ongoing work, we are expanding not only the code base to which we apply our methodology but also the range of functionality that our method can verify automatically. We are also evaluating best practices for long-term maintenance of provable code and for bringing new developers up to speed on existing provable code bases.
Research areas
Cloud and systems
Security, privacy, and abuse prevention
Automated reasoning
Tags
Formal verification
Model checking
Provable security
Conference
ICSE 2020
Related publications
Code-level model checking in the software development workflow
About the Author
Daniel Schwartz-Narbonne
Daniel Schwartz-Narbonne is a senior software development engineer in Amazon Web Services' Automated Reasoning Group.
Related content
Demystifying AI agents
Marc Brooker
October 16, 2025
Amazon vice president and distinguished engineer Marc Brooker explains how agentic systems work under the hood — and how AWS’s new AgentCore framework implements their essential components.
Cloud and systems
Amazon Nova AI Challenge returns with Nova Forge access for competing teams
Staff writer
February 2, 2026
For the first time in an academic competition, students can customize frontier AI models to build trusted software agents
Machine learning
How Amazon uses AI agents to anticipate and counter cyber threats
Daniel Weiss
November 24, 2025
Amazon's competitive-agent architecture creates a continuous improvement cycle that develops security protections at machine speed, reducing what typically takes weeks down to hours.
Security, privacy, and abuse prevention
Work with us
See more jobs
See more jobs
Applied Scientist, Amzn Shipping-Prd & Tech
IN, HR, Gurugram
Our customers have immense faith in our ability to deliver packages timely and as expected. A well planned network seamlessly scales to handle millions of package movements a day. It has monitoring mechanisms that detect failures before they even happen (such as predicting network congestion, operations brea
... (conteúdo truncado)

```

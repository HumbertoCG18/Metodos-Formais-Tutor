# The Young Software Engineers Guide to Using Formal Methods | K. Rustan M. Leino, Amazon | 07.06.2018 at 10:16 | Part of EPFL IC Research Day 2018 | Lausanne, Switzerland

**Link:** [https://portal.klewel.com/watch/webcast/epfl-ic-research-day-2018/talk/3/](https://portal.klewel.com/watch/webcast/epfl-ic-research-day-2018/talk/3/)

## Conteúdo Extraído

```text
The Young Software Engineers Guide to Using Formal Methods | K. Rustan M. Leino, Amazon | 07.06.2018 at 10:16 | Part of EPFL IC Research Day 2018 | Lausanne, Switzerland
Conferences
About us
Login
Sign up
Conferences
/
EPFL IC Research Day 2018
/
The Young Software Engineer’s Guide to Using Formal Methods
Player is loading...
Info
Transcription
Embed
The Young Software Engineer’s Guide to Using Formal Methods
K. Rustan M. Leino, Amazon
Thursday, June 7, 2018
							  ·  
							10:16 a.m.
							  ·  
							
								
									01h 
								
								
									07m 
								
								23s
Embed
Copy embed code
Player is loading...
Transcriptions
Note: this content has been automatically generated.
00:00:00
but
00:00:02
well thank you all for coming and it's five pleasure to and to
00:00:06
talk to about using formal methods and i'm going to concentrate on
00:00:11
uh how you get started with what formal methods and some of the things that um
00:00:15
that you can apply for so um it's only fair to start off by saying what what are formal methods
00:00:22
a formal methods are a mathematically based or logically based
00:00:27
approach to uh to writing software and by writing software i mean
00:00:32
writing specifications that say what the software supposed to do a writing the code that's actually going to
00:00:38
to execute on the machine and then trying to connect those two pieces in in some sort
00:00:43
of way that is that through verification to check that the code is really doing what what
00:00:47
the specifications are telling us that the uh what we intend for the software to do
00:00:53
so it's um it's also good to explain the various words i had on my
00:00:58
longs title slide so formal methods was one and young software engineers was another
00:01:04
so what are young software engineers today well they're probably
00:01:08
engineers software engineers were just starting college maybe
00:01:11
i'm maybe they've gotten started in college maybe there are few years um until they start college
00:01:18
how can these people be um be getting exposed to formal methods so that they can use it in fact
00:01:25
is as they're developing software um and in industry or for uh for any other purpose so um
00:01:34
um formal methods are mathematically based that is logically based or they are precise
00:01:40
in some ways but why is that something that we would like
00:01:44
well there are a fair number of of of considerations
00:01:47
in software uh production today and one is correctness
00:01:52
when you when you write the program you um you would like to to make sure that doesn't crash that
00:01:58
is perhaps one of the one of the first things that you would think about software uh and um
00:02:03
in the um but twenty years ago we started
00:02:06
seeing in the press affecting serve everyone's lives
00:02:10
various is a source of um security attacks uh there were typically at that point um
00:02:17
it came through buffer overruns a buffer over on is just
00:02:21
uh your computer accessing memory word word shouldn't be so these
00:02:25
are program errors that allow certain kinds of security attacks
00:02:29
so memory safety is something that we would like well memory safety is something
00:02:33
that you can obtain if you start using the language that um
00:02:39
that is type safe that does not allow you to access any part of of memory like for example
00:02:44
c. program but there are other other things that you would consider as well you have um
00:02:50
you have run time exceptions so if you run a java program for example
00:02:55
um the program may it may all the sudden and because you've uh you've attempted some operation that was not allowed
00:03:02
so the good thing with that is that as the program and
00:03:06
setup point you're not uh you're not inviting further security attacks
00:03:11
but uh but having such problems in your software means that your your customers
00:03:16
are going to be um a bit worried by by this behaviour
00:03:20
and perhaps customers go to different uh different platform different application
00:03:25
and stop using stop using your apps stop using your web sites uh
00:03:29
they don't trust you anymore they they want to do something different
00:03:32
but it's also costly to and to fix these things later now
00:03:38
if it's yes is a crash you can't fix them by um
00:03:42
by reporting by collecting various kinds of uh a crash reports
00:03:47
that various apps and um and the software programs would report
00:03:51
back to you so because of the the software deployment
00:03:55
that process today you can get these things out to customers rather quickly for example if you have
00:04:02
uh if your um if errors are on the on the website you can just update your software on
00:04:07
the website you don't need to update that millions of apps all um all of the world
00:04:13
but then there's one more step which is that of functional correctness so why would you want to go all
00:04:19
the way to functional correctness to make sure that that your program is correct well sometimes you don't
00:04:25
some programs it's okay if they don't if they don't always work
00:04:29
um and wise that well there's lots of priorities uh
00:04:33
you um you may want to release the product just as quickly as you can um you may want to um
00:04:40
um to spend less money because you want to see that you are these
00:04:44
the features that the customers would want to have in the first place
00:04:47
no that's um these are strategies that's some uh some groups
00:04:51
and software companies uh it may choose to to apply
00:04:55
so i would not expect in the future that all software is going to be verified
00:04:59
to be functionally correct but there are places where functional correct this really matters
00:05:05
no one place where you would like to go beyond just the
00:05:08
the simple crashed for unison programs is the area of security
00:05:13
and when you when you deal with security there is no such thing
00:05:16
as as having a program that is just partially secure that's
00:05:20
it's not going to be just a little bit secure it's either secure or does and uh if it if it
00:05:25
has folder abilities that attackers can uh can make use of
00:05:29
then your data um uh is is not safe so
00:05:34
putting a price at obtaining security is something that um
00:05:38
uh that you may want to do that that is if you um if you have a resource budget for
00:05:44
for your programmers for your software engineers putting effort into making sure
00:05:49
that things are secure uh is a good thing and um
00:05:53
so security is that is a really difficult thing even for experts and um if you have all of
00:05:59
the the literature in the last uh twenty thirty years you will found a a number of
00:06:05
uh problems in uh and encrypted graphic protocol sort of number breakage is
00:06:10
and uh so even with the experts these are difficult things
00:06:13
to do but if you're if you're an amateur just getting used to things then uh then you probably shouldn't attempt it
00:06:20
but if you do you see i'm paying a special attention to all of all areas of correctness is is really key
00:06:26
you know these are things that that you may see if you're
00:06:31
if you're going to develop programs in uh in and say i'm in a company setting
00:06:35
uh you have some products that you're that you're putting out there but what about
00:06:39
what about all the rest of us who are writing software in in various other ways that perhaps are not
00:06:44
as important we think well you still need you still need to think about getting a program correct
00:06:50
even if your program is not the highly the most highly critical software
00:06:55
that that you're producing you still need to have some mindset
00:06:59
uh some uh some techniques everything about your program that lets you figure out
00:07:05
is this program really going to work or not but it's it's it's not okay to just
00:07:09
had various statements the program and then hope that one day perhaps it is going to
00:07:13
be cracked you need to actually think about what these things are just like
00:07:17
other kinds of engineers would have various methods of calculating if we're
00:07:22
bridges gonna stand up and and so forth there are methodology
00:07:25
sinner techniques in software engineering that let you think about programs to make sure that they that they really are okay
00:07:31
and the good thing here is that there's plenty of tools support today um there wasn't a tool support
00:07:37
for these things say twenty twenty five years ago a lot of things have happened since then
00:07:42
and um so you can get a lot of help and that help can be their balls for
00:07:46
teaching people about how to how to reason about software and also using it in fact this
00:07:52
okay so i'm in the future the new software engineers the young software engineers of today
00:07:59
uh or a likely to see these sort of uh the first a crack this insecurity issues a lot more
00:08:05
um the um with data being stored uh even more so when in the cloud
00:08:10
uh you worry about security and making sure that that everything is um
00:08:14
uh is kept safe uh and um and the tools can help with that
00:08:19
so um what about the cost if you mean it would be really great to be able to have a ball that that says
00:08:26
using formal methods is going to make your software development keeper is going to let you
00:08:31
get there faster is going to let you compete better as well um then
00:08:39
many of us would have that feeling that we can get there but if you look at measurements i think
00:08:44
there's only one project that really has a lot of these measurements and jim uh mention this project project
00:08:50
it's the s. c. l. for project in them from australia
00:08:54
which build a um a a micro kernel and um
00:08:59
uh that colonel has um when it started it was about ten
00:09:04
thousand lines just under ten thousand lines of of c. code
00:09:07
which is not a lot of code it's something that you could you would think are sure i can write that in a weekend
00:09:12
but uh can you write it correctly the question and to begin with uh
00:09:17
they had about two hundred thousand lines of specifications and prove scripts
00:09:24
so that is about twenty times the the number of lines of executable
00:09:29
code well today that number is is even higher because because
00:09:33
this group has has had a lot of things so in fact i think that these numbers a little bit outdated even so
00:09:39
but the but you can see that there's a large ratio here of lots of
00:09:43
lines of specifications and prove steps to the number of of lines of code
00:09:49
so now you might say cheese this what i'm in for well that one thing is that we're all
00:09:54
learning how to do these sorts of things and uh they have had a particular tool set here
00:09:59
they have a dealt with a number of especially tricky problems but they've also done
00:10:05
measurements over these many years and i think that this group has done
00:10:09
that these measurements uh breast but it's actually no one else has and what they have shown that compared
00:10:15
to other less packed this is approaches that even with these numbers that you may think are
00:10:19
our um extremely um large of of a large gap between the ten thousand
00:10:25
in the five hundred thousand lines of of uh specs improves is that
00:10:30
compared to other that's packed this as they found that they're only somewhere between a factor
00:10:34
of two and three away from the cost of developing something similar you saying
00:10:39
uh other best back this is like a testing and and things like that and of course when
00:10:43
you write test suites those add up to a lot of lines of code as well so
00:10:49
if you believe these numbers are representative and if you believe that we can do better
00:10:53
than the the ratio of well as i'm showing here fifty fifty two to one
00:10:59
uh if we could do to improve that ratio only to by a factor of two or three
00:11:04
then maybe we couldn't set here and make the the argument that is always going to
00:11:08
be caught more cost effective for these sorts of projects to to apply formal methods
00:11:13
so you know the case it's showing that when you when you
00:11:18
strive for tools uh correctness when you want to make
00:11:21
sure that things really are correct and secure there are techniques that can help you get in in in that direction
00:11:28
okay so there are pieces of code that you would like
00:11:32
even today uh let's say you're writing a variation of
00:11:36
binary binary so a binary search and instead of i'm wanting to find
00:11:41
exact elements the exact index where something is you want to find
00:11:45
the place where you want to insert something if it isn't actually in the in the right that's like
00:11:50
so maybe have or a library routine for doing this or maybe you're gonna write it yourself your writings such
00:11:56
a routine yourself and you could imagine a lot of other routines that you would write of this work
00:12:00
there is no reason for you to to have any errors in this code at all
00:12:05
would you probably want to do is you're gonna test it a few times if you're good software engineer you
00:12:10
will write um a test suite that you that you incorporate with them with every building every every change
00:12:15
but you can do even better than that have not too much cost if you understand
00:12:19
what these methods are now i'll show you some of of that as well
00:12:24
and um the formal methods as i mentioned before just that
00:12:27
the reasoning process itself the thinking process that goes on
00:12:31
uh that when you use formal methods is um is going to help you be be a better software dinner
00:12:37
so well how is it on there are three areas would be may think about here um verification specification and development
00:12:44
i had these on in a different word or uh in that we're not defined formal methods on the previous slide them good putting them
00:12:51
in this war because i think that this is perhaps how most people think of of things they might think of verification first
00:12:59
well i have some piece of code i'd like to make sure that it's correct how can
00:13:02
i make sure it's correct well i'm i might wish for just the push button tool
00:13:07
another or in such areas where uh being able to run the pushbutton two
00:13:13
or maybe running it tool but some specification that some expert road
00:13:17
um and it one example of this is the uh the slam project that
00:13:21
took place um in fact in them a gym there's group and um
00:13:27
when norm well almost twenty years ago now at uh at microsoft and uh this is the kind of a pushbutton
00:13:33
technique where you could have a a tool that uh that tries to find yours in a program for you
00:13:39
but if you want to extend this t
... (conteúdo truncado)

```

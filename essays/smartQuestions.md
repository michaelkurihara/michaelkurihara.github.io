---
layout: essay
type: essay
title: "Stack Overflow Is Not Your Tech Support: A Question of Clarity, Commitment, and Professionalism"

# All dates must be YYYY-MM-DD format!
date: 2018-01-25
labels:
  - Learning
  - Computer Science
  - How to ask for Help
  - Professionalism
  - Neti
---

## Stack Overflow Is Not Your Tech Support

Eric Steven Raymond's "How To Ask Questions The Smart Way" is an insightful and provocative guide on
"how to ask questions in a way more likely to get you a satisfactory answer."  Many of Mr. Raymond's suggestions can be
grouped in three categories:
- Professionalism (i.e., showing courtesy, patience, post your question to the right forum, tact, and gratitude) - Clarity (i.e., clearly stating your problem, what you have done so far, and what you are trying to do) - Commitment (i.e., the effort you put into your project and your question) ## Of Professionalism: Many of Mr. Raymond's insights are self-evident, or at least they should be, but they stating to hammer in their importance.  He nails one of his most important the beginning of his essay, and it is that you cannot "assume that the author of an informative webpage wants to be your free consultant."  While he is speaking about writing directly to an individual in this example, it not a stretch to apply this idea to posting to forums.  Later, he reinforces this idea by saying:  "Make it clear you appreciate the time people spend helping you for free."  The key word here is "free."  Again, this obvious, but it highlights a critical difference that threw me because I take civility and professionalism seriously. I work at UHM School of Nursing and Dental Hygiene's Office of Student Services.  Key word:  "services."  As someone who might be the school's first contact with a new student, it is vital that I make a good impression.  Experience has taught me that there are in fact "stupid" questions as Mr. Raymond points out.  The difference is that I cannot call someone for asking a question that I might have just answered or it is covered on the web site they just professed to have read.   I do understand the impulse to give a "RTFM" or "STFW" type response.  Worse still, I occasionally have to
deal with people having a bad day, and realistically I cannot always give them the answer they want to hear.  So, for
me, I often find reading posts on tech forums a little grating.
  
Sometimes it is the person asking the question, sometimes it someone "trying" to help, sometimes it is the bickering
between responders.  There is a lot behavior that seems "unprofessional," but Mr Raymond's essay is not able turning to
consulting companies for tech support.  He is actually talking about reaching out to a community of volunteers whose
motives and means of communications will be as varied and individuals that make up that community.  One of the more
reassuring discoveries I made while researching this essay was that Meta Stack Overflow included questions that tackled
was behavior of its members, and the community itself can take actions to help police itself.  And, as Mr Raymond
reminds the reader:

>There are also plenty of commercial companies you can contract with for help, both large and small. Don't be dismayed at the idea of having to pay for a bit of help! After all, if your car engine blows a head gasket, chances are you would take it to a repair shop and pay to get it fixed. Even if the software didn't cost you anything, you can't expect that support to always come for free.

Something about the importance of asking questions.

>The first thing to understand is that hackers actually like hard problems and good, thought-provoking questions about them. If we didn't, we wouldn't be here. If you give us an interesting question to chew on we'll be grateful to you; good questions are a stimulus and a gift. Good questions help us develop our understanding, and often reveal problems we might not have noticed or thought about otherwise. Among hackers, “Good question!” is a strong and sincere compliment.

## Of Clarity and Commitment

As I was reading the essay, I thought about those "RTFM" and "STFW" questions, and immediately looked for something that 
seem so simple and obvious, so I Googled how to write for loops in Stack Over Flow, and found: 
[https://stackoverflow.com/questions/4170656/for-loop-in-python](https://stackoverflow.com/questions/4170656/for-loop-in-python),
with the following question under the header "for loop in Python":

>In C/C++, I can have the following loop for(int k = 1; k <= c ; k +=2)
>
>How do do the same thing in Python?
>
>I can do this for k in range(1,c): in Python, which would be identical to for(int k = 1; k <= c ; k++) in C/C++.

This simple and straight forward question, with one typo, was tagged simply with "python."  I happy to report no one posted a "RTFM" or
a "STFW", but clearly this is a question that could have easily been uncovered by checking the official Python
documentation web site.

Now on first appearance, this seems like a fairly straight forward question, but it is actually problematic for the
following 2 reasons:
- What is the goal?  Is there a goal?
- Python2 or Python3?  Vagueness and typos as a warning sign!

## What is the goal? Is There a goal?

One of the tips that I plan to follow from here on out is to include a description of my goal.  In this case, either the
questioner wants to know the answer for the sake of knowing the answer, or it could for some unstated reasons...but 
reading the post, I began to suspect something that the essay mentions, but I was initially skeptical about: 

>Hackers are good at spotting homework questions; most of us have done them ourselves. Those questions are for you to work out, so that you will learn from the experience. It is OK to ask for hints, but not for entire solutions.

I can easily imagine that person asking this question is a student who just learned C and C++, and now it is time to
learn Python.  Maybe I am right, and may be I am wrong.  The lack of clarity about why the user wants to know can have
unexpected consequences.

The first responder to this post got derailed by the question and went so far off on a tangent that they did not
actually answer the question because they assumed they knew what questioner wanted:

>You should also know that in Python, iterating over integer indices is bad style, and also slower than the alternative. If you just want to look at each of the items in a list or dict, loop directly through the list or dict.

```python
mylist = [1,2,3]
for item in mylist:
    print item

mydict  = {1:'one', 2:'two', 3:'three'}
for key in mydict:
    print key, mydict[key]
```

>This is actually faster than using the above code with range(), and removes the extraneous i variable.
>
>If you need to edit items of a list in-place, then you do need the index, but there's still a better way:

```python
for i, item in enumerate(mylist):
    mylist[i] = item**2
```

>Again, this is both faster and considered more readable. This one of the main shifts in thinking you need to make when coming from C++ to Python.

Now the first responder should have asked probably clarified what the questioner planned to do with a for loop first,
but given the nature of the Python community and how zealous they can be about doing things the "Pythonic way" it is not 
so surprising.

The second responder to the post actually answered the question with a simple: 

```python
for k in range(1,c+1,2):
```

This of course spawned a fury of replies over the merits of the code, but at least it answered the question.  Sadly,
the original poser of the question was not one of the people who took part of the conversation, much less thanked the
second responder.
  

## Python2 or Python3?  Vagueness and typos as a warning sign!

In this case, the difference between Python2 and Python3 is not that great given the simplicity of the code, but the
fact that question does not specify which version of Python bellies a greater problem.  How much thought did the
questioner put into the post?  The typo: "How do do the same thing in Python?" is another sign of either laziness
or indifference.

Much of Mr Raymond's tips focus on the importance of taking the time to write a good question.  Not only is a good
question important in terms of getting a the best answer, but it also a demonstration of the questioners commitment to
work for the answer.  As a former teacher, I can tell you that one thing that always bothered me was when a student
would say "I don't get it."  What is it that you are not getting?  Hysterics and panic are no guarantee that someone
really wants to learn as opposed to being spoon fed the answer.  

The problem of course is that it takes time formulate a good question!  You need to spend trying to solve the problem on
your own so that you have a sense of the problem and can in your question you can write about what you have done so far.
You then need to think about the question, and it seem odd, but in way this also part of the problem solving process
because you might figure the problem in the process.  Once you formulate your question, then you actually to proof it to
make sure that it clearly and concisely communicates: 
- Context
- Objective
- What you have done so far
- What is the problem

The irony of course is that this question would not have been hard to salvage.  A better and simple way to ask this
question would have been to ask for a pointer to a good reference or an online Python training program.  

## A Good question!

So, what is a good question?  One technical question that I faced when I first encountered when I started to use 
Ubuntu was a problem updating my clamav.  Thankfully, the person who made this gave it a great header name, so that
finding it on Google was a breeze:

>clamav - ERROR: /var/log/clamav/freshclam.log is locked by another process?

[https://askubuntu.com/questions/909273/clamav-error-var-log-clamav-freshclam-log-is-locked-by-another-process](https://askubuntu.com/questions/909273/clamav-error-var-log-clamav-freshclam-log-is-locked-by-another-process)

The post:

>I have installed clamav and I want to to update the files that it uses to identify viruses:

```bash
$ sudo freshclam

ERROR: /var/log/clamav/freshclam.log is locked by another process
ERROR: Problem with internal logger (UpdateLogFile = /var/log/clamav/freshclam.log).
```

>What should I do with this error?
>
>EDIT:

```bash
$ sudo lsof /var/log/clamav/freshclam.log

COMMAND   PID   USER   FD   TYPE DEVICE SIZE/OFF     NODE NAME
freshclam 866 clamav    3wW  REG  259,1   100134 10486045 /var/log/clamav/freshclam.log
```

What I love about this question is that it is well named, it objective is clear, the problems is clear, and the error
message is clear.  The person who posed the even responded to a question in a reply and added the "EDIT:" section the
post.

## Appreciation

Of course, my favorite part of Mr. Raymond's essay, is the Disclaimer section, which precedes the Introduction:

>Many project websites link to this document in their sections on how to get help. That's fine, it's the use we intended — but if you are a webmaster creating such a link for your project page, please display prominently near the link notice that we are not a help desk for your project!
>
>We have learned the hard way that without such a notice, we will repeatedly be pestered by idiots who think having published this document makes it our job to solve all the world's technical problems.
>
>If you're reading this document because you need help, and you walk away with the impression you can get it directly from the authors of this document, you are one of the idiots we are talking about. Don't ask us questions. We'll just ignore you. We are here to show you how to get help from people who actually know about the software or hardware you're dealing with, but 99.9% of the time that will not be us. Unless you know for certain that one of the authors is an expert on what you're dealing with, leave us alone and everybody will be happier.

And to all the brave souls have risked being "pestered by idiots" by giving up their time to help their peers and the
next generation of hackers, Danke Sch&#246;n!

---
layout: essay
type: essay
title: "Stack Overflow Is Not Your Tech Support: A Question of Clarity, Commitment, and Professionalism"

# All dates must be YYYY-MM-DD format!
date: 2018-01-25
labels:
  - Learning
  - Computer Science
---

## Stack Overflow Is Not Your Tech Support

Eric Steven Raymond's "How To Ask Questions The Smart Way" is an insightful and provocative guide on
"how to ask questions in a way more likely to get you a satisfactory answer."  Many of Mr. Raymond's suggestions can be
grouped in three categories:
- Clarity (i.e., clearly stating your proble, what you have done so far, and what you are trying to do)
- Commitment (i.e., the effort you put into your project and your question)
- Professionalism (i.e., showing courtesy, patience, post your question to the right forum, tact, and gratitude)

Many of Mr. Raymond's insights are self-evident, or at least they should be, but they stating to hammer in their
importance.  He nails one of his most important the beginning of his essay, and it is that you cannot
"assume that the author of an informative webpage wants to be your free consultant."  While he is speaking about writing
directly to an individual in this example, it not a stretch to apply this idea to posting to forums.  Later, he
reinforces this idea by saying:  "Make it clear you appreciate the time people spend helping you for free."  The key
word here is "free."  Again, this obvious, but it highlights a critical difference that threw me because I take civility
and professionalism seriously.

I work at UHM School of Nursing and Dental Hygiene's Office of Student Services.  Key word:  "services."  As someone
who might be the school's first contact with a new student, it is vital that I make a good impression.  Experience has
taught me that there are in fact "stupid" questions as Mr. Raymond points out.  The difference is that I cannot call
someone for asking a question that I might have just answered or it is covered on the web site they just professed to
have read.   I do understand the impulse to give a "RTFM" or "STFW" type response.  Worse still, I occasionally have to
deal with people having a bad day, and realistically I cannot always give them the answer they want to hear.  So, for
me, I often find reading posts on tech forums a little grating.
  
Sometimes it is the person asking the question, sometimes it someone "trying" to help, sometimes it is the bickering
between responders.  There is a lot behavior that seems "unprofessional," but Mr Raymond's essay is not able turning to
consulting companies for tech support.  He is actually talking about reaching out to a community of volunteers whose
motives and means of communications will be as varied and individuals that make up that community.  One of the more
reassuring discoveries I made while researching this essay was that Meta Stack Overflow included questions that tackled
was behavior of its members, and the community itself can take actions to help police itself.  And, as Mr Raymond
reminds the reader:

> There are also plenty of commercial companies you can contract with for help, both large and small. Don't be dismayed at the idea of having to pay for a bit of help! After all, if your car engine blows a head gasket, chances are you would take it to a repair shop and pay to get it fixed. Even if the software didn't cost you anything, you can't expect that support to always come for free.

Something about the importance of asking questions.

> The first thing to understand is that hackers actually like hard problems and good, thought-provoking questions about them. If we didn't, we wouldn't be here. If you give us an interesting question to chew on we'll be grateful to you; good questions are a stimulus and a gift. Good questions help us develop our understanding, and often reveal problems we might not have noticed or thought about otherwise. Among hackers, “Good question!” is a strong and sincere compliment.

## Of Clarity and Commitment

As I was reading the essay, I thought about those "RTFM" and "STFW" questions, and immediately looked for something that 
seem so simple and obvious, so I Googled how to write for loops in Stack Over Flow, and found: 
[https://stackoverflow.com/questions/4170656/for-loop-in-python](https://stackoverflow.com/questions/4170656/for-loop-in-python),
with the following question:

> In C/C++, I can have the following loop for(int k = 1; k <= c ; k +=2)
>
> How do do the same thing in Python?
>
> I can do this for k in range(1,c): in Python, which would be identical to for(int k = 1; k <= c ; k++) in C/C++.

This simple and straight forward question was tagged simply with "python."  I happy to report no one posted a "RTFM" or
a "STFW".  The two most interesting replies were:

>You should also know that in Python, iterating over integer indices is bad style, and also slower than the alternative. If you just want to look at each of the items in a list or dict, loop directly through the list or dict.
> I can do this for k in range(1,c): in Python, which would be identical to for(int k = 1; k <= c ; k++) in C/C++.

```python
mylist = [1,2,3]
 for item in mylist:
     print item

 mydict  = {1:'one', 2:'two', 3:'three'}
 for key in mydict:
     print key, mydict[key]
```

> This is actually faster than using the above code with range(), and removes the extraneous i variable.
>
> If you need to edit items of a list in-place, then you do need the index, but there's still a better way:

```python
> for i, item in enumerate(mylist):
>     mylist[i] = item**2
```

> Again, this is both faster and considered more readable. This one of the main shifts in thinking you need to make when coming from C++ to Python.

Another response that actually answered the initial question and generated the most discussion replies from other
posters:  

> Try using this:
>
> for k in range(1,c+1,2):

:w

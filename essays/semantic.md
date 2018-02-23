---
layout: essay
type: essay
title: How Many Damn Languages Does It Take to Make A Website?!?!

# All dates must be YYYY-MM-DD format!
date: 2018-02-20
labels:
  - Learning
  - Semantic UI
  - Web Development
  - Digital Humanities
---

## How Many Damn Languages Does It Take to Make A Website?!?!

It has almost been twenty years since I wrote my first HTML file.  I have made almost dozen half-hearted attempts to learn how to do some basic web development over the last two decades, and with every attempt I am struck the same conceited question:  How many damn languages does it to make a website?  Seriously?  How many does it take?  

[<img class="ui medium right floated rounded image" src="https://cdn-images-1.medium.com/max/800/1*raWO3dhM4jMjf9VY-kZzNg.png">](https://hackernoon.com/how-it-feels-to-learn-javascript-in-2016-d3a717dd577f)

I wrote my first HTML file back in 1999, so I remember when it was just HTML and CSS.  Over time, this problem has seemingly gotten worse.  A few years ago, I learned about coding boot camps.  I looked up the Javascript developer curriculum for one such boot camp, and I was dumbfounded by the promise to cover "[20+ languages and frameworks](https://www.devleague.com/tracks/view/javascript-web-engineer)."  That seemed both insane and unreal - and I am not referring to the idea of cover all that in 16 weeks.  How could there be 20+ languages and frameworks to learn???  I remember looking up some those languages and framework.  I merely r flipped out over the idea that CSS was not enough and somebodies invented SASS and Less.  I lost my lunch when started to learn more about the Javascript situation!  

Now that I have declared the CS major and I am thinking about going into digital humanities, I think have gained some perspective, and it is one of the reasons I am so excited by the promise of Semantic UI.  But first a brief trip back into history.


## The limits of HTML alone

In 1999, just scant 3 years after the release of CSS, I wrote some HTML for a lecture I was giving on the rise of Islam for History 151: World Civilizations.  I wanted Outline, and HTML seem perfect.  I could make an outline with hyperlinks to images and have all of it projected onto the big screen!  Needless to say, I did not use any CSS.  I wrote all my "styling" in-line.  I did not see the point to using any CSS.  This decision less based on arrogance, and more based in ignorance.  Not mention a ton of laziness.  I am proud to say that I changed the background color!  Thankfully, I never posted my first masterpiece to the www, so there is no evidence of my first best effort. I can say with no ego that as god awful as it seems now, my endeavor was exactly what I wanted.  Like most historians, I like outlines for lecture.  What really matters to us is the narrative we weave with some images thrown into add some color.  By today's standard this does not sound very innovative, but please keep in mind that back in 1999, most of the UHM history faculty were still paring transparencies with an overhead projector!  This was the bleeding edge.

I stole the idea of making a html outline from Prof Karen Jolly, one of the more tech savvy members of the UHM History Department.  Here is a link to one her lecture outlines from the HIST 151 that she taught in 2008: [Christian Culture In Byzantium.](http://www2.hawaii.edu/~kjolly/151f08/081021Byz.html)  I will be the first to concede that this web site now feels as old as its subject matter.  I am big believe in the importance of negative space, but this web site seems also haunted by all its emptiness.  Knowing how Prof Jolly lectures, there is more than enough substance for her to fill in gaps in content.  The void that this web site cannot fill is that at best it does not capture the eye, at worst it offends it.  Know what I know now, I cannot help but thing a little CSS could come to rescue.

In contrast, there is the [National Archives DOCSTeach website}(https://www.docsteach.org/), which is very modern, i.e., stylized.  When I first learned about digital humanities, I realized that part of the problem is that historian cannot just rely on narrative alone.  Would be digital historians need to learn to not only communicate visually, we need to know how to use the tools of the visual medium.  Knowing HTML is not enough anymore.  Back in 1999, I was truly happy with just using html and writing all my styling into the html tags. 


## Semantic UI:  I See What You Mean

The promise...the promise of technology is always that it will make your life better, easier, or make you more money.  The following code highlights the promise of a more transparent way to style your web design by using natural language:

````html
<div class="ui three buttons">
  <button class="ui active button">One</button>
  <button class="ui button">Two</button>
  <button class="ui button">Three</button>
</div>
````

Anyone familiar with English could easily infer that parent div class governs three buttons.  They may not know what it will look like without a visual example, but the expectation is that there will be three buttons, and first one will be "active."  Better still:

````html
<div class="ui centered aligned three column grid">
  <div class="column">One</div>
  <div class="column">Two</div>
  <div class="column">Three</div>
</div>
````
The parent div governs a centered aligned three column grid.  What I mean is what I get.  This is of course how we end up with 20+ competing languages and frameworks, but its a promise that my most incredulous and lazy self cannot helped be charmed by.  The real problem of course is that nothing is ever this easy.  The hard trade off with Semantic UI is learning how it behaves when you start using it more complicated ways.  


## Semantic UI:  What I mean is not what I see...

I learned today a lesson that I will not soon forget.  I spent well over 10 minutes trying to center the bottom elements for a mock up of the Hard Rock Cafe web page.  If we just read the code using natural language that then code below should work.  

````html
<!--<div class="ui centered aligned borderless inverted menu">-->
  <!--<div class="item"><i class="phone icon"></i>+1-808-955-7383</div>-->
  <!--<div class="item"><i class="mail icon"></i>Email Us</div>-->
  <!--<div class="item"><i class="home icon"></i>280 Beachwalk, Honolulu, HI 96815</div>-->
  <!--<div class="item"><i class="twitter icon"></i></div>-->
  <!--<div class="item"><i class="facebook f icon"></i></div>-->
  <!--<div class="item"><i class="instagram icon"></i></div>-->
  <!--<div class="item"><i class="pinterest icon"></i></div>-->
  <!--<div class="item"><i class="tripadvisor icon"></i></div>-->
<!--</div>-->
````
The code almost works.  Everything is great, but for some reason it does not center the menu.  Eventually, I gave up on the ui menu feature and went with:

````html
<div class="ui bottommenu centered aligned compact grid">
  <div class="item"><i class="phone icon"></i>+1-808-955-7383</div>
  <div class="item"><i class="mail icon"></i>Email Us</div>
  <div class="item"><i class="home icon"></i>280 Beachwalk, Honolulu, HI 96815</div>
  <div class="item"><i class="twitter icon"></i></div>
  <div class="item"><i class="facebook f icon"></i></div>
  <div class="item"><i class="instagram icon"></i></div>
  <div class="item"><i class="pinterest icon"></i></div>
  <div class="item"><i class="tripadvisor icon"></i></div>
</div>
````

While the code above is even simpler, I still do not know why menu would not work.  Something I plan to learn.  One of the most frustrating things about learning something new is when your expectations are not met. 

Semantic UI has a lot of promise, but it will never be as transparent as my inner-lazy-self would like.  I guess I should have expected that.  Natural language is one of the most complex parts of human civilization.  That's why we are not all poet laureates and rappers.

What I find most appealing about Semantic UI is that it seems like a step in the right direction.  I hope it is a sign that natural language will continue to gain favor over abbreviations and vague keywords.  We will probably never program in natural language, but hopefully, by having code that is easier to read because we can process parts of it through the natural language registers of our mind, then it will be less intimidating, so those of use steeped in the humanities might step forward and embrace these new tools of communication.  Well, at least for us native English speakers, but that is another language problem.

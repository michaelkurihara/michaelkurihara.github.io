---
layout: essay
type: essay
title: "\"The most durable thing in writing is style...\""

# All dates must be YYYY-MM-DD format!
date: 2018-02-04
labels:
  - Learning
  - Computer Science
  - Code Style
  - Professionalism
---

## \"The most durable thing in writing is style, and style is the most valuable investment a writer can make with his time.\" 

Opined the great American author Raymond Chandler.  _**Style**_, a word overloaded with meaning and a concept overwrought with commentaries, weighs heavily upon all would be writers regardless of whether they are crafting prose or programming code.  In this case, Chandler used the word style style in the sense of the authorial voice.  The _je ne sais quoi_ that distinguishes one writer from another.  And while all writers must find their own voice, we cab generalize Chandler's advice think of style as structured pattern or a particular design, then we shift the egocentric meaning of _**style**_ tS larger issues of function and form.  After all, the quality of writing can never be measured by simple utilitarian calculus.  


## \"Whatever, it runs fine for now.\"

[<img class="ui medium right floated rounded image" src="https://imgs.xkcd.com/comics/code_quality_2_2x.png">](https://xkcd.com/1695/)

In Randall Munroe's brilliant _xkcd_ comic strip: ["Code Quality 2"](https://xkcd.com/1695/) (featured to the right), Pony-Tail once again reluctantly reviews Cueball's code.  What follows is another volley jibes at Cueball's code to which he  retorts:  "Whatever, it runs fine for now."  But can we trust it?  Will it always work?  Are their any unintended side-effects?  Does sloppyCoding == sloppyThinking?  If only Cueball followed up with his promise from the original ["Code Quality"](https://xkcd.com/1513/) strip and "read a style guide,' he would not have endure Ponytail's vicious and seemingly well-deserved barbs.

Coding is hard enough already.  A tough algorithm can be difficult to implement, but poor style just exacerbates the problem.  Sloppy code is the "worst."  And if you wrote said sloppy code, then it also embarrassing.  Style can at least spare us all some of the shame.  Style provides a set of ground rules designed to ensure consistency, clarity, and can even save us from dangers and hours of debugging.  Styles often require us to to follow "best" practices or prevent us from using features that might be error prone.     The C programming language still has goto, but as Kernighan and Ritchie note in their  canonical _The C Programming Language_:

>C provides the infinitely-abusable goto statement, and labels to branch to.  Formally, the goto is never necessary, and in practice it is almost always easy to write code without it.  We have not used goto in this book.

Just because a language supports a feature, it does not always mean we should use it.  The promise of JSLint is to help coders avoid the worst parts of JavaScript as noted on its help page:

>JavaScript is a sloppy language, but hidden deep inside there is an elegant, better language. JSLint helps you to program in that better language and to avoid most of the slop.
>
> \- [From JSLint Help Page](http://www.jslint.com/help.html)

JSLint makes no apologies, and goes far as to warn a would-be user that:   

>JSLint will hurt your feelings. Side effects may include headache, irritability, dizziness, snarkiness, stomach pain, defensiveness, dry mouth, cleaner code, and a reduced error rate.

This probably true for all Linters and any style guide that you do not write yourself (and maybe even then).

## CheckStyle or how to make sure your code is not [\"like a salad recipe written by a corporate lawyer using a phone autocorrect that only knew Excel formulas.\"](https://xkcd.com/1513/)

My first run in with a linter came in ICS 211, the second programming class in the UHM ICS curriculum.  One of the teaching assistants convinced the professor that it was a good idea to use the CheckStyle to review our Java code.  Unfortunately, we did not start using CheckStyle until the 4 week, so we had to go back and refactor all our code to make it CheckStyle compliant.  I can still hear the groans and the muttering of four letter words.  Things got better as we clearly learned that the Eclipse IDE we were using could help us refactor the code in most cases.  Even better, as we got used to using CheckStyle, it got easier.  Like a grammar checker, it flagged the errors as we typed.  We literally learning style as we typed.

Inevitable of course, there were something that just seemed ludicrous at first.  I remember a bit of nerd rage when I discovered that the style we were using did not allow for the ternary operator.  I had just learned about it in break between ICS 111, and I was keen to use it.  I went so far as to ask the my teaching assistant for an exception. He denied my appeal.  At the time I was not happy.  I still think ternary operator has a place in Java coding, but in retrospect, I can see why you have to set a standard and keep to it.  

By the end of the semester, everyone's code "looked" far more professional.  The style we used was particularly draconian about comments.  Every method had comment, every parameter, every exception, every return statement, and so on.  Our comments started seem almost repetitive.  I often found the comments harder to write than code.  This is one of biggest limits of any linter.  CheckStyle could make sure you made an entry, but it could not evaluate the comments.  Nor could it provide any tips, which it could do for code. 

Below is a method I wrote for our hash table project, which was the hardest project of the semester.

```java
/**
 * Wrapper for Put method, which adds the specified Key and associated Value 
 * to this table, if successful, it returns null.  If the specified key is 
 * already stored in this table, then it replaces the old value and returns 
 * it.  If last put exceeds threshold, table is rehashed.  If the hash table
 * is full, throws an ArrayIndexOutOfBoundsException exception.
 * @param key The Key paired to the specified Value to put into this table.
 * @param value The Value paired to the specified Key to put into this table.
 * @return Null if the specified key and associated value is successfully put
 * into this table; if the key is already in this table, then it replaces the
 * associated value and returns the old value.
 * @throws ArrayIndexOutOfBoundsException If this hash table is full.
 * @throws IllegalArgumentException If specified key is null.
 */
public V put(final K key, final V value) {
  // checks if rehash is necessary
  if (rehashSwitchedOn && checkLoadThresholdStatus()) {
    rehash();
  }

  // should always be false if rehash method is active and working properly
  // throws exception when table is both full and put is NOT a replacement
  if (isFull() && (getKeyIndex(key) == DEFAULT_NIL)) {
    throw new ArrayIndexOutOfBoundsException("Warning this table is FULL!");
  }

  if (key == null) {
    throw new IllegalArgumentException("New Key May Not Be Null");
  }

  return put(computeIndex(key), key, value);
}
```

Looking back, I am still not satisfied with all my comments, especially the one for the method itself.  What I am happy learned from CheckStyle was the importance of the use of keyword final.  After I started using final in Java, I never had accidental assignment vs equality check again.  Getting used to always using {} with ifs was another easy adjustment and one that paid off course you never knew when you might want to add more lines following your conditionals.  

One of my happiest moments while taking ICS 211 was when I showing some friends my code.  They could not believe change in quality, and in just one semester to boot!  My only real complaint from CheckStyle is why didnot use it in ICS 111 since were using the Eclipse IDE even then.  It would have been helpful.  

The code below is from the first of three projects from ICS 111:

```java
		// plays- soundName1 position
		public void playKey1() {
			if(play==true){
			keyNote1.stop(); // resets play point
			keyNote1.play();
			scaling();
			}
		}
```

For reasons I cannot recall, this method was over-indented by one whole level and for some reason, I left all code within the if {} at the same level as if itself.  How absolutely horrifying.  CheckStyle could have saved me from that.  The great thing about CheckStyle and most linters is that you can set your own style, and a style guide could have been written for students just learning to code.

By my third ICS 111 project, my code look this: 

```java
// re-targets drone if chicken moves off screen
private void reTargeting() {
  chicks.add(mine);  // returns the off-screen chicken to chicks arraylist

	if(!chickens[chicks.get(0)].cooped) {
		mine=chicks.get(0);
		chicks.remove(0);
		if(borderGuard(chickens[mine].getX(),chickens[mine].getY())) {
			desty = y + (chickens[mine].getY() - getY());
			destx = x + (chickens[mine].getX() - getX());
			whereTheCoopAt(mine);
		} else {
			watchDog();  // behavior when the only chickens are off screen
		}
	}	
}
```

The virtue of this code is that at least everything is aligned.  There is only 1 nested if and else statement.  There should be a space between "mine" and "chicks" on the "mine=chicks.get(0);" line.  It is a little odd that I call variable y and the method getY() on the same line.  The comments are not the best, but at least there are some comments.  The bigger issue is the names of all the variables and methods are just unhelpful.  This another important limit to any linter.  Naming things is hard, and there's no linter that can tell if you name is a good one or not.  The problems with these names they are not helpful.  Besides getX() and getY(), whereTheCoopAt and watchDog do not really describe what the methods do.  I wrote watchDog and one of teammates wrote the ingenious whereTheCoopAt.  At the time, I thought both names were pretty clever, but now they just too clever by half as the clich&#233 goes.

## Mystery of Good Code

Figuring out what is good code and how to write good code remains an unsolved mystery.  Humans are still learning.  We are still trying to solve this conundrum using the so-called Feynman.

>The Feynman Algorithm:
>
>    1. Write down the problem.
>    2. Think real hard.
>    3. Write down the solution.
>
> [- Murray Gell-Mann](http://wiki.c2.com/?FeynmanAlgorithm) 

Of course, as the joke goes, this is a lot easier if you have the brain of Richard Feynman.  For the rest of us, the writing of good code is much like the **xkcd** comic 884.

[<img class="ui large right floated rounded image" src="https://imgs.xkcd.com/comics/good_code.png">](https://xkcd.com/844/)

The beauty of style is that it gives us a good place to start.  As noted styles and "best practices" will change as programming and the change in tandem.  One cannot help but wonder with the development of AI that can write programs, how will that effect the way we code.
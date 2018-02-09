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

Coding is hard enough already, reading sloppy code is like trying to glean an algorithm through a opaque window.  Sloppy code is the proverbial "worst."  And if you wrote the sloppy code, then it is the worst plus humiliating.  Style can at least spare some of the shame.  Style is a set of ground rules designed to ensure consistency, clarity, and even coding problems by their requiring the coder to follow certain practices or by restricting certain practices.    Consider, the C programming language still has goto, but in the 2nd edition of the cannonical _The C Programming Language_, Brian Kernighan and Deniss Ritchie note:

>C provides the infinitely-abusable goto statement, and labels to branch to.  Formally, the goto is never necessary, and in practice it is almost always easy to write code without it.  We have not used goto in this book.

Just because a language supports something, does not mean one should use it.  The JSLint promises to help coders by avoiding the worst of JavaScript.

>JavaScript is a sloppy language, but hidden deep inside there is an elegant, better language. JSLint helps you to program in that better language and to avoid most of the slop. JSLint will reject programs that browsers will accept because JSLint is concerned with the quality of your code and browsers are not. You should gladly accept all of JSLint's advice.
>
> \- [From JSLint Help Page](http://www.jslint.com/help.html)




>JSLint will hurt your feelings. Side effects may include headache, irritability, dizziness, snarkiness, stomach pain, defensiveness, dry mouth, cleaner code, and a reduced error rate.



## Warning JSLint will hurt your feelings.



## CheckStyle or how to make sure your code is not [\"like a salad recipe written by a corporate lawyer using a phone autocorrect that only knew Excel formulas.\"](https://xkcd.com/1513/)

My first run in with a linter came in ICS 212, the second programming class in the UHM ICS curriculum.  One of the TA convinced the professor that it was a good idea to use the CheckStyle to review our Java code.  Unfortunatley, we did not start using CheckStyle until the 4 week, so we had to adjust all our earlier work, which was a bit of pain.

Code from my final project in ICS 111:

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

The virtue of this code is that at least everythign is aligned.  Back in ICS 111, tabs were okay.  There is only 1 nested if and else statement.  There should be a space between "mine" and "chicks" on the "mine=chicks.get(0);" line.  It is a little odd that I call variable y and the method getY() on the same line, since both get teh sm get the same information.  tThe comments are not the best, but at least there are some comments.  The bigger issue is the names of all the variables and methods are just unhelpful.  Looking back on this code, even I barely remember what all the methods do.  


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

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

Opined the great American author Raymond Chandler.  _**Style**_, a word overloaded with meaning and a concept overwrought with commentaries, weighs heavily upon all would be writers regardless of whether they are crafting prose or programming code.  In this case, Chandler used the word style style in the sense of the authorial voice.  The _je ne sais quoi_ that distinguishes one writer from another.  And while all writers must find their own voice, we cab generalize Chandler's advice think of style as structured pattern or a particular design, then we shift the egocentric meaning of _**style**_ to larger issues of function and form.  

_**Style**_ can 


Writing prose a code is never a pure utilitarian function.   for one's code to simply work.  


[<img class="ui medium right floated rounded image" src="https://imgs.xkcd.com/comics/code_quality_2_2x.png" width=75%>](https://xkcd.com/1695/)



>JavaScript is a sloppy language, but hidden deep inside there is an elegant, better language. JSLint helps you to program in that better language and to avoid most of the slop. JSLint will reject programs that browsers will accept because JSLint is concerned with the quality of your code and browsers are not. You should gladly accept all of JSLint's advice.
>
> \- [From JSLint Help Page](http://www.jslint.com/help.html)




>JSLint will hurt your feelings. Side effects may include headache, irritability, dizziness, snarkiness, stomach pain, defensiveness, dry mouth, cleaner code, and a reduced error rate.


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
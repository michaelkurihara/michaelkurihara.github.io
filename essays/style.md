---
layout: essay
type: essay
title: ""

# All dates must be YYYY-MM-DD format!
date: 2018-02-04
labels:
  - Learning
  - Computer Science
  - Code Style
  - Professionalism
---


```java
// finds the degree that the drone is heading
private double bearing(int destx, int desty) {
	double d = 0;
	int q = 1;
	int v = 0;
	int theX = 0;
	int theY = 0;
	int ax = getX();  // current position x
	int ay = getY();  // current position y

	if(destx<=ax)
		q = -1; // adjust for quadrant 1
	else
		q = 1;  // adjustment for quadrant 2

	if(desty<=ay) {
		// for quadrants 1 & 2
		theX = ((destx - ax)*(destx - ax));  
		theY = ((desty - ay)*(desty - ay));
	} else {
		if(destx<=ax)
			v = 0; // adjust for quadrant 3
		else
			v = 90;  // adjustment for quadrant 4
		// for quadrants 3 & 4			
		theX = ((ax - destx)*(ax - destx));
		theY = ((ay - desty)*(ax - destx));
	} 
	
	d = Math.toDegrees(q*(Math.atan2(theX, theY)))+v;
	return d;
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

---
layout: post
title: "Quicksort implementation and testing"
tagline: "FsCheck vs ScalaCheck"
description: "Implementing and testing Quicksort algorithm"
category: "functional exercises" 
tags: [lists, f#, scala, scalacheck, fscheck]
---
{% include JB/setup %}

In this functional exercise, I'm going to implement simple Quicksort algorithm and examine it by using property-based testing approach.  
For those who are not familiar with property-based testing, it is a great talk of Scott Wlaschin - [An introduction to property based testing](https://fsharpforfunandprofit.com/posts/property-based-testing/).  
  
Libs  
- [FsCheck](https://github.com/fscheck/FsCheck) is a library for testing .NET programs on F#, C#, and VB.  
- [ScalaCheck](https://github.com/rickynils/scalacheck) is a library used for automated property-based testing of Scala or Java programs.  
  
Both libraries are ports of Haskell's [QuickCheck](http://www.cse.chalmers.se/~rjmh/QuickCheck/), but ScalaCheck has influenced FsCheck as well.
  
  
### F&#35;  
<script src="https://gist.github.com/dkholod/c9c6f3b711c7c3ffeed81de4dcafa29c.js"></script>
_output_:  
> Check.One (config, ``list is sorted`` badSort)  
;;  
Falsifiable, after 508 tests (3 shrinks) (StdGen (93102065,296205589)):  
Label of failing property: neighbour pairs from a list should be ordered  
Original:  
[2; -1]  
Shrunk:  
[1; 0]  

> Ok, passed 100000 tests.  
  
### Scala  

Sort function looks quite similar to F# version.   
<script src="https://gist.github.com/dkholod/62a56c611ec035993d78d0f0877dff5b.js"></script>  
  
_output_:  
> \+ list is sorted.sorted list should have same length as original: OK, passe  
  d 100000 tests.  
! list is sorted.neighbour pairs from a list should be ordered: Falsified a  
  fter 1506 passed tests.  
\> ARG_0: List("0", "-1")  
\> ARG_0_ORIGINAL: List("2147483647", "-1208819329")  
\+ list is sorted.sorted list should have same length as original: OK, passe  
  d 100000 tests.  
\+ list is sorted.neighbour pairs from a list should be ordered: OK, passed  
  100000 tests.  
res0: Unit = ()  
  
  

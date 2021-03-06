title: FizzBuzz
category: Technical
date: 2013-09-14
description: Learn how to solve the FizzBuzz problem.

<h2>The Question</h2>
<p>This has become a famous problem across many programming blogs for being notoriously hard to solve, despite being very easy!  Supposedly many people fail this problem so don't become discouraged if it's' not obvious to you.  Many interviewers give this question as a warm-up expecting it to be easy only to be surprised when not many get it right.  The question is as follows:</p>

<p>"Write a program that prints the numbers from 1 to 100. But for multiples of three print "Fizz" instead of the number and for the multiples of five print "Buzz". For numbers which are multiples of both three and five print "FizzBuzz"."</p>

<h2>The Solution</h2>
<p></p>
	:::java
	for(int x = 1; x <= 100; x++) {
		if(x % 15 == 0)
			System.out.println("FizzBuzz");
		else if(x % 3 == 0)
			System.out.println("Fizz");
		else if(x % 5 == 0)
			System.out.println("Buzz");
		else
			System.out.println(x);
	}

<p>That's it!  Not so bad, eh?</p>

<p>I think what trips people up here is the ordering of the logic.  You need to make sure that you check whether it is dividible by 15 first, otherwise it will never be reachable since it would also be divisible by 3 and 5.  Using the modulus operator to check whether a number is a multiple is straightfoward.</p>

<p>You could alternatively solve it like this:</p>
	:::java
	for(int x = 1; x <= 100; x++) {
		if(x % 3 != 0 && x % 5 != 0) {
			System.out.println(x);
			continue;
		}
		if(x % 3 == 0)
			System.out.print("Fizz");
		if(x % 5 == 0)
			System.out.print("Buzz");
		System.out.println("");
	}

<p>While this is also valid, the first solution is more clear with its intent and has a better structure to its logic.  In this example it is not as obvious that it will print "FizzBuzz" for a number divisible by 15.</p>

<p>Many people on StackOverflow have taken it upon themselves to come up with more <a href="http://stackoverflow.com/questions/11764539/writing-fizzbuzz">unique solutions</a>, though they are in C#. :)</p>
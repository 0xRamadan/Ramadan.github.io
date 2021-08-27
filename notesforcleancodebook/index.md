# NotesForCleanCodeBook


{{< figure src="/images/CleanCodePicture.jpg" title="Clean Code book" alt="a picture for clean code book" >}}

<b>All my notes are going to be on my github account</b>
<a href="https://github.com/RaymondReddigton" target="_blank">My Github Account</a>
<div>

## Chapter 01
Note of Chapter one

### Introduction

5:44 PM 11/23/2020
Name: mahmoud Abdallah Hassan

				Clean Code Book
				      Chapter 01
				      Clean Code
• code represents the details of the
  requirements.

• specifying requirements in such detail that a machine can execute them is
  programming. Such a specification is code

• But we will never eliminate necessary precision—so there will always be code.

• It was the bad code that brought the company down.

• If you are a programmer of any experience then you’ve felt this impediment many times. Indeed, we have a name   for it. We call it wading. We

• LeBlanc’s law: Later equals never.

‎
• No change is trivial.
• Management does the only thing they can; they add more staff

• (new staff): They don’t know the difference between a change that matches the design intent and a change that   thwarts the design intent

### The Grand Redesign in the Sky
• The Grand Redesign in the Sky:
	Eventually Management bend to the demands of the developers and authorize the
	grand redesign in the sky.
	A new tiger team is selected.
	Now the two teams are in a race.
	Management will not replace the old system until the new system can do everything that the old system 		does.
	This race can go on for a very long time. (could take 10 years)
	the new system be redesigned because it’s such a mess.
	(moral): keeping your code clean is not just cost effective; it’s a matter of professional survival

### Attitude
• Attitude:
	We are unprofessional.
	This may be a bitter pill to swallow.
	(as programmers): we should not be shy about telling them what we think.
	It’s your job to defend the code with equal passion.
	(moral): it is unprofessional for programmers to bend to the will of managers who don’t understand the 		risks of making messes.

• The Primal Conundrum:
	True professionals know that the second part of the conundrum is wrong. You will not make the deadline 		by making the mess.
	The only way to make the deadline—the only way to go fast—is to keep the code as clean as possible at all 	times.

### The Art of Clean Code
• The Art of Clean Code?:
	The bad news is that writing clean code is a lot like painting a picture. Most of us know when a picture is 		painted well or badly. But being able to recognize good art from bad does not mean that we know how to 		paint. So too being able to recognize clean code from dirty code does not mean that we know how to write 	clean code!

	Writing clean code requires the disciplined use of a myriad little techniques applied through a 			painstakingly acquired sense of “cleanliness.” This “code-sense” is the key. Some of us are born with it. 		Some of us have to fight to acquire it. Not only does it let us see whether code is good or bad, but it also 		shows us the strategy for applying our discipline to transform bad code into clean code.

### What Is Clean Code
• What Is Clean Code?:

#### Bjarne Stroustrup quote
	Bjarne Stroustrup, inventor of C++
	and author of The C++ Programming
	Language.

		"like my code to be elegant and efficient. The
		logic should be straightforward to make it hard
		for bugs to hide, the dependencies minimal to
		ease maintenance, error handling complete
		according to an articulated strategy, and performance
		close to optimal so as not to tempt
		people to make the code messy with unprincipled
		optimizations. Clean code does one thing
		well."
##### notes	
	notes: 
		• “elegant.” pleasingly graceful and stylish in appearance or manner; pleasingly ingenious 				and simple.
		• efficienc
	                 • “tempt.” Bad code tempts the mess to grow!
	     	• One broken window starts the process toward decay.
	  	• clean code does one thing well
	  	• Bad code tries to do too much.


#### Grady Booch quote
	Grady Booch, author of Object
	Oriented Analysis and Design with
	Applications

		"Clean code is simple and direct. Clean code
		reads like well-written prose. Clean code never
		obscures the designer’s intent but rather is full
		of crisp abstractions and straightforward lines
		of control."
##### notes
	notes:
		• a readability perspective
		• It should contain only what is necessary.

#### Dave Thomas quote
	“Big” Dave Thomas, founder
	of OTI, godfather of the
	Eclipse strategy

		"Clean code can be read, and enhanced by a
		developer other than its original author. It has
		unit and acceptance tests. It has meaningful
		names. It provides one way rather than many
		ways for doing one thing. It has minimal dependencies,
		which are explicitly defined, and provides
		a clear and minimal API. Code should be
		literate since depending on the language, not all
		necessary information can be expressed clearly
		in code alone."
##### notes
	notes:
		• clean code makes it easy for other people to enhance it.
		• Code without tests, is not clean.
		• Smaller is better.
		• literate: the code should be composed in such a form as to make it readable by humans.
	
#### Michael Feathers quote
	Michael Feathers, author of Working
	Effectively with Legacy Code
		

		"I could list all of the qualities that I notice in
		clean code, but there is one overarching quality
		that leads to all of them. Clean code always
		looks like it was written by someone who cares.
		There is nothing obvious that you can do to
		make it better. All of those things were thought
		about by the code’s author, and if you try to
		imagine improvements, you’re led back to
		where you are, sitting in appreciation of the
		code someone left for you—code left by someone
		who cares deeply about the craft."

##### notes	
	notes:
		• paid appropriate attention to details.


#### Ron Jeffries quote
	Ron Jeffries, author of Extreme Programming
	Installed and Extreme Programming
	Adventures in C#.
	
		"In recent years I begin, and nearly end, with Beck’s
		rules of simple code. In priority order, simple code:
		• Runs all the tests;
		• Contains no duplication;
		• Expresses all the design ideas that are in the system;
		• Minimizes the number of entities such as classes, methods, functions, and the like."
#### notes	
	notes:
		• duplication: it’s a sign that there is an idea in our mind that is not well represented in the code.
		  didn't understand that 

		"however. I also look at whether an object or method is doing more than one thing. If it’s an 			object, it probably needs to be broken into two or more objects. If it’s a method, I will always 			use the Extract Method refactoring on it, resulting in one method that says more clearly what it 			does, and some submethods saying how it is done."


		• all programs are made up of very similar elements.
		• Reduced duplication, high expressiveness, and early building of simple abstractions.
### We Are Authors
• We Are Authors:
	• The next time you write a line of code, remember you are an author,
  	  writing for readers who will judge your effort.
	• there’s no way to write code without reading it, so making it
	 easy to read actually makes it easier to write.

### Conclusion
• Conclusion: 
	Books on art don’t promise to make you an artist. All they can do is give you some of the
	tools, techniques, and thought processes that other artists have used. So too this book cannot
	promise to make you a good programmer. It cannot promise to give you “code-sense.”
	All it can do is show you the thought processes of good programmers and the tricks, techniques,
	and tools that they use.
</div>

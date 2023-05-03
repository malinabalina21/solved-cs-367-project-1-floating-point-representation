Download Link: https://assignmentchef.com/product/solved-cs-367-project-1-floating-point-representation
<br>
This is to be an individual effort. <strong>No partners</strong>.

No late work allowed after 48 hours; each day late automatically uses up one of your tokens (or when you’re out of tokens, causes a penalty – see the syllabus)




In class, we talked about the IEEE standard for floating point representation and did examples using different sizes for exponent and fraction fields so that you could learn how to do the conversions.   For this assignment, <strong>you are going to write code to do this, allowing you to store these smaller floating point numbers in a 32-bit integer</strong>.




<strong>INPUT:</strong>  For this assignment, you will read in a ‘program’ and call your functions to implement these programs.   An example of one of these programs is:




<strong>x = 18.113 print x y = 4.5 a = x + y print a z = x * y print z</strong>




<strong>OUTPUT:</strong>  The output will be the current values of the given variables at the print statements.  For the above program, output would be:




<strong>x = 18.0937500000 a = 22.5937500000 z = 81.3750000000 </strong>




Some of this task is already done for you.  I will provide a program that reads in the given programs, saves the variable values and calls the functions (described next) that you will be implementing.




<strong>You are going to implement a 15 bit floating point representation, where 5 bits are for the exponent and 9 are for the fraction.</strong>  Using bit level operators, you will write functions (shown below) to help implement the program statements:

<ul>

 <li><strong>Assignment statement</strong> (<strong>variable = value</strong>) – calls your function <strong>computeFP()</strong>, which converts from a C float value to our mini-float representation (which only uses the <strong>15</strong> lowest of the given 32 bits).</li>

</ul>




<strong>int  computeFP(float val) { } </strong>

<strong>// input: float value to be represented </strong>

<strong>// output: integer version in our representation    </strong>




o Given the number of bits, the rounding you will have to do for this representation is pretty substantial.   For this assignment, we are always going to take the easy way and truncate the fraction (i.e. round down).  For example, the closest representable value for <strong><sub>18.113</sub></strong> (rounding down) is <strong><sub>18.09375</sub></strong>, as can be seen in the program output.




<ul>

 <li><strong>Print statement</strong> (print variable) – uses your <strong><sub>getFP()</sub></strong> function to convert from our mini-float representation to a regular C float value, and formats/prints it out nicely.</li>

</ul>




<strong>float getFP(int val) { } </strong>

<strong>// Using the defined representation, compute and  </strong>

<strong>// return the floating point value </strong>




<ul>

 <li><strong>Add statement</strong> – for this statement, you are going to take two values in our representation and use the same technique as described in class/comments to add these values and return the result in our representation.</li>

</ul>




<strong>      int addVals(int source1, int source2) {} </strong>

<strong> </strong>

<ul>

 <li><strong>Multiply statement</strong> – for this statement, you are going to take two values in our representation and use the same technique as described in class/comments to multiply these values and return the result in our representation.</li>

</ul>




<strong>      int multVals(int source1, int source2) {} </strong>

<strong> </strong>




<h1>Assumptions</h1>




To make your life a little easier, we are going to make the following assumptions:

<ul>

 <li>No negative numbers. The sign bit can be ignored.</li>

 <li>No denormalized (or special) numbers. If the given number is too small to be represented as a normalized number, you can return <strong><sub>0</sub></strong>.  Same thing with numbers that are too large.</li>

</ul>

<h1>Getting Started</h1>

First, get the starting code (<strong><sub>prog1_f18.tar</sub></strong>) from the same place you got this document.  Once you un-tar the handout on zeus (using <strong><sub>tar xvf prog1_f18.tar</sub></strong>), you will have the following files:

<ul>

 <li><strong><sub>c</sub></strong> – <strong>This is the file you will be modifying (and submitting).</strong> There are stubs in this file for the functions that will be called by the rest of the framework.  Feel free to define more functions if you like but put all of your code in this file!</li>

</ul>




<ul>

 <li><strong><sub>Makefile</sub></strong> – to build the assignment (and clean up).</li>

</ul>




<ul>

 <li><strong><sub>README</sub></strong> – read it.</li>

</ul>




<ul>

 <li><strong><sub>c</sub></strong> – This is the main program for the assignment. You should not change it.  It implements a recursive descent parser to read in the program files, determine what each line is supposed to do, and call your functions to convert, add and multiply.</li>

</ul>




<ul>

 <li><strong><sub>all_values</sub></strong> – This is a program I wrote to make debugging easier for me. It prints out all legal values in our representation!   This will help you determine what values you should be seeing.  For example, in the above program I assign <strong>113</strong> to x.   This number is not in the output for this program.  The closest smaller number is <strong><sub>18.0625</sub></strong> – when I see this output, I know that value is being rounded and stored correctly.</li>

</ul>




<ul>

 <li><strong><sub>program1</sub></strong>, <strong><sub>program2</sub></strong> – some sample input files. Note that the comments give information about the expected outputs.</li>

</ul>




<ul>

 <li><strong><sub>h</sub></strong> , <strong><sub>fp.h</sub></strong>, and <strong><sub>fp.l</sub></strong> – You can ignore these files – They are the Lex specification which tokenizes input and sends it to the recursive descent parser in the main program.</li>

</ul>

<h1>Implementation Notes</h1>

<ul>

 <li>Program Files – The accepted syntax is very simplistic and it should be easy to write your own programs to test your code (which I strongly encourage). Variable names are single lower case letters.  Comments start with the character ‘#” and go to the end of the line.   There are 4 different statement types:</li>

 <li><strong>print x </strong> – where x is a variable.</li>

 <li><strong><sub>x = <em>value</em></sub></strong> – for some floating point value.  This statement has the obvious meaning.</li>

 <li><strong><sub>x = y + z</sub></strong> – for any legal variable names o <strong><sub>x = y * z</sub></strong>  – for any legal variable names</li>

</ul>

<strong> </strong>

<strong> </strong>



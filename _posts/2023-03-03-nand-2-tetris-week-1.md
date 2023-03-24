---
layout: post
title:  "NAND 2 Tetris - Week One"
date:   2023-03-03
---

# Nand 2 Tetris - Week 1 👾

> This is part of the OSSU journey mentioned [here](https://gl4ss3s.github.io/ossu/2023/02/14/BackToSchool.html)

When becoming more and more curious about CS, and you want to start learning how everything is put together, one will eventually be guided to a course called **Nand-2-Tetris**.

As part of me keeping track of the journey, I though what better way than to show what is covered and give some guidance to those looking to take part in the course.

*P.S. This will not explain the concepts found in the course, but I will however be giving some code snippets (also not all of them)*
*Along with this article and other resources on the internet, you will be able to get the code snippets for most, if not all gates (Not that I would know 👀 **cough**..**cough**), you should try and complete it on your own and use this merely as a guide on how to complete the assignment*

When starting with the course, the instructors give a good overview of what will be covered and be the focus. Every week covering a different topic on how to build a computer (from scratch).

You will be using their Hardware Simulator during the duration of the first week and is probably going to take a bit of getting used to when using the language used to describe the Logic Gates.

Soon after the main section you will be given a challenge to complete.

### How to approach it 🤔

The instructors will ask you to complete each Logic Gate in the sequence it displays in the downloaded files.

![Project-01](https://res.cloudinary.com/thurling/image/upload/v1677831364/Blog%20Posts/Nand-week-one/Screenshot_2023-03-02_at_20.31.47_qmrooh.png)


Now this list won't mean to much at this point, but when going through the first challenge you will be asked to complete them from the top down, unless I misunderstood the professors explanation, I disagree with this approach for the following reason.

There are 2 types of Logic Gates that will be built:
 - Elementary Logic Gates i.e. simple gates
 - Composite Logic Gates i.e. more complex gates built on the foundations of the simpler ones or other composite ones

I would recommend the starting point to be completing all the elementary gates, which are **AND, OR & NOT** so you don't sit for hours on end trying to implement different varieties of **NAND** gates for each implementation and then wanting to start drinking when one bloody `0` should be a `1` and everything else is fine.

So lets start with the **AND (^)** gate, which you will use quite a bit, you can implement it like the following:
```hdl
CHIP And {
	IN a, b;
	OUT out;

	PARTS:
	// Put your code here:
	Nand(a=a, b=b, out=nand);
	Nand(a=nand, b=nand, out=out);
}
```
Once this chip is complete you will be asked to complete a 16-bit version of the same chip, this is isn't terribly difficult, now one thing to note because this isn't your normal programming language. Things like `if` statements or `for` loops are not available so for a 16-bit version you're basically going to do some copy-pasting:
```hdl
CHIP And16 {
	IN a[16], b[16];
	OUT out[16];

	PARTS:
	// Put your code here:
	And(a=a[0], b=b[0], out=out[0]);
	And(a=a[1], b=b[1], out=out[1]);
	And(a=a[2], b=b[2], out=out[2]);
	And(a=a[3], b=b[3], out=out[3]);
	And(a=a[4], b=b[4], out=out[4]);
	And(a=a[5], b=b[5], out=out[5]);
	And(a=a[6], b=b[6], out=out[6]);
	And(a=a[7], b=b[7], out=out[7]);
	And(a=a[8], b=b[8], out=out[8]);
	And(a=a[9], b=b[9], out=out[9]);
	And(a=a[10], b=b[10], out=out[10]);
	And(a=a[11], b=b[11], out=out[11]);
	And(a=a[12], b=b[12], out=out[12]);
	And(a=a[13], b=b[13], out=out[13]);
	And(a=a[14], b=b[14], out=out[14]);
	And(a=a[15], b=b[15], out=out[15]);
}
```
And in the spirit of letting you try your best and not giving anything away, now you can go and implement the **OR & NOT** gates before we move one to the next part.

### Composite Logic Gates 🧱

For the composite gates mentioned, they will take advantage of the the work you did previously and so now it's time to complete the **Mux, DMux & XOR** and all their multi-way/-bit counterparts.

> **XOR** shouldn't be too difficult to complete so I am not going to focus on that one.

So just to get you started, we will focus on the **Mux** Logic Gate:
```hdl
CHIP Mux {
	IN a, b, sel;
	OUT out;

	PARTS:
	// Put your code here:
	Not(in=sel, out=nsel);

	//OR
	And(a=a, b=nsel, out=c1);
	And(a=b, b=sel, out=c2);
	Or(a=c1, b=c2, out=out);
}
```
The above spec will output either `a` or `b` based on the value you chose for `sel` . Now as you've guessed...it's your turn to complete the  rest of the gates.

#### Conclusion

Hopefully this sent you on the correct path on how to approach the assignment, by outlining the best place to start with based on personal experience.

"But you can use the basic functionality without implementing it yourself..." I here you say, and to that I say you are correct sir, but, if you are anything like me and you forgot about this specific *feature*...this will save you from some pain and suffering.

Anyhow...if you don't want to try and complete everything, you can find all the code snippets in my gists:
[Not Judging 👀](https://gist.github.com/Gl4SS3S)

# Risk Calculator
A fine grained application security risk calculator for MacOS X written in Objective C. 

This is what we use at Threat Intelligence to rate risks. It's loosely based upon the OWASP Risk Methodology, but has
some allowances for OSTMM 3 isms, such as attack chaining. 

So no more guessing if stored XSS is really a big deal, calculate it!


## How does it calculate the risks?

If you are trying to guess the magic sauce as to where the risk factors are weighted, I use integer tag values on individual menu attributes. These tags are set between 0 .. 3 .. 6 .. 9, and are used to determine each impact factor. The code uses selectedTag to obtain the tag value I set in the scene editor:

    chainingFactor = (double)[chaining selectedTag];

I felt it was quicker to do it that way than have a lot of language comparisons in the code. 

## Where is your risk table?

Our risk table is currently expressed in a multi-dimensional NSArray. I think a good future version might spin this out to a dynamic risk table and offer choices such as a 3x3, 4x4 (ISO 31000), and 5x5 tables of different sorts, and to allow customization so you can make your own without compiling. But for now... it is what it is. 

Code
(C) 2015 Andrew van der Stock, andrew@threatintelligence.com 

Licensed under the GPLv3. If you need a different license, please ask - I do not bite. 

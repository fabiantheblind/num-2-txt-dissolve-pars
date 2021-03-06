#numbering-2-text-dissolve-paragraphs  

this is a ID CS6 script 4 [SR.V Design](http://srv-design.de/).  

##prerequisites  
Create from your InDesign Footnotes Endnotes using [foot_to_endnote.jsx by Peter Kahrel.](http://www.kahrel.plus.com/indesign/foot_to_endnote.html)  

##What Happens  
1. It removes all [`paragraphDestinations`](http://jongware.mit.edu/idcs6js/pc_ParagraphDestinations.html) in the document  
2. It takes the selected story and converts all numbering to text via [`convertBulletsAndNumberingToText()`](http://jongware.mit.edu/idcs6js/pc_Paragraph.html#convertBulletsAndNumberingToText).  
3. It converts TAB to WHITESPACE  
4. It converts LINEBREAK to WHITESPACE  
5. It converts CARRIAGE RETURN to DIGIT WHITESPACE  
6. It converts DIGIT WHITESPACE + ( DIGIT (1 to 100000 times) + 0 (1 to 100000 times) + PERIOD ) = VARIABLE to CARRIAGE RETURN + VARIABLE  

##Usage  

1. Copy your pages with the endnote stories into a new document (drag & drop works fine)  
2. Select the first textframe of the story you want to dissolve.
3. Run the script  

##Source  
![source image](https://raw.github.com/fabiantheblind/num-2-txt-dissolve-pars/master/source.png)  
##Result  
![result image](https://raw.github.com/fabiantheblind/num-2-txt-dissolve-pars/master/result.jpg)  


##Misc  
###Grep Expression Numbers  
There is also a [GREP .xml](https://raw.github.com/fabiantheblind/num-2-txt-dissolve-pars/master/find%20numbers%20SV.xml) included to find every "10.", "20.","30." and so on and replaces them with a CARRIAGE RETURN and the result.  

    <FindExpression value="~/(\d{1,100000}0{1,100000}\.)">
    
    <ReplaceExpression value="\r$1">

##License  
Copyright (c)  2013 Fabian "fabiantheblind" Morón Zirfas  
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software  without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to  permit persons to whom the Software is furnished to do so, subject to the following conditions:  
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.  
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A  PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF  CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.  

see also http://www.opensource.org/licenses/mit-license.php

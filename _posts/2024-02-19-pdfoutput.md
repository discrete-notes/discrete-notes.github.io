---
layout: post
title: pdfoutput = 1
redirect_from: "/2024/02/19/pdfoutput/"
permalink: pdfoutput
---

A short post to share a latex trick. 

I ran into the following issue twice when submitting a paper to arXiv: I get an error
saying that the pdf could not be produced, although everything works well
on overleaf and on my computer. The arxiv compilation logs seem to say that 
everything is fine. The arXiv advice for this type of error is not really 
helping, just hinting that there could be a problem with figures. 
And indeed there are some tikz figures in these papers, but nothing fancy. 
Also the document classes are some standard ACM or LIPICs; nothing problematic 
there a priori. 

The truth is, I still don't know what is the problem. My student Sébastien 
and I just dug up some forum with a magic spell. Just add the following 
in the first lines of the pdf:

    \pdfoutput=1
    
After that it works perfectly. If you run into similar trouble, maybe this 
will help. 




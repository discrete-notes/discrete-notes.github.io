---
layout: post
title: Compiling old latex with latexrelease
redirect_from: "/2024/03/05/latexrelease/"
permalink: latexrelease
---

One more latex trick, which could be helpful to you too.

It has happended to me a few times that I'm recompiling some oldish beamer, 
and a file that would compile perfectly a few years back, now has weird 
error messages. For example:

	! Extra \endgroup.
	\document ->\beamer@firstminutepatches \endgroup
	\par \AtBeginDocument {\@if...
	l.58 \begin{document}
	Things are pretty mixed up, but I think the worst is over.
	
Last time, I found a workaround, which is to compile with the latex compiler 
from a few years back. This can be done easily with the 
[latexrelease](https://www.latex-project.org/help/documentation/latexrelease.pdf)
package. 

For example, in my case, having the document start by

	\RequirePackage[2020-02-02]{latexrelease}
	\documentclass{beamer}
	
solved the issue.


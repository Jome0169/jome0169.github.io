---
layout: post
title:  "My Toolbox"
date:   2018-01-19 9:00 -0600
tags: old-postings
share: false
---
It seems like everyone who does computational biology has a different workflow.
Whether it be a different IDE, different libraries, everyone has a set up that is uniqly their own. In an attempt to distill my
knowledge to those who might be interested, I thought I'd
write a quick post detailing some components of my workflow that I couldn't
live without.

## IDEs/Text Editors:

#### VIM

If you know me, this won't surprise you. I'm an avid VIM user. I find its
'lightweightness' as well as its universal occurrence on servers essential. Need to open a massive 4Gb file in it? Sure! It
won't be pretty, but god damn does it work. Need to make a quick edit to that
script you just copied over? Easy Peazy. 

This paired with its massive archive of plugins makes it an amazing editor that
can do anything sublime2 or visualstudio code can. It's also a text editor that I find consistently rewards you for 
sticking with it. If you find yourself coding along, consistenly hitting the
same "Pain point", the VIM community has come up with a macro combination to solve it. 

#### RStudio 

If you use R, you know what this is and why you need it. It makes writing R
scripts joyous, logically displays your environment, and makes graphing/ 
dealing with packages easy. 

## Command Line 'Accessories'

#### TMUX
Honestly, between TMUX and VIM, I'm not sure which has had a larger
effect on my workflow. At this point both are completely indispensable to me,
albeit for different reasons.

TMUX is a terminal multiplexer. It allows users to split their singular
terminal session into multiple, allowing you login once, and then have a pane
dedicated to writing bash scripts, copying over data, etc...

Not sold? It ALSO doesn't log off much like **screen**, meaning you can open up
3-4 windows, run separate commands, detach the session, and come back later.
This has so so so many added benefits. Hit the wrong hot key and close your
terminal window? YOUR WORK IS STILL THERE!!!. Honestly, I can't praise TMUX
highly enough. It's infinite customizability, and integration with VIM
transforms both these softwares into an amazing IDE that can be accessed on any
remote server.

It's a computational biologists dream.

#### fd (like find, but I can remember the command)

Finding files is a pain in the ass with the `find` command. For whatever reason
I can never seem to remember the inane synatx

#### CONDA
This is possibly my most recent addition to my workflow as of late. But my GOD,
I don't know how I ever lived without it before. Conda is a container workflow
that allows a user to generate a specific enviornment to run their software. So
if you're having issue getting all of your python library installs to work
across different clusters, conda is a god send. Its actually hard to imagine
just how much time it has saved me overall.

## Libraries

#### pybedtools/pysamtools

Possibly the best python libraries I've ever used. Well documented, fast,
excellent usage scenarios. It's saved me countless hours, and allowed me to
break up the standard worflow of "Data -> Command Line App -> python 
-> output" to just "Data -> python -> output", allowing me to avoid a full
step. 

This paired with the fact that these libraries are very well tested, and have
some pretty sophisticated communities around them allow me to relax just a bit
more, and focus on my science.

#### Tidyverse 
I dislike the R programming language. I think it's poorly written, and
needlessly complex. It's the perl of statistics in so many ways. The Tidyverse
basically makes R usable. If you're not using it I weep for you.


## Bonus

#### Rhodia Sketch pad
Honestly, sometimes you just desperatly need to sketch out your ideas. I'm a
massive believer that

#### R for data analysis 
I still suck at R for the most part. So this free E-book for me has been an
absolute godsend. 

#### Good headphones



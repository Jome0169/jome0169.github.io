---
layout: post
title:  "Getting Started in Bioinformatics"
date:   2018-01-19 9:00 -0600
tags: old-postings
share: false
image:
---

This is a question I see all the time online. It has many variants, but the
most frequent I see goes something like - "Where should I start, and what do I need to learn to get into bioinformatics/genomics?". So, in the hopes of providing decent answer to those just getting started in the field, I wanted to write a brief post with the hopes of pointing you in the right direction. This guide it by no means intensive introduction to the field, nor is it meant to be. The reality is that bioinformatics as a field is far too vast and large for me to try and  describe everything you will need to learn. Rather, I'll just be highlighting a few powerful building blocks that'll get you started quicklky.

One point I want to make clear before we begin, is that this blog post is
written for those who have biological questions they want to ANSWER using
computation and computer science. This is wholly different from the valuable 
group of biologist pursuing method development (creating software). While many of the skills
overlap, I can't appreciably write a guide from this perspective as it's not
my own. 

Someone who is a biologist who wants to answer biological questions qill have a
very different avenue of learning than someone who is trying to create tools
for biologist to learn. But alas, the roadmap waits...

##### 1. The Very Beginning

The first thing you must learn is command line. It's the cornerstone of
learning to interact with data on your computer, and learning that you can
divorce yourself from programs such as EXcel and be totally fine. You can thinkg og command line as a simplified and stripped back method in which you can access and interact with your computer. Instead of using a [graphical user interface](https://en.wikipedia.org/wiki/Graphical_user_interface)(GUI for short), you'll be working with your computer on a more basal level of only text commands. While this may appear intimidating at first, the pay offs of learning it thoroughly have massive returns on your productivity. 

To learn the ins and outs of command line there are two places I would
recommend starting. If you're technophobic and a little unsure of yourself i would recommend [Code Academys command line course](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwjLgLKUia_fAhUln-AKHepWA58QFjAAegQIAxAC&url=https%3A%2F%2Fwww.codecademy.com%2Flearn%2Flearn-the-command-line&usg=AOvVaw2W4SXDZOVLJGgMMuEIe6j-). Code Academy offers users the opprotunity to begin learning the basics of using command lines on a computer without the need to worry about "messing up" your computer. However, while this might seem great, at some point you will have to pivot to actually using command line on your personal system. For this, I think the best turtorial I have found is http://www.ee.surrey.ac.uk/Teaching/Unix/ Basic
commands and excercises. Worth your time. It covers the very fundamentals much
like code academy, but makes the transition to your own machine easy and
intuitive.

One of the main resons I tell people to start here is that most bioinformatics software is not created to be run with a GUI. The designers
of said softwares are far more focused on results rather than creating a
simplified programming interface. So if you're interested in actually
assembling your genome, or transcriptome, or calling peaks, or ANYTHING -
you'll have to use command line.Being proficient in it is of massive importance. I would go so far as to say that if you can't use the command line, you can't do bioinformatics on any discernible level. And while there are [companies](https://www.geneious.com/) attempting to mitigate the need for command line interfaces, these tools are severluy under powered, and slow in comparison to doing it to yourself. 

##### 2. The Actual Programming

While learning the command line is a crucial step in bioinforamtics, learning
to program and script are fundamental and important skills any developing
bioinformatician must learn. 

Often times the output from software isn't exactly what you want. Or it simply
won't be imputed very easily due to the nature of the file format. But then
you're left with an issue. How do you parse a 3GB file and remove the
information you want? You might be able to do it on command line using a combo
of awk, and or grep, but what if the operations you're performing are very
complex? 

The best solution to this issue is to begin teaching yourself 'scripting'. Scripting can basically be thought of as writing small pieces of code that can help you impute different types of data to a more reasonable format. At a basic level if can make working with text files a much easier affair, and at a higher level it opens up avenues for publishing bioinforamtics software for others to use.

Something I want to mention is that if you're just getting into scripting, the
distance between writing your first for loop, and solving your first
bioinformatics task can be quite large. With this space irritation can easily
creep in and frusturate first time learners. That's why I always reccomend
people attempt to apply the skill they're learning as quickly as they can, to
begin to give them direction and an a basic understanding of use cases.

At first scripting can seem like and inconquerable task. It can seem like the
difference between someo one who is fluent in a langauge and yourself is
massive. But like anything else, it's simply a matter of taking your time, and
practicing. Writing scripts that are always a little bit outside of what you're
capabale of.

But, enough motivation, and on to the resources. First and formost, learn
python, and Python 3 at that. Any other langauge is simply archaic, and not
worth your time (come at me perl boys). To learn python, the most effective
tools I used were two fold - [Learn python the hard
way](https://learnpythonthehardway.org/), and [code academy 
intro to python course](https://www.codecademy.com/learn/learn-python). Both offer the basics of the language and syntax
and put you on the fast path to learning a language. Make sure you're focusing
on questions such as "how could I use this data type in my own questions?
Should i put this fasta file into a string, or a dictionary, and what are the
benefits?""

If you're looking for immediate practice as well, check our
http://rosalind.info . Rosalind is an awesome sight named after one of the
discoverers of DNA (Rosalind Franklin), and offers some excellent practice
problems that allow you to pivot your basic python understanding to solving
basic bioinformatics task. These probelms scale quickly, so be ready for a
challenge!


##### 3. Getting to Know The "Greatest Hits"

Time and time again in this field you will most likely find yourself reaching
for the same slew of tools. Tools that are so central to the analysis and usage
of next generation sequencing (NGS) data that you'll find yourself using them
consistenly. A brief list of tools that I find myself using on the regular are
tools such as 

* SAMTOOLS
    - Alignment software for aligning whole genome shotgun (WGS) reads from an experiment to a reference genome. This is an essential step in almost all
analysis in bioinformatics

* BLAST
    - BLAST is a pariwise alignment tool that lets you align two sequences
    together that you wish to compare. Lets say you want to compare two genes
from the same family and see how "similar" they are? Blast can get the job done

* BEDTools
    - Can be thought of as the cousin to samtools. Operates on slightly
      different data types, but the usage remains the same. How do I find where
certain genes intersect with my reference genome? How do I know how many reads
cover a certain regions?

This list is by no means exhaustive, nor is it really even close to being so.
The tools you end up using will be very specific to your own questions and
emthods you are pursuing. 

And my last note on this. Don't worry about memorizing the manuals for any of
these tools. What I always say is the first time you use a tool, read the
manual all the way through ONCE - so you have an idea of what it can and cannot
do. After this, make sure you're using the right tool for the job. Find a
review where it is compared to other known tools, and ensure that its
performance is at least in the ballpark of usability.

If you're looking for the best guide I have found on using these tools I would
reccomend XXXXX qebstei. A phenomenal blog post that seeks to teach you the
basics of some of these aplpliocations with the real tool sets you'll be using.



##### 4. Reading Scienctific Articles

This is an aspect of bioinformatics/genomics that I believe is heavily
understated in most "intro" guides. While many such guides instruct you to get
a handle and grasp on programming, far fewer discuss the necessity of reading
everything you possibly can related to the field. With whatever you end up
pursiong there's no point in redoing work that has been done by a precursor.
Why try and create a genome assembler without knowing the current
methods? Reading, and reserach is crucial. Don't reinvent the wheel and expect
to be hailed as the genius in the field. Rather, use the wheel to get somewhere
you want to be.

Something I have found to be consistenly true in bioiformatics, and ascience as
a whole is that those who read ask the better questions, allowing them to publish research that we all actually want to read. 

It's east to cruise on your programming in this field. It's easy to be the guy
in the lab people need to write python scripts. But if you want to be a
scientist and not just someones code moneky you HAVE to, and I mean HAVE to
read widly and deeply in the field. It will make you great.


##### 5. Continuing to learn

The last point I'll make in this list is that this list is far from exhaustive
in what you'll need to do learn to 'be a bioinforamtician'.
Bioinforamtics is a massive field that is only getting more complex and
advanced as time goes on. This puts the task of continuoius development
direcltly on the individual. There comes a point where no one can teach you
everything you must learn, so it's up to you to figure out what you need to
learn, and how to learn it.

The best people in thie field are those who have a voracious desire to learn
and understand. My advice is to keep trying, and keep advancing. It's amazing
what consisten effort can yield even if you don't belive yourself to be 'gifted'. Just enjoy the process, and don't be afraid to mess up and get your hands dirty. Learning is all about making mistakes. So who really cares if you ruin a Fasta file because of a bad carrot command as long as you have backups?

Bioinformatics rewards Do-ers, so make sure you are one.

-Pablo 



---
layout: post
title:      "Done! ...So Now What?"
date:       2018-09-08 16:43:37 -0400
permalink:  done_so_now_what
---


You've made it through another section of labs and you're finally starting to feel like you're getting the hang of this coding thing, so what do you do now?  Sure, you can just continue on to the next set of classes and labs and follow the Learn.co corriculum as written, but maybe you want to do some coding in the real world first to test your understanding.  You're probably thinking "Yeah! That sounds great!" but now the question is how to get started?  Let me tell you about my favorite method (*<-- see what I did there?*) for practicing code on my own.

You could try your hand at creating your own small programs and see how it goes.  This is a great approach because it can bring all of your learnings together and test whether you understand the practice without all the hints and the tests and the structure that the Learn IDE provides you during the labs.  For me, the first time I attempted this I immediately realized that I had no idea where to start!  This helped show me that I need to go back and get better acquainted with file-structures.  Once past that hurdle, I started running into somewhat familiar challenges such as unexpected return values, keeping my variables and scope straight, etc.  It’s frustrating, but if you can fight through it and come out with a working program you will not only become a much stronger coder for having gone through all of that, but you can look with pride at your unique creation.

Yes, this is an excellent challenge, and certainly one that should be attempted at some point, but there is also another way - one that won’t pull you away from the curriculum for days or weeks at a time while you’re troubleshooting your own designs - and that is online coding challenges.  While not as extensive as building a program from scratch, I’ve found that these puzzles are often quite challenging and, since they provide very little in terms of structure, they still force me to design my own top-to-bottom solution based on the requirements given.  Additionally, I’m often forced to research and learn new concepts, rather than simply strengthening what I already know, which is a huge benefit over starting from scratch on my own.

The real bonus of these challenges; however, is the ability to compare my finished product to other users’ work.  At [CodeWars](https://www.codewars.com), the userbase votes to determine the “best” code according to several criteria, so you can compare your work to the “best practice” or the “most clever” solutions that have been found.  This is incredibly helpful because it not only provides instant feedback regarding your own work, but it also gives you the chance to see the way that more experienced coders go about solving the *exact same problem*, an opportunity not present in many other industries without finding and working with a mentor.  Looking into some of the less familiar solutions has helped me to find techniques to take my code to the next level.  Consider, for example, my first Ruby challenge solution:
```
def longest(a1, a2)
  array = a1.split("")+a2.split("")
  sorted_array = array.sort
  new_array = sorted_array.select.each_with_index {|val, i| val != sorted_array[i-1]}
  new_array.join
end
```
Now, compare that to the Best Practice for the same challenge:
```
def longest(a, b)
  (a+b).chars.uniq.sort.join
End
```
It’s clear that, even at the beginner level, there’s a lot to learn from access to these alternate solutions!  Through his window into the minds and work of experienced coders, I’ve found countless new techniques to improve the elegance of my own code.  

![](http://www.codewizardshq.com/wp/wp-content/uploads/2016/08/codewars.png)

Try it out and see for yourself!


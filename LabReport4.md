#Lab Report 4

How to change index1 to index2 with Vim
1. vim ListExamples.java (opens file)
2. <esc> (normal mode)
3. :44 <ENTER> (jump to line 44)
4. e (jump to end of word)
5. r (replace mode)
6. 2 (replace 1 with 2)

Instead of typing :44 and e, one could click at the end of “index1” on the vim file and the cursor will jump to it. This could be an easier process for some.

Alternatively, find and replace is an option, but that takes more keystrokes.

7 key sequences is needed, not including the initial keystrokes to get into vim

#1 - “:%s/sc/checker/g” to search and replace all sc occurrences to checker

Instead of using :44 , using j to get to the correct line would be more practical

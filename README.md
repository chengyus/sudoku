# sudoku 

Original source is from:
https://gist.github.com/gregnavis/5380415

## My Changes:
comment out what I found to be a hang block.
and added a paste\_input block.
The the whole code file is usable.

Implicit notes by reading the source:
1. (paste\_input): after copying (carefully select all 81 grid) and pasting from the sudokuweb.org, the user must press enter again for a blank line.
2. to list and verify using the origin to\_s, remember to use puts in front
such as "puts s.to\_s" (of course after instantiate/constructing an instance).
3. to solve, use original source's solve method. It works. But of course it spoils the fun, but the allowed\__* methods won't spoil as much.

Side note, I noticed original author's using block seem to have incorrectly used [x][y], but in my paste_\_input method I had to fix it for in to work (for the matrix not to be transposed).

Afterthought:  I started this folder actually locally trying to create an analyzer and a solver. But end up putting them into not\_used folder because it's not quiet worth the effort (but I think for Human solving, analyze should locate 
the easist row or column; that would be interesting).

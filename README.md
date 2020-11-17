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

## To Run (for those need explicit Ruby irb run syntax):
irb -r ./sudoku.rb

### Sample irb lines
```
s = Suduko.new
s.paste_input
7
 
 
5
2
 
 
8
 
1
8
 
 
4
 
 
3
 
 
6
2
 
 
3
7
9
 
3
 
 
 
1
2
9
7
 
 
4
6
 
 
5
 
 
8
 
 
 
 
9
8
 
4
 
 
9
 
2
 
4
 
 
7
5
 
 
 
6
7
 
 
4
 
7
4

3
 
 
5

# ^explicit blank line,
 => 0..80 
2.7.1 :003 > puts s.to_s
7 - - 5 2 - - 8 -
1 8 - - 4 - - 3 -
- 6 2 - - 3 7 9 -
3 - - - 1 2 9 7 -
- 4 6 - - 5 - - 8
- - - - 9 8 - 4 -
- 9 - 2 - 4 - - 7
5 - - - 6 7 - - 4
- 7 4 - 3 - - 5 -
 => nil 
2.7.1 :004 > solve(s)
 => true 
2.7.1 :005 > puts s.to_s
7 3 9 5 2 6 4 8 1
1 8 5 7 4 9 6 3 2
4 6 2 1 8 3 7 9 5
3 5 8 4 1 2 9 7 6
9 4 6 3 7 5 1 2 8
2 1 7 6 9 8 5 4 3
8 9 1 2 5 4 3 6 7
5 2 3 9 6 7 8 1 4
6 7 4 8 3 1 2 5 9
 => nil 
```

#Use

- Change the absolute jocco.CSS path and create a jocco command:

~~~
	#!/bin/bash
	julia /home/ben/Documents/installs/jocco/jocco.jl $1
~~~

- Then you can simply call:

~~~
	jocco myfile.jl
~~~

- Use a whitespace to send a comment to the doc side, and no whitespace to keep it inline.

	`# A doc comment.`
	`#An inline comment.`

#Changes

- Fixed a bug which made the code be always one block behind the comments:

	- removed `unshift!(code,"")` line from `highlight_code()` (not sure why it was there to start with).
	- fixed `m.captures == (nothing,)` to `m.captures == [nothing,]`  and  `(doc_line,) = m.captures` to `doc_line = m.captures[1]` (I guess Julia's syntax changed). 

- Moved haskell source files to a temporary folder. This means loosing these (non-essential) functionalities:
	
	- Code highlighting in documentation comments.
	- Hyperlinks for doi.

- Fixed some outdated Julia syntax.

- Used absolute jocco.CSS path.

#UTF8

On some files, the `docs` text comes out (of pandoc) as UTF8. Uncomment the line `#push!(docs, convert(UTF8String,""))`. (to do: conditional)

#Original README
                             o
                                __   __   __   __
                             | /  \_/    /    /  \_
                             |/\__/ \___/\___/\__/
                            /|
                            \|

Jocco is a simple literate-programming-style documentation generator for
Julia.  See http://lcw.github.com/jocco for more information.

#Changes

- Moved haskell source files to a temporary folder. This means loosing these (non-essential) functionalities:
	
	- Code highlighting in documentation comments.
	- Hyperlinks for doi.

- Fixed some outdated Julia syntax.

- Used the absolute jocco.CSS path (you should change it to yours) so that you can create a jocco command:

	#!/bin/bash
	julia /home/ben/Documents/installs/jocco/jocco.jl $1

- Then you can simply call:

	jocco myfile.jl

#Bug

- There is a problem with the parser. The comment blocks are one level above the code blocks. It shows on the jocco examples for the first code blocks but get fixed ater because of the white line in the html header. An ugly fix before a real one is thus to start your source file as follows:

	#This is my awesome package which does such and such.
	"

	"

	#Here is my first function. It's great.
	function great()
		println("great!")
	end

	


#Original README
                             o
                                __   __   __   __
                             | /  \_/    /    /  \_
                             |/\__/ \___/\___/\__/
                            /|
                            \|

Jocco is a simple literate-programming-style documentation generator for
Julia.  See http://lcw.github.com/jocco for more information.

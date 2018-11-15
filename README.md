# pp_move
Pre-post-processing for Distributed Proofreaders (pgdp.net): Move Sidenotes and Illustrations to paragraph breaks; rejoin continuation footnotes

PURPOSE: Pre-process a file just received from F2 to: 

1. rejoin all continuation footnotes 

2. move Illustrations and Sidenotes to the nearest paragraph break that is within the same Section and not within a Footnote. Sidenotes only move UP; Illustrations may move up or down.
    
    Exception: does not move *[Sidenotes that are not followed by a blank line and are not preceded by either a blank line or a page separator. Such *[Sidenotes are assumed to be intended to remain embedded within their paragraphs.
        
3. delete top-of-page blank lines that are followed by *[Illustration or *[Sidenote; those tags always should be at the very top of the page, so the blank lines are formatting errors.

   
REQUIRES: Python 3 or higher.

   
INSTALLATION: 

1. Create a folder; for convenience, let's call it "pp_move"

2. download pp_move.zip. It contains three files: readme.txt, pp_move.py, and pp_move.bat

3. unzip it into the pp_move folder

4. optionally, put a shortcut to "pp_move.bat" on your desktop or wherever you prefer. 
   

OPERATION: 

Preferred method (if you are running Windows): 

1. drag & drop a "projectIDxxxxx.txt" file from its project folder onto the pp_move shortcut or the actual pp_move.bat. Trying to drop it onto "pp_move.py" will not work 

2. the resulting file will appear in the project folder. It'll have the same name as the original, with "_moved" appended: "projectIDxxxxx_moved.txt". 

Alternate method (without using the .BAT file):

1. COPY a "projectIDxxxxx.txt" file to the pp_move folder 

2. rename it to "x.txt" (really "x.txt"; "x" is not a variable) 

3. run "pp_move.py" by double-clicking it (it looks for "x.txt" if it doesn't find a filename in the Command line, which it won't, as there won't be a Command line when you start it this way) 

4. it will create a file named "x_moved.txt" in the pp_move folder 

5. move "x_moved.txt" to your project folder 


USING THE NEW FILE: 

PP the new file and review the summary pp_move placed at the top, then delete it. Be sure to check for unjoined Footnotes, invalid Footnotes, and the position & validity of all [Illustration and [Sidenote tags.

Some will not have been moved between paragraphs when certain configurations of Footnotes or Blocks got in the way of finding good paragraph breaks, or because of errors in the text (usually unbalanced brackets). Searching for *[ and ]* should find most of these. 


RUN-TIME OPTION: If you do not want pp_move to rejoin footnotes, include -f or /f in the command-line, AFTER the name of the input file. The  practical way to do that is to edit PP_MOVE.BAT and change the last line of it.

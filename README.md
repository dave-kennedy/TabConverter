[Demo](http://dave-kennedy.github.io/TabConverter)

This little library does one thing: it converts music written in [VexTab](http://vexflow.com) note/octave syntax into
fret/string syntax. For example, entering this:

    vextab
    tabstave notation=true
    notes :q C-D-E-F/4 | G-A-B/4 C/5

into the "Note/octave syntax" textbox at the top of the page will produce this:

    vextab
    tabstave notation=true
    notes :q 3/5 0/4 2/4 3/4 | 0/3 2/3 0/2 1/2

in the "Fret/string syntax" textbox at the bottom of the page.

Why would this be useful? Because if you feed VexTab the fret/string syntax it will automatically produce the
corresponding notes on the staff, but the reverse is not true. i.e., if you feed VexTab the note/octave syntax it won't
automatically produce the corresponding notes on the tab.

I understand why this functionality (probably) wasn't built into VexTab: most notes on the staff correspond to more
than one fret/string position. It isn't a clear one-to-one relation. To solve this problem, the tc.convert function
accepts a position argument. Providing a value of 0 will return the lowest position available, while providing a value
of 1 will provide the next higher position, etc.

The tc.convert function also accepts an instrument argument. At the moment, it works with the guitar and mandolin. For
the mandolin, you'll also want to use the correct tuning:

    tabstave notation=true tuning=E/5,A/4,D/4,G/3

In a nutshell, you can use this script to convert a piece of sheet music to tablature. Just enter the resulting syntax
into VexTab and it will render both the staff and the tab.

How to use
==========

- Open terminal or another form of shell
- *curl -L 'https://github.com/adrianhelvik/ankicsv/raw/master/ankicsv' > /usr/local/bin/ankicsv*
- Create one or more files with the *.ankisource* extension
- Type *ankicsv some-file.ankisource*
- The result is then stored as a csv file with the same name (*some-file.csv* in this example)

About the syntax
================
The syntax for *.ankisource* files is pretty simple.
Separate questions are separated by empty lines.
Make comments with #. Preceding linebreaks can be made
insignificant by starting a line with | (pipe character).

How to write regular questions
------------------------------

    What color is the sun?
    Yellow


How to write multiple choice questions
--------------------------------------

    ? What color is the sun?
    X Green
    X Blue
    V Yellow

How to write fill-in-the-blanks questions
-----------------------------------------

    The sun is ___yellow___.

How to write multiple fill-in-the-blanks-questions in one go
------------------------------------------------------------

    % How do you make pan cakes?
    You heat the oven
    You mix stuff
    You cook

.. which is equivalent to typing:

    How do you make pan cakes?
    ___You heat the oven___
    | You mix stuff
    | You cook

    How do you make pan cakes?
    You heat the oven
    | ___You mix stuff___
    | You cook

    How do you make pan cakes?
    You heat the oven
    | You mix stuff
    | ___You cook___

How to write comments
---------------------

    # Really important question
    # I have to remember this
    What is clorophyl?
    Plant goo

    # This is even more important
    ? What do you use for scale?
    V Bananas
    X Pears
    X Apples

How to split content over several lines
---------------------------------------

    This is a really cool question,
    | .. but it is way too long for one line.
    And this is the answer!

Why this program was written
============================

Anki is wonderful, but creating many flashcards can be extremely tedious, and creating something like a multiple choice or fill-in-the-blanks question is boring.
With Ankicsv this process is automated, so you can worry about studying and not about fiddling with Anki.

Happy studying!

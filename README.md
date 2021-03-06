How to use
==========

- Open terminal or another form of shell
- `curl -L 'https://github.com/adrianhelvik/ankicsv/raw/master/ankicsv' > /usr/local/bin/ankicsv`
- Create one or more files with the `.ankisource` extension
- Type `ankicsv <file names>`
- The result is then stored as a csv files matching the names of the input files but with a `.csv` extension
- Import `.csv`-files into Anki with *Allow HTML in fields* enabled.

About the syntax
================
The syntax for *.ankisource* files is pretty simple.
Separate questions are separated by empty lines.
Make comments with #. Preceding linebreaks can be made
insignificant by starting a line with | (pipe character).

Single lines that are not fill in the blanks questions
will be ignored. For me this is a convenience as I can
create questions and add answers.

How to write regular questions
------------------------------

    What color is the sun?
    Yellow

How to write multiple choice questions
--------------------------------------

Wrong answers are marked with a capital X,
the right answer is marked with a capital V.
Only one correct answer is allowed.

    ? What color is the sun?
    X Green
    X Blue
    V Yellow

The fields are enumerated in Anki. So that
in this case the result would be:

    What color is the sun?

    1) Green
    2) Blue
    3) Yellow

How to write fill-in-the-blanks questions
-----------------------------------------

Fill-in-the-blanks questions use 3 underscores
to surround the field to hide.

    The sun is ___yellow___.

How to write multiple fill-in-the-blanks-questions in one go
------------------------------------------------------------

    % How do you make pancakes?
    You heat the oven
    You mix stuff
    You cook

.. which is equivalent to typing:

    How do you make pancakes?
    | ___You heat the oven___
    | You mix stuff
    | You cook

    How do you make pancakes?
    | You heat the oven
    | ___You mix stuff___
    | You cook

    How do you make pancakes?
    | You heat the oven
    | You mix stuff
    | ___You cook___

How to write comments
---------------------

A comment is simply a line starting with #.

    # Really important question
    # I have to remember this
    What is chlorophyll?
    Plant goo

    # This is even more important
    ? What do you use for scale?
    V Bananas
    X Pears
    X Apples

How to split content over several lines
---------------------------------------

    This is a really cool question..
    | but it is way too long for one line.
    And this is the answer!

Variables
---------

    DEFINE some stuff = the right answer

    What is ${some stuff} to this question? 1 + 1 = ___2___

.. which is equivalent to

    What is the right answer to this question? 1 + 1 = ___2___

Mixins
------

Mixins are like variables except that they accept an argument

    MIXIN true?(parameter 1, paramater 2) = Is it true that either ${parameter 1} or ${parameter 2}?

    @{true?}(the moon is blue, the sky is green)
    No

.. which is equal to

    Is it true that either the moon is blue or the sky is green?
    No

Why this program was written
============================

Anki is wonderful, but creating many flashcards can be extremely tedious, and creating something like a multiple choice or fill-in-the-blanks question is boring.
With Ankicsv this process is automated, so you can worry about studying and not about fiddling with Anki.

Happy studying!

The `commenting` LaTeX package
==============================

[![rel badge]][releases]
[![licence badge])][licence]

This package attempts to provide a simple and flexible set of macros to typeset
(and hide) comments and remarks which are supposed to be read only by the
authors of a multi-author document, during the process of writing and reviewing
it. It provides macros for printing comments inline or in the margin, giving
visual hints of their location and author. All the comments are typeset only
when in draft mode. Pdf's native comments are also somehow optionally supported
through the `pdfcomment` package.

Package options are provided to globally change aspects of the appearance of the
comments and the use of more sophisticated features (color, pdfcomment, margin
notes). This is especially useful, for instance, when switching from a normal
layout to a two columns one: setting the `nompar` option would suppress any
margin note and would include all the comments inline.

Copyright (c) 2012-2015, Emanuele D'Osualdo.

Released under the LaTeX Project Public License.

## Basic Usage

To use the package, simply put it in your path and write in the preamble

    \usepackage{commenting}

When setting up a multi-author document, you can define authors' names,
nicknames and colors (in the preamble):

    \declareauthor{fz}{Frank}{blue}
    \declareauthor{jlp}{Jean-Luc}{green!30!black}

Optionally you can change the base style for the comments:

    \setcommentstyle{\sffamily}

or the style of a particular author:

    \setauthorstyle{fz}{\itshape}

Then you can use the commenting macros in the body:

    \comment[fz]{Jazz is not dead. It just smells funny}        % a comment from Frank
    \comment[fz](11/04){Jazz is not dead. It just smells funny} % a comment with date

Other macros include `\todo`, `\annot`, `\changed`, `\draftnote`.

**Please note** that these macros will output something only when in `draft` mode.
To make them work when in `final` mode set the local `draft` mode in the `\usepackage` line.

One of the cool features of `commenting` is its ability to selectively turn comments on and off with the macros

    \onlyauthors{fz,jlp}
    \NoCommentsBefore{12/04}
    \NoCommentsAfter{20/04}
    \ExcludeNonDatedComments

To only display comments by a subset of the authors, or comments within a temporal span.

Read the documentation for more details on all the options and macros.

[releases]: https://github.com/bordaigorl/latex-commenting/releases
[rel badge]: https://img.shields.io/github/release/bordaigorl/latex-commenting.svg
[licence]: http://www.latex-project.org/lppl.txt
[licence badge]: https://img.shields.io/badge/licence-LaTeX%20Project%20Public-3C3C3C.svg
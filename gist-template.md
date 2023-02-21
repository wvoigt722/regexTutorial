# Title (replace with your title)

This tutorial has been written with the purpose of describing how to match an email using regex. The example provided will be the following : /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ This piece of regex allows its user to be able to validate whether or not something is an email. It provides ranges of characters that are associated with things that all emails have in common. In doing so it allows the user to be able to match any email.

## Summary

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ This is a piece of regex that allows someone to match an email.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

Regex is considered a literal and needs to be wrapped in / (slashes).

We see this with out example : /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

### Anchors

^ and $ are both anchors.

The ^ signifies the begining with the characters that follow it.

The $ signifies the end with the characters that preceed it.

We can see this clearly in our example :

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

\b is also an anchor we will discuss later.

### Quantifiers

Quantifiers set limits for your piece of regex. In our exmaple we see the quantifier {2,6} immediately preceedin out $. This sets a limit between 2 and 6 characters.

### OR Operator

Using the OR operator ( | ) allows the user to be inclusive in searches rather then exclusive. Instead of only being able to search for [xyz] when we use the OR operator our criteria expands to allow a match for any of those characters [x|y|z]. This is useful when grouping constructs.

### Character Classes

Character classes define a set of characters.

. - matches any character except a newline character (\n)

\s - matches and single whitespace character

\d - matches any Arabic numeric digit

\w - matches any alphanumeric character from the basic latin alphabet.

### Character Escapes

A Character Escape is something that allows us to use a character that would otherwise be interpreted literally by the regex component. Our example uses character excapes a few times.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

We notice the backslashes before the periods in this example. This is telling regex that it should be looking for a period. Usually a period is a character class that looks to match any character except a newline charcter (\n).

### Flags

Flags are an additional limit that is set on regex. It comes after the second slash mark that usually signifys the end of the regex. Some flags are:

g - global search

i - case insensitive

m - multi-line search

This gives us more control and specificity over what we would like to match. Our example does not have any flags but we could easily add one if we wished like this:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/i

Now our search would ignore case and match anything regarless of whether it was upper or lower case.

### Grouping and Capturing

Grouping and capturing is when we want to find multiple snippets of regex. Our example has three different pieces of regex that are grouped. We use () parenthesis to accomplish this.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

When we look at our example we can see the following groups:

1 - ([a-z0-9_\.-]+)
2 - ([\da-z\.-]+)
3 - ([a-z\.]{2,6})

The first will be looking for any lower case letters a-z, numbers 0-9, and if it has periods or hyphens.

the second will do the same as the first, and the third will do the same except it wont look for numbers or the hyphen and will be betewen 2-6 characters in length.

### Bracket Expressions

Bracket expression are anything between [] brackets and they represent ranges of characters we are attempting to match against.

As mentioned previously in grouping constructs. It is important to rememeber regex is case sensative. In our example we would not get any matches back for emails using capital letters since that is outside the scope of our bracket expressions.

### Greedy and Lazy Match

Greedy simply means to match the longest possible repetitions or string and Lazy means to match the shortest string or fewest possible repetions.

## Author

The author of this gist was William Voigt with reference to the following tutorial on regex:
https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial

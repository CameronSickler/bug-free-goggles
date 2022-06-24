# Cameron's Regex Tutorial Challenge
<br>

## Introduction
<br>

Hello and welcome to my regular expression tutorial. Often referred to as simply regex, it is defined as a sequence of characters that defines a specific search pattern. 

Regex is used in many different ways to make searching, replacing, validating, etc. faster and easier. I hope you find this tutorial helpful in understanding this amazing tool.
<br>
<br>

## Summary
<br>

In this tutorial I will be explaining the key components of regex with accompanying examples. At the end of the tutorial we will use what we learned in the tutorial to review a commonly used regex for matching an email. Below, is a snippet of the regex I mentioned. 
<br>
<br>

Matching an Email – 
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
<br>


After reading through this tutorial, we should have the knowledge needed to understand this regex and an explanation will be provided at the end. 
<br>
<br>
<br>

## Table of Contents
<br>
<br>

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
- [Final Example](#final-example)
<br>
<br>
<br>

## Regex Components
<br>
<br>

### Anchors
<br>
Anchors do not search for specific characters but rather look for matching positions. So put simply, anchors could be used to match before characters, after characters, or even in between characters. 
<br>
<br>

See the following commonly used anchor symbols:

`^` - carat, hat, circumflex, exponent
<br>

`$` - dollar(s)
<br>
<br>

The carat symbol is used to find a matching start position. Consider the following:

`^Apple` - when placing the carat symbol in front of the word apple, the regex is going to look for any matching string that starts with the word Apple. 
<br>
<br>

The dollar symbol is used to find a matching end position. Consider the following:

`Dog$` - when placing the dollar symbol at the end of the word Dog, the regex looks for any matching string that ends with the word Dog. 
<br>
<br>

When the carat and dollar symbols are used in conjuction, all characters in between them will be considered the string that the regex will search for an exact match of. Consider the following:

`^Happy Birthday$` - The regex will look for any matching string that starts with Happy and ends with Birthday. 
<br>
<br>

### Quantifiers
<br> 
Quantifiers are used to look for matches with a specific quantity of characters. Quantifier symbols are placed immediately after the character in question. If a quantifier symbol is intented to look for 2 or more sequencial characters, then curly brackets or paranthesis are used followed immediately by a quantifier symbol.

<br> 

See the following commonly used quanitier symbols:

<br> 

`+` - plus
<br>

`*` - asterisk
<br>

`?` - question mark
<br>

`()` - parenthesis
<br>

`{}` - curly brackets/brace
<br>
<br>

The plus symbol is used to look for one or more instances of a matching character. Consider the following:

`123+` - The regex will look for string matches where "12" is followed by at least one or more instances of "3". 
<br>
<br>

The asterisk symbol is used to look for zero or more instances of a matching character. Consider the following:

`abc*` - The regex will look for string matches where "ab" is followed by zero instances of "c" AND where "ab" is followed by one or more instances of "c". 
<br>
<br>

The question mark symbol is used to look for zero or one instances of a matching character. Consider the following:

`goodbye?` - The regex will look for string matches where "goodby" is followed by zero or one instances of "e".  
<br>

The parenthesis symbols are used to group sequencial characters for a quanitier. Consider the following:

`(abc)` - The regex would now consider "abc" as the set of characters to look for matches of depending on the quantifier that would immediately follow the closing parenthesis symbol.
<br>
<br>

The curly brackets/braces are used to look for specific quantities of character(s) instances. Consider the following:

`abc{5}` - The regex would search for matching instances where "ab" is followed by exactly five instances of "c".

`abc{5,}` - The regex would search for matching instances where "ab" is followed by five instances or more of "c".

`abc{1-5}` -  The regex would search for matching instances where "ab" is followed by one instance of "c" or more, but not containing more than five instances of "c".
<br>
<br>
<br>

### OR Operator
<br>

OR Operators are used to look for matches with one or another character. 
<br>
<br>
See the following commonly used Or operator symbols:
<br>
<br>

`( | )` - parenthesis vertical pipe parenthesis
<br>

`[]` - square brackets
<br>
<br>

The parenthesis vertical pipe parenthesis symbols look for matches of a character that directly preceeds the pipe OR a character that directly follows the pipe. Consider the following:

`a(b|c)` - The regex would search for matching instances where "a" immeidately followed by either "b" or "c".
<br>
<br>

The square brackets look for matches of one or the other characters inside the brackets. Consider the following:
<br>

`a[bc]` - The regex would search for matching instances of "a" immediately followed by either "b" or "c" but the "b" or "c" would not be captured.
<br>
<br>

### Character Classes
<br>

Character classes are used for searching specific categories or types of characters. 
<br>

See the following commonly used character classes symbols:
<br>

`\d` - digit character
<br>

`\w` - word character
<br>

`\s` - whitespace character
<br>

`.` - period character
<br>
<br>

The digit character will search for matches of a single character that is a digit. Consider the following:

`abc\d` - The regex will search for any instance of a single digit that immediately follows "abc".
<br>
<br>

The word character will search for matches of an alphanumeric character (which includes the underscore symbol). Consider the following:

`abc\w` - The regex will search for any instance of an alphanumeric character the immediately follows "abc".
<br>
<br>

The whitespace character will search for matches of any whitespace (which includes tabs and line breaks). Consider the following:

`abc\s` - The regex will search for any instance of whitespace that immediately follows "abc".
<br>
<br>

The period symbol will search for matches of any character. An example is not neccessary for this symbol.
<br>
<br>

### Flags
<br>

Flags are used for changing the default search pattern of a regex. 
<br>

See the following commonly used flag symbols:
<br>

`i` - ignore casing
<br>

`g` - search all occurances
<br>

`m` - multi-line
<br><br>

The ignore casing flag remove case sensitivity from the default search perameters. 
<br>

The search all occurances flag will change the default search parameters to instead search all possible matches in a string. 
<br>

The multi-line flag enables ^ and $ to notate the start and end of a line instead of the entire string.
<br>
<br>

### Grouping and Capturing
<br>

Grouping and Capturing is used for treating multiple characters as a single unit. 
<br>

See the following for commonly used grouping and capturing syntax:
<br>
<br>

`()` - parenthesis
<br>

`?:` - disable capture group
<br>

`?<>` - name group
<br>
<br>

The parenthesis create a capture group. Consider the following:

`a(bc)` - the regex will look for all instances of "a" that are followed by "bc".
<br><br>

The disable capture group removes the capture group from being included in the match results. Consider the following:

`1(?:23)*` - the regex will look for all instances of "1" that preceed "23" but the "23" is not included in the result. 
<br><br>

The name group provides a name for the character(s) that is between the less than greater than symbols. Consider the following:

`a(?<foo>bc)` - the regex will look for all instances of "a" that is followed by "bc" and the resulting match(s) is a value and the key is foo.
<br><br>


### Bracket Expressions
<br>
Bracket Expressions are used for matching a sepcific set of single characters or it may match a set of characters. 
<br>
<br>

See the following commonly used symbol:
<br>


`[]` - square brackets
<br><br>

The square brackets match string values based on the characters inside the brackets. Consider the following:

`[abc]` - the regex will search for string matches that contain "a" or "a b" or "a c".

`[0-9]` - the regex will search for string matches that contains a character from 0-9.
<br><br>


### Greedy and Lazy Match
<br>
Greedy and Lazy are terms to describe the size of a match result. By default quantifiers * + {} are considered greedy because matches can be expanded as far as possible through a given string. These greedy quantifiers can be refined to render more specific match results which would then be considered lazy operators. Adding a ? symbol can be used to refine match results.
<br>
<br>

Consider the following example:

`<h1> Hello World </h1>` - if a regex such as `<.+>` was used, the match would render the entire string value because it includes all characters between the very first less than symbol and the very last greater than symbol.

HOWEVER

if a regex such as `<.+?>` was used, the match would render only the `<h1>` and `</h1>` from the string because the ? is refining the search to only include all characters but from within a given set of greater than less than symbols. 
<br>
<br>

### Boundaries
<br>
Boundaries are used for refining match results to look for characters that have specific types of characters that precede or follow.
<br>
<br>

See the following commonly used symbols:

`\b` - non-word border
<br>

`\B` - word border

<br><br>
The non-word border symbol refines match results to only include results when the preceding and following characters on either side of the result are non-word characters. Consider the following:

`\b123\b` - the regex will search for all instances of "123" but only if a non-word character preceeds the beginning of the string AND another follows the end of the string. 
<br><br>

The word border symbol refines match results to only include results when the preceding and following characters on either side of the result are word characters. Consider the following:

`\B123\B` - the regex will search for all instances of "123" but only if a word character preceeds the beginning of the string AND another follows the end of the string. 
<br><br>


### Back-references
<br>

Back-references are used for reusing previous capturing groups by referencing them again later in the regex.
<br><br>

See the following for commonly used symbols:

`\1` - back slash number
<br><br>

Back slash number symbol would become the indicator reference for a previously captured group. Consider the following:

`([xyz])\1` - the regex would indentify "xyz" as the captured group and the "\1" would actually be considered "xyz" again when being used for searching matches. 
<br><br>

### Look-ahead and Look-behind
<br>

Look-ahead and Look-behind is used for modifying match results to consider if specified character(s) are directly following or preceding a matching character. 
<br><br>

See the following commonly used symbols:

`(?=)` - look ahead
<br>

`(?<=)` - look behind
<br><br>

The look ahead will search for matches and then verfiy the following character(s). Consider the following:
`a(?=b)`- the regex will search for instances of "a" but only if the following character is "b".
<br><br>


The look behind will search for matches and then verfiy the preceding character(s). Consider the following:
`(?<=a)b`- the regex will search for instances of "a" but only if the preceding character is "a".
<br><br>


### Final Example
<br>

We have come to the end of the tutorial. Let's revisit our regex for emails and see if we can understand what it is doing!
<br>
<br>
<br>

Matching an Email – 
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
<br><br>

Perhaps we can go step-by-step through the symbols and see what each of them do. Perhaps

```
/ - denotes the boundary of the regex
^ - meta escape that asserts the starting position of the string
( - begins first capturing group
[ -begins character class
a-z - matches any single character "a" through "z"
0-9 - matches any single digit "0" through "9"
_ - matches an underscore
\. - matches a . symbol
- - matches a - symbol
] - end character class
+ - greedy quantifier to include any number of preceding character class matches
) - end first capturing group

@ - matches a @ symbol

( - begin second capturing group
[ - begin character class
\d - any single digit
a-z - matches any single character "a" through "z"
\. - matches a . symbol
- - matches a - symbol
] - end character class
+ - greedy quantifier to include an number of preciding character class matches
) - end second capture group
\. - matches a . symbol
( - begin third capture group
[ - begin character class
a-z - matches any single character "a" through "z"
\. - matches a . symbol
] - end character class
{2,6} - matches previous character class between 2-6 times
) - end third capture group
$ - meta escape that asserts the ending position of the string
/ - denotes the boundary of the regex
```

<br><br>
The email regex is one of many examples of this powerful tool. Be sure to visit the web to discover other regex examples that you might consider using in the future!

I hope you enjoyed this tutorial on regular expressions and thank you for visiting!


<br>
<br>

## Author
<br>
Cameron Sickler - Full-Stack Computer Coding Student
<br>
Graduation Date - Aug 4th 2022
<br>
GitHub: CameronSickler
<br>
LinkedIn: linkedin.com/in/cameron-sickler-a17764106

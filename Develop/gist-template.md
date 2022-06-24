# Title (replace with your title) Cameron's Regex Tutorial Challenge
<br>

## Introduction
<br>

Hello and welcome to my regular expression tutorial. Often referred to as simply regex, it is defined as a sequence of characters that defines a specific search pattern. 

Regex is used in many different ways to make searching, replacing, validating, etc. faster and easier. I hope you find this tutorial helpful in understanding this amazing tool.
<br>
<br>

## Summary
<br>

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
